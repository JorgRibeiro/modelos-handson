# Capítulo 03: Classificação

## Objetivo

Estudar problemas de classificação usando o MNIST como base principal e exercícios aplicados com Titanic e detecção de Spam/Ham. O capítulo cobre classificação binária, multiclasse, multirrótulo e multioutput, além de métricas fundamentais como acurácia, matriz de confusão, precisão, revocação, F1, curva precisão-revocação e ROC.

## Pré-requisitos

- Conceitos dos Capítulos 01 e 02: treino/teste, validação, sobreajuste, subajuste e pipelines de pré-processamento.
- Familiaridade com NumPy, Pandas, Matplotlib e Scikit-Learn.
- Noções de validação cruzada, busca de hiperparâmetros e interpretação de métricas.
- Conhecimento básico sobre dados tabulares e texto bruto ajuda nos exercícios Titanic e Spam/Ham.

## Estrutura do Capítulo

```text
chapter-03/
├── 03_classification_pt.ipynb
├── 03_classification_pt.ipynb.bak
├── README.md
├── Respostas.md
├── exercicios/
│   ├── 03_exercicio1.ipynb
│   ├── 03_exercicio2.ipynb
│   ├── 03_exercicio3.ipynb
│   ├── 03_exercicio4.ipynb
│   ├── titanic/
│   │   ├── train.csv
│   │   ├── test.csv
│   │   └── gender_submission.csv
│   └── emails/
│       ├── easy_ham/
│       ├── easy_ham_2/
│       ├── hard_ham/
│       ├── spam_1/
│       ├── spam_2/
│       └── spam_3/
└── images/
    └── classification/
```

## Notebooks

| Arquivo | Tema | Conteúdo principal | Status |
|---|---|---|---|
| `03_classification_pt.ipynb` | Classificação com MNIST | Classificador binário para o dígito 5, validação cruzada, matriz de confusão, precisão, revocação, F1, curvas PR/ROC, classificação multiclasse, análise de erros, classificação multirrótulo e multioutput. | Estruturado |
| `exercicios/03_exercicio1.ipynb` | Novo classificador para MNIST | Treino de classificador binário e multiclasse, validação cruzada, `GridSearchCV` e avaliação final. | Implementado |
| `exercicios/03_exercicio2.ipynb` | Aumento de dados | Expansão do treino do MNIST por deslocamentos, validação cruzada e avaliação no teste. | Implementado |
| `exercicios/03_exercicio3.ipynb` | Titanic | Pipeline tabular com atributos numéricos/categóricos, `RandomForestClassifier`, `KNeighborsClassifier`, validação cruzada, `GridSearchCV` e `accuracy_score`. | Implementado |
| `exercicios/03_exercicio4.ipynb` | Detector de Spam/Ham | Pipeline modular para e-mails brutos, parsing de headers/MIME/HTML, features explicáveis, TF-IDF, `LogisticRegression`, validação cruzada, `GridSearchCV`, `accuracy_score`, matriz de confusão e análise de falsos positivos/falsos negativos. | Implementado |

## Datasets e Arquivos Auxiliares

### MNIST

Usado no notebook principal e nos exercícios 1 e 2. O capítulo trabalha com imagens de dígitos para explorar classificação binária, multiclasse, multirrótulo e multioutput.

### Titanic

Local: `exercicios/titanic/`

| Arquivo | Uso |
|---|---|
| `train.csv` | Treino e validação dos modelos. |
| `test.csv` | Base de previsão/submissão. |
| `gender_submission.csv` | Respostas de referência para avaliação local do exercício. |

### SpamAssassin / Spam-Ham

Local: `exercicios/emails/`

| Pasta | Classe | Quantidade de arquivos |
|---|---:|---:|
| `easy_ham/` | Ham | 2551 |
| `easy_ham_2/` | Ham | 1401 |
| `hard_ham/` | Ham difícil | 251 |
| `spam_1/` | Spam | 500 |
| `spam_2/` | Spam | 1398 |
| `spam_3/` | Spam | 501 |

Total identificado em `emails/`: 6603 arquivos brutos de e-mail.

O exercício 4 começa com `easy_ham` e `spam_1` para validar o pipeline, e deixa caminho claro para expandir o treino com `spam_2`, `spam_3`, `easy_ham_2` e `hard_ham`.

## Imagens Geradas

Local: `images/classification/`

O diretório contém 11 figuras usadas ou geradas no estudo do MNIST:

- exemplos de dígitos limpos e ruidosos;
- matrizes de confusão;
- curvas precisão-revocação;
- curva ROC;
- análise de erros;
- exemplos de classificação multioutput.

## Roteiro de Estudo Recomendado

1. Execute `03_classification_pt.ipynb` em ordem.
2. Entenda por que acurácia pode ser enganosa em bases desbalanceadas.
3. Compare matriz de confusão, precisão, revocação, F1, ROC-AUC e curva precisão-revocação.
4. Estude o exercício 1 para reforçar validação cruzada e `GridSearchCV` com MNIST.
5. Use o exercício 2 para observar o impacto de aumento de dados.
6. Use o exercício 3 para praticar pipelines tabulares com Titanic.
7. Use o exercício 4 para praticar classificação de texto e construção de um pipeline completo para Spam/Ham.

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

- Treinar classificadores binários e multiclasse com Scikit-Learn.
- Avaliar classificadores com validação cruzada, matriz de confusão e métricas por classe.
- Interpretar precisão, revocação, F1, ROC-AUC e curvas precisão-revocação.
- Ajustar hiperparâmetros com `GridSearchCV`.
- Criar pipelines para dados tabulares e texto bruto.
- Tratar problemas com classes desbalanceadas.
- Inspecionar falsos positivos e falsos negativos em um detector de Spam/Ham.

## Exercícios

As perguntas e respostas do capítulo estão organizadas em `Respostas.md`.

Status atual:

- Exercício 1: MNIST com novo classificador.
- Exercício 2: aumento de dados no MNIST.
- Exercício 3: Titanic com pipelines e modelos supervisionados.
- Exercício 4: detector de Spam/Ham com pipeline de texto.

## Status de Conclusão

- [x] Notebook principal estruturado.
- [x] Exercícios 1 e 2 com MNIST.
- [x] Exercício 3 com Titanic.
- [x] Exercício 4 com Spam/Ham.
- [x] Validação cruzada, `GridSearchCV` e avaliação final aplicados nos exercícios práticos.
- [ ] Revisar e completar as respostas discursivas em `Respostas.md`.

**Última atualização**: 14 de maio de 2026
