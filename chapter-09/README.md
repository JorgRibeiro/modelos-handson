# Capítulo 09: Aprendizado Não Supervisionado

## Objetivo

Aprender técnicas para encontrar estrutura em dados sem rótulos, cobrindo clustering, K-Means, segmentação de imagens, aprendizado semissupervisionado, DBSCAN, outros algoritmos de clustering, misturas Gaussianas, detecção de anomalias e modelos Bayesianos.

## Pré-requisitos

- Conceitos dos Capítulos 01 a 08: classificação, regressão, validação, redução de dimensionalidade e métricas.
- Familiaridade com NumPy, Matplotlib, Scikit-Learn e noções básicas de probabilidade.

## Estrutura do Capítulo

### Notebooks

| Experimento | Descrição | Dificuldade |
|-------------|-----------|------------|
| `09_unsupervised_learning.ipynb` | Fluxo de aprendizado não supervisionado: clustering, K-Means, inércia, múltiplas inicializações, Mini-Batch K-Means, escolha do número de clusters, segmentação de imagens, aprendizado semissupervisionado, DBSCAN, clustering espectral e aglomerativo, misturas Gaussianas, detecção de anomalias, BIC/AIC e Bayesian Gaussian Mixture Models. | Intermediário |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 09 do livro, com atenção às diferenças entre clustering, detecção de anomalias e modelos generativos.
2. **Prática**:
   - Execute o notebook `09_unsupervised_learning.ipynb` em ordem.
   - Compare clustering rígido e suave.
   - Analise inércia, método do cotovelo e silhueta.
   - Use clustering para segmentação de imagem e aprendizado semissupervisionado.
   - Compare K-Means, DBSCAN, clustering espectral, aglomerativo e misturas Gaussianas.
   - Observe como BIC/AIC ajudam a escolher o número de componentes.
3. **Reflexão**:
   - Por que clustering é difícil de avaliar sem rótulos?
   - Quando K-Means falha?
   - Como misturas Gaussianas podem ser usadas para detecção de anomalias?
   - Qual a vantagem de `BayesianGaussianMixture`?

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

- ✅ Treinar e interpretar K-Means e Mini-Batch K-Means.
- ✅ Usar inércia, cotovelo e silhueta para avaliar clusters.
- ✅ Aplicar clustering em segmentação de imagens e aprendizado semissupervisionado.
- ✅ Usar DBSCAN, clustering espectral e aglomerativo.
- ✅ Treinar misturas Gaussianas e usá-las para clustering suave e detecção de anomalias.
- ✅ Selecionar número de clusters com BIC/AIC e entender misturas Gaussianas Bayesianas.

## Exercícios

- **Perguntas do Capítulo 9**: as soluções finais foram deixadas fora do notebook principal e serão organizadas em `Respostas.md`.

## Status de Conclusão

- [ ] Conceitos fundamentais revisados.
- [x] Notebook principal estruturado até Bayesian Gaussian Mixture Models.
- [ ] Exercícios completos.

**Última atualização**: Maio de 2026
