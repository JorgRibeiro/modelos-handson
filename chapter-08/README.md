# Capítulo 08: Redução de Dimensionalidade

## Objetivo

Estudar técnicas para reduzir o número de atributos preservando informação relevante, cobrindo PCA, variância explicada, compressão, PCA randomizado, PCA incremental, projeção aleatória, LLE e Kernel PCA.

## Pré-requisitos

- Conceitos dos Capítulos 01 a 07: validação, classificação, regressão e pipelines.
- Noções básicas de álgebra linear, variância, projeções e decomposição em valores singulares.
- Familiaridade com NumPy, Matplotlib e Scikit-Learn.

## Estrutura do Capítulo

### Notebooks

| Experimento | Descrição | Dificuldade |
|-------------|-----------|------------|
| `08_dimensionality_reduction.ipynb` | Fluxo de redução de dimensionalidade: PCA, componentes principais, projeção, uso do Scikit-Learn, variância explicada, escolha do número de dimensões, compressão, PCA randomizado, PCA incremental, projeção aleatória, LLE e Kernel PCA. | Intermediário |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 08 do livro, com atenção à intuição geométrica de PCA.
2. **Prática**:
   - Execute o notebook `08_dimensionality_reduction.ipynb` em ordem.
   - Observe como PCA projeta dados 3D em 2D.
   - Compare variância explicada e perda de informação.
   - Use PCA para compressão e reconstrução.
   - Compare PCA randomizado, incremental, projeção aleatória e LLE.
3. **Reflexão**:
   - Quando redução de dimensionalidade ajuda e quando pode atrapalhar?
   - Como escolher o número de dimensões?
   - Qual a diferença entre técnicas lineares e não lineares?

## Como Executar os Notebooks

```bash
source ../.venv/bin/activate
jupyter lab
```

Se estiver usando o shell Fish:

```fish
source ../.venv/bin/activate.fish
```

## Resultados Esperados

- ✅ Aplicar PCA manualmente e com Scikit-Learn.
- ✅ Interpretar componentes principais e variância explicada.
- ✅ Escolher número de dimensões com base na variância preservada.
- ✅ Usar PCA para compressão e reconstrução.
- ✅ Entender PCA incremental, PCA randomizado, projeção aleatória, LLE e Kernel PCA.

## Exercícios

- **Perguntas do Capítulo 8**: as soluções finais foram deixadas fora do notebook principal e serão organizadas em `Respostas.md`.

## Status de Conclusão

- [ ] Conceitos fundamentais revisados.
- [x] Notebook principal estruturado até Kernel PCA.
- [ ] Exercícios completos.

**Última atualização**: Maio de 2026
