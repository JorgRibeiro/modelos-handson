# Capítulo 06: Árvores de Decisão

## Objetivo

Aprender como Árvores de Decisão são treinadas, visualizadas e regularizadas. O capítulo cobre previsões, estimativas de probabilidade, regressão com árvores, sensibilidade à orientação dos dados, alta variância e a intuição por trás de florestas baseadas em votação.

## Pré-requisitos

- Conceitos dos Capítulos 01 a 05: classificação, regressão, validação, sobreajuste, regularização e ajuste de hiperparâmetros.
- Noções básicas de impureza, probabilidade, entropia, variância e visualização de modelos.
- Familiaridade com NumPy, Matplotlib, Scikit-Learn e Graphviz.
- Entendimento de `GridSearchCV`, validação cruzada e avaliação em conjunto de teste.

## Estrutura do Capítulo

```text
chapter-06/
├── 06_decision_trees.ipynb
├── 06_exercicio_7.ipynb
├── 06_exercicio_8.ipynb
├── README.md
├── Respostas.md
└── images/
    └── decision_trees/
```

## Notebooks

| Arquivo | Tema | Conteúdo principal | Status |
|---|---|---|---|
| `06_decision_trees.ipynb` | Árvores de Decisão | Treino e visualização, previsões, probabilidades por folha, regularização, regressão, sensibilidade à rotação dos dados, alta variância e acesso à estrutura interna da árvore. | Estruturado |
| `06_exercicio_7.ipynb` | Ajuste no conjunto moons | Treino e ajuste de uma Árvore de Decisão com `GridSearchCV`, validação cruzada, avaliação no teste e comparação com uma árvore sem ajuste. | Implementado |
| `06_exercicio_8.ipynb` | Floresta manual | Geração de 1000 subconjuntos com `ShuffleSplit`, treino de 1000 árvores, avaliação individual e combinação das previsões por voto majoritário. | Implementado |

## Datasets e Arquivos Auxiliares

### Iris

Usado no notebook principal para treinar e visualizar uma Árvore de Decisão simples, além de interpretar nós, folhas, impureza de Gini e probabilidades por classe.

### Moons

Usado nos exercícios 7 e 8 para ajustar uma árvore com validação cruzada e construir manualmente uma floresta por votação majoritária.

### Dados Sintéticos de Regressão

Usados no notebook principal para demonstrar regressão com Árvores de Decisão, regularização e comportamento por regiões constantes.

### Arquivos `.dot`

Local: `images/decision_trees/`

| Arquivo | Uso |
|---|---|
| `iris_tree.dot` | Representação exportada da árvore treinada no Iris. |
| `regression_tree.dot` | Representação exportada da árvore usada em regressão. |

## Imagens Geradas

Local: `images/decision_trees/`

O diretório contém figuras e arquivos auxiliares usados ou gerados no estudo:

- fronteiras de decisão de árvores;
- árvore com alta variância;
- efeito de `min_samples_leaf`;
- pré-processamento com PCA;
- sensibilidade à rotação dos dados;
- regressão com árvores;
- regularização em regressão;
- arquivos `.dot` para visualização com Graphviz.

## Roteiro de Estudo Recomendado

1. Execute `06_decision_trees.ipynb` em ordem.
2. Visualize a árvore do Iris com Graphviz.
3. Compare árvores sem restrição e árvores regularizadas.
4. Observe como rotação dos dados afeta fronteiras de decisão.
5. Inspecione o atributo `tree_` para entender a estrutura interna.
6. Execute `06_exercicio_7.ipynb` para praticar ajuste de hiperparâmetros com validação cruzada.
7. Execute `06_exercicio_8.ipynb` para entender, passo a passo, a ideia por trás de uma Floresta Aleatória.

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

- Treinar Árvores de Decisão para classificação e regressão.
- Visualizar e interpretar árvores treinadas.
- Explicar impureza de Gini e probabilidades estimadas em folhas.
- Controlar sobreajuste com hiperparâmetros como `max_depth`, `max_leaf_nodes` e `min_samples_leaf`.
- Entender sensibilidade à orientação dos eixos e alta variância.
- Usar `GridSearchCV` para ajustar `DecisionTreeClassifier`.
- Combinar várias árvores por voto majoritário para reduzir variância.
- Relacionar a floresta manual do exercício 8 à ideia de Random Forests.

## Exercícios

As perguntas e respostas do capítulo estão organizadas em `Respostas.md`.

Status atual:

- Perguntas 1 a 6: respostas conceituais revisadas, corrigidas e traduzidas.
- Exercício 7: Árvore de Decisão ajustada no conjunto moons com acurácia próxima de 85,5%.
- Exercício 8: floresta manual com 1000 árvores, voto majoritário e acurácia final próxima de 86,0%.

## Status de Conclusão

- [x] Notebook principal estruturado.
- [x] Respostas conceituais revisadas.
- [x] Exercício 7 implementado.
- [x] Exercício 8 implementado.
- [x] `GridSearchCV`, `ShuffleSplit`, avaliação no teste e voto majoritário aplicados nos exercícios práticos.

**Última atualização**: 23 de maio de 2026
