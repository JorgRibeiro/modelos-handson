# Capítulo 07: Aprendizado por Ensemble e Florestas Aleatórias

## Objetivo

Entender como combinar vários modelos para obter previsões mais robustas e, em alguns casos, mais precisas do que as de um único estimador. O capítulo cobre classificadores por votação, bagging, pasting, avaliação out-of-bag, Florestas Aleatórias, importância de atributos, boosting, Gradient Boosting, HistGradientBoosting e stacking.

## Pré-requisitos

- Conceitos dos Capítulos 01 a 06: classificação, regressão, validação, sobreajuste, regularização e Árvores de Decisão.
- Entendimento de divisão treino/validação/teste, validação cruzada e avaliação em conjunto de teste.
- Familiaridade com NumPy, Pandas, Matplotlib e Scikit-Learn.
- Noções de estimadores, pipelines, probabilidades de classe e métricas como acurácia.

## Estrutura do Capítulo

```text
chapter-07/
├── 07_ensemble_learning_and_random_forests.ipynb
├── 07_exercicio_8_9.ipynb
├── README.md
├── Respostas.md
├── datasets/
│   ├── housing.tgz
│   └── housing/
│       └── housing.csv
└── images/
    └── ensembles/
```

## Notebooks

| Arquivo | Tema | Conteúdo principal | Status |
|---|---|---|---|
| `07_ensemble_learning_and_random_forests.ipynb` | Ensembles e Florestas Aleatórias | Classificadores por votação, bagging, pasting, avaliação OOB, Random Forests, importância de atributos, AdaBoost, Gradient Boosting, HistGradientBoosting e stacking. | Estruturado |
| `07_exercicio_8_9.ipynb` | Exercícios 8 e 9 | MNIST dividido em treino, validação e teste; comparação entre classificadores individuais, `VotingClassifier`, stacking manual e `StackingClassifier`. | Implementado |

## Datasets e Arquivos Auxiliares

### Moons

Usado no notebook principal para comparar classificadores individuais com ensembles por votação, além de demonstrar bagging e pasting com Árvores de Decisão.

### Iris

Usado para treinar uma Floresta Aleatória e visualizar a importância de atributos.

### MNIST

Usado no notebook principal para demonstrar importância de pixels em uma Floresta Aleatória e no notebook `07_exercicio_8_9.ipynb` para os exercícios práticos de votação e stacking.

### Housing

Local: `datasets/housing/`

Usado na seção de `HistGradientBoostingRegressor`, com pré-processamento de atributos categóricos e avaliação por validação cruzada.

## Imagens Geradas

Local: `images/ensembles/`

O diretório contém figuras usadas ou geradas no estudo:

- lei dos grandes números;
- comparação entre Árvore de Decisão isolada e Bagging;
- importância dos pixels do MNIST;
- comportamento do AdaBoost;
- Gradient Boosting;
- efeito da taxa de aprendizado no Gradient Boosting.

## Roteiro de Estudo Recomendado

1. Execute `07_ensemble_learning_and_random_forests.ipynb` em ordem.
2. Compare votação rígida e votação suave em classificadores diferentes.
3. Observe como bagging reduz a variância de Árvores de Decisão.
4. Compare avaliação OOB com avaliação em conjunto de teste.
5. Treine Florestas Aleatórias e interprete importâncias de atributos.
6. Compare AdaBoost, Gradient Boosting e HistGradientBoosting.
7. Estude a seção de stacking no notebook principal.
8. Execute `07_exercicio_8_9.ipynb` para praticar votação e stacking no MNIST.
9. Compare os resultados do `VotingClassifier`, do stacking manual e do `StackingClassifier`.

## Como Executar os Notebooks

Entre no diretório do projeto:

```bash
cd modelos-handson
```

Ative o ambiente:

```bash
source .venv/bin/activate
```

Se estiver usando Fish:

```fish
source .venv/bin/activate.fish
```

Inicie o Jupyter:

```bash
jupyter lab
```

## Resultados Esperados

Ao concluir este capítulo, você deverá ser capaz de:

- Combinar modelos com votação rígida e votação suave.
- Explicar por que ensembles funcionam melhor quando os modelos são diversos.
- Treinar ensembles com bagging e pasting.
- Usar avaliação out-of-bag como estimativa interna de desempenho.
- Treinar Florestas Aleatórias e interpretar importâncias de atributos.
- Diferenciar bagging, pasting, boosting e stacking.
- Treinar modelos com AdaBoost, Gradient Boosting e HistGradientBoosting.
- Construir manualmente um ensemble de stacking usando predições de validação.
- Usar `StackingClassifier` para combinar estimadores de base com um estimador final.

## Exercícios

As perguntas e respostas do capítulo estão organizadas em `Respostas.md`.

Status atual:

- Perguntas 1 a 7: respostas conceituais revisadas, corrigidas e traduzidas.
- Exercício 8: MNIST dividido em treino, validação e teste; treino de `RandomForestClassifier`, `ExtraTreesClassifier`, `LogisticRegression` e comparação com `VotingClassifier`.
- Exercício 9: stacking manual com predições no conjunto de validação e comparação com `StackingClassifier`.

Resultados obtidos no notebook `07_exercicio_8_9.ipynb`:

| Modelo | Acurácia no teste |
|---|---:|
| `RandomForestClassifier` | 0.9657 |
| `ExtraTreesClassifier` | 0.9706 |
| `LogisticRegression` | 0.9149 |
| `VotingClassifier` | 0.9501 |
| Stacking manual | 0.9679 |
| `StackingClassifier` | 0.9720 |

## Status de Conclusão

- [x] Notebook principal estruturado até stacking.
- [x] Respostas conceituais revisadas.
- [x] Exercício 8 implementado com votação no MNIST.
- [x] Exercício 9 implementado com stacking manual e `StackingClassifier`.
- [x] Comparação entre classificadores individuais, votação e stacking registrada.

**Última atualização**: 29 de maio de 2026
