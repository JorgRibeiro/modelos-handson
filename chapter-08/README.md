# Capítulo 08: Redução de Dimensionalidade

## Objetivo

Estudar técnicas para reduzir o número de atributos preservando informação relevante, cobrindo PCA, variância explicada, compressão, PCA randomizado, PCA incremental, projeção aleatória, LLE e Kernel PCA.

**Status: concluído.** Notebook principal estudado, perguntas conceituais revisadas e exercícios 9 e 10 implementados e executados, com resultados em [Respostas.md](Respostas.md).

## Pré-requisitos

- Conceitos dos Capítulos 01 a 07: validação, classificação, regressão e pipelines.
- Noções básicas de álgebra linear, variância, projeções e decomposição em valores singulares.
- Familiaridade com NumPy, Matplotlib e Scikit-Learn.

## Estrutura do Capítulo

### Notebooks

| Experimento | Descrição | Dificuldade |
|-------------|-----------|------------|
| [08_dimensionality_reduction.ipynb](08_dimensionality_reduction.ipynb) | Fluxo de redução de dimensionalidade: PCA, componentes principais, projeção, uso do Scikit-Learn, variância explicada, escolha do número de dimensões, compressão, PCA randomizado, PCA incremental, projeção aleatória, LLE e Kernel PCA. | Intermediário |
| [08_exercicio_9.ipynb](08_exercicio_9.ipynb) | Experimento passo a passo no MNIST: comparação de floresta aleatória e SGDClassifier com e sem PCA, incluindo acurácia e tempos de treinamento e preparação. | Intermediário |
| [08_exercicio_10.ipynb](08_exercicio_10.ipynb) | Visualização das primeiras 5.000 imagens do MNIST com t-SNE, números e miniaturas; comparação com PCA, LLE e MDS, medindo tempo e preservação de vizinhanças. | Intermediário |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 08 do livro, com atenção à intuição geométrica de PCA.
2. **Prática**:
   - Execute o notebook `08_dimensionality_reduction.ipynb` em ordem.
   - Observe como PCA projeta dados 3D em 2D.
   - Compare variância explicada e perda de informação.
   - Use PCA para compressão e reconstrução.
   - Compare PCA randomizado, incremental, projeção aleatória e LLE.
   - Execute o exercício 9 para comparar classificadores com e sem PCA.
   - Execute o exercício 10 para comparar projeções em 2D e inspecionar os dígitos por miniaturas.
3. **Reflexão**:
   - Quando redução de dimensionalidade ajuda e quando pode atrapalhar?
   - Como escolher o número de dimensões?
   - Qual a diferença entre técnicas lineares e não lineares?

## Como Executar os Notebooks

Na pasta `chapter-08`, ative o ambiente criado conforme o [README geral](../README.md#configuracao-do-ambiente) e abra o Jupyter Lab:

```bash
source ../.venv/bin/activate
jupyter lab
```

Se estiver usando o shell Fish:

```fish
source ../.venv/bin/activate.fish
```

Execute as células de cada notebook em ordem. Os exercícios foram executados com Python 3.11.14, NumPy 2.1.3 e Scikit-Learn 1.5.2. O primeiro carregamento do MNIST pode exigir acesso à internet; depois, o Scikit-Learn reutiliza seu cache local.

Os notebooks criam automaticamente as pastas de figuras: `images/dim_reduction` no principal e `images/exercicio_10` no exercício 10. O arquivo `my_mnist.mmap`, gerado pelo exemplo de PCA incremental, permanece local e é ignorado pelo Git.

## Resultados Esperados

- ✅ Aplicar PCA manualmente e com Scikit-Learn.
- ✅ Interpretar componentes principais e variância explicada.
- ✅ Escolher número de dimensões com base na variância preservada.
- ✅ Usar PCA para compressão e reconstrução.
- ✅ Entender PCA incremental, PCA randomizado, projeção aleatória, LLE e Kernel PCA.

## Exercícios

- **Questões 1 a 8**: respostas conceituais revisadas e resumos das respostas oficiais em [Respostas.md](Respostas.md).
- **Exercício 9**: implementação em [08_exercicio_9.ipynb](08_exercicio_9.ipynb), com resultados da execução em [Respostas.md](Respostas.md#9---compare-classificadores-no-mnist-com-e-sem-pca).
- **Exercício 10**: implementação em [08_exercicio_10.ipynb](08_exercicio_10.ipynb), com resultados e figuras em [Respostas.md](Respostas.md#10---visualize-o-mnist-com-t-sne-e-compare-outras-técnicas).

## Resultados Obtidos

### Exercício 9 — Classificação com e sem PCA

Foram usadas 60.000 imagens para treino e 10.000 para teste. O PCA foi ajustado apenas no treino e reduziu **784 para 154 atributos**, preservando **95,0196% da variância**.

| Modelo | Dados | Treinamento do classificador | Acurácia no teste |
| --- | --- | ---: | ---: |
| Floresta aleatória | Originais | 6,38 s | 97,05% |
| Floresta aleatória | PCA | 19,11 s | 94,88% |
| SGDClassifier | Originais | 64,97 s | 88,47% |
| SGDClassifier | PCA | 13,95 s | 88,13% |

O PCA tornou o treinamento da floresta cerca de **3 vezes mais lento**, mas acelerou o SGD em **4,66 vezes**. Incluindo o ajuste do PCA e a transformação do treino, a aceleração do SGD foi de **4,28 vezes**. Nesta execução, ambos os classificadores perderam acurácia; reduzir dimensões não garante melhoria de desempenho.

### Exercício 10 — Visualização em duas dimensões

Os quatro métodos foram ajustados nas mesmas primeiras **5.000 imagens**, sem usar os rótulos. A preservação de vizinhanças foi avaliada por *trustworthiness*, com 10 vizinhos, na mesma amostra de 1.000 imagens; valores maiores indicam melhor resultado nesse critério.

| Método | Ajuste e transformação | Trustworthiness |
| --- | ---: | ---: |
| t-SNE | 7,30 s | 0,9532 |
| PCA | 0,17 s | 0,7429 |
| LLE | 2,68 s | 0,8126 |
| MDS | 79,61 s | 0,7981 |

O t-SNE apresentou grupos visualmente mais distinguíveis e a maior preservação de vizinhanças nesta configuração. Foram geradas figuras por cor, 180 anotações numéricas e 100 miniaturas. O PCA em 2D preservou apenas **17,27% da variância**. O MDS atingiu o limite de **300 iterações**, portanto mais iterações ou outras inicializações podem alterar seu resultado.

Veja a [comparação visual](images/exercicio_10/comparacao_metodos.png) e as [miniaturas no t-SNE](images/exercicio_10/tsne_miniaturas.png). As configurações completas e a interpretação estão em [Respostas.md](Respostas.md). Os tempos correspondem a uma única execução e variam conforme o computador e sua carga.

## Status de Conclusão

- [x] Conceitos fundamentais revisados nas questões 1 a 8.
- [x] Notebook principal estruturado até Kernel PCA.
- [x] Exercício 9 implementado e executado sem erros.
- [x] Exercício 10 implementado e executado sem erros.
- [x] Respostas, resultados e figuras documentados.

**Última atualização**: 19 de outubro de 2026
