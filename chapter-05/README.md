# Capítulo 05: Máquinas de Vetores de Suporte

## Objetivo

Compreender Support Vector Machines para classificação e regressão. O capítulo cobre margem larga, margem suave, sensibilidade à escala, kernels polinomiais, kernel RBF, atributos de similaridade, regressão com SVM e a intuição geométrica por trás do modelo.

## Pré-requisitos

- Conceitos dos Capítulos 01 a 04: treino/teste, validação, escalonamento, classificação, regressão, regularização e otimização.
- Noções básicas de vetores, produto escalar, distância e margens.
- Familiaridade com NumPy, Matplotlib e Scikit-Learn.
- Entendimento de `Pipeline`, `StandardScaler`, validação cruzada e busca de hiperparâmetros.

## Estrutura do Capítulo

```text
chapter-05/
├── 05_support_vector_machines.ipynb
├── 05_exercicio_9.ipynb
├── 05_exercicio_10.ipynb
├── 05_exercicio_11.ipynb
├── README.md
├── Respostas.md
└── images/
    └── svm/
```

## Notebooks

| Arquivo | Tema | Conteúdo principal | Status |
|---|---|---|---|
| `05_support_vector_machines.ipynb` | SVMs para classificação e regressão | Classificação linear, margem suave, SVM não linear, kernel polinomial, atributos de similaridade, kernel RBF, regressão com SVM, visualização do funcionamento interno e implementação didática com descida do gradiente em lote. | Estruturado |
| `05_exercicio_9.ipynb` | Comparação de SVMs lineares | Comparação entre `LinearSVC`, `SVC(kernel="linear")` e `SGDClassifier` em um problema linearmente separável do Iris. | Implementado |
| `05_exercicio_10.ipynb` | Classificação Wine | Classificação do conjunto Wine com SVMs lineares, escalonamento e visualização em 2D com PCA. | Implementado |
| `05_exercicio_11.ipynb` | Regressão California Housing | Ajuste de um regressor `SVR` com kernel RBF no California Housing, usando `RandomizedSearchCV` em uma amostra do treino e avaliação por RMSE. | Implementado |

## Datasets e Arquivos Auxiliares

### Iris

Usado no notebook principal e no exercício 9 para demonstrar classificadores SVM lineares em um problema separável.

### Moons

Usado no notebook principal para visualizar fronteiras não lineares com atributos polinomiais, kernel polinomial e kernel RBF.

### Wine

Usado no exercício 10. O dataset contém 178 amostras de vinho, 13 atributos químicos e 3 classes de cultivadores.

### California Housing

Usado no exercício 11 para regressão com `SVR`. Como o dataset possui mais de 20.000 instâncias, a busca de hiperparâmetros é feita em uma amostra menor do treino.

## Imagens Geradas

Local: `images/svm/`

O diretório contém 13 figuras usadas ou geradas no estudo:

- classificação de margem larga;
- sensibilidade a outliers e escalonamento;
- comparação entre margens pequenas e grandes;
- visualizações de kernels e dimensões superiores;
- classificadores SVM polinomiais e RBF no dataset moons;
- regularização;
- função hinge;
- regressão com SVM.

## Roteiro de Estudo Recomendado

1. Execute `05_support_vector_machines.ipynb` em ordem.
2. Observe como o escalonamento altera a fronteira de decisão da SVM.
3. Compare o efeito dos hiperparâmetros `C`, `gamma`, `degree` e `epsilon`.
4. Entenda quando usar `LinearSVC`, `SVC`, `LinearSVR` e `SVR`.
5. Execute `05_exercicio_9.ipynb` para comparar implementações lineares de SVM.
6. Execute `05_exercicio_10.ipynb` para praticar classificação multiclasse com SVMs no Wine.
7. Execute `05_exercicio_11.ipynb` para ajustar um `SVR` com busca de hiperparâmetros.

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

- Treinar SVMs lineares e não lineares.
- Interpretar margem, vetores de suporte e margem suave.
- Explicar por que SVMs são sensíveis ao escalonamento.
- Usar kernels polinomial e RBF.
- Ajustar hiperparâmetros como `C`, `gamma`, `degree` e `epsilon`.
- Aplicar SVMs em regressão.
- Comparar `LinearSVC`, `SVC(kernel="linear")` e `SGDClassifier`.
- Usar `Pipeline` com `StandardScaler`.
- Aplicar busca de hiperparâmetros com `RandomizedSearchCV`.

## Exercícios

As perguntas e respostas do capítulo estão organizadas em `Respostas.md`.

Status atual:

- Perguntas 1 a 8: respostas conceituais revisadas e traduzidas.
- Exercício 9: comparação entre três classificadores SVM lineares.
- Exercício 10: classificação do conjunto Wine com SVMs.
- Exercício 11: ajuste de `SVR` no California Housing e avaliação por RMSE.

## Status de Conclusão

- [x] Notebook principal estruturado.
- [x] Respostas conceituais revisadas.
- [x] Exercício 9 implementado.
- [x] Exercício 10 implementado.
- [x] Exercício 11 implementado.
- [x] Escalonamento, validação cruzada e busca de hiperparâmetros aplicados nos exercícios práticos.

**Última atualização**: 23 de maio de 2026
