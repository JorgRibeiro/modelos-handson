# Capítulo 04: Treinando Modelos

## Objetivo

Entender como modelos lineares são treinados e otimizados. O capítulo cobre regressão linear, Equação Normal, descida do gradiente em lote, estocástica e em mini-lotes, regressão polinomial, curvas de aprendizado, regularização, parada antecipada, regressão logística e regressão Softmax.

## Pré-requisitos

- Conceitos dos Capítulos 01 a 03: treino/teste, validação, sobreajuste, subajuste, métricas e classificação.
- Noções básicas de álgebra linear, derivadas, funções de custo e otimização.
- Familiaridade com NumPy, Matplotlib e Scikit-Learn.
- Entendimento básico de validação cruzada e interpretação de curvas de aprendizado ajuda nos exercícios.

## Estrutura do Capítulo

```text
chapter-04/
├── 04_training_linear_models.ipynb
├── 04_exercicio12.ipynb
├── README.md
├── Respostas.md
└── images/
    └── training_linear_models/
```

## Notebooks

| Arquivo | Tema | Conteúdo principal | Status |
|---|---|---|---|
| `04_training_linear_models.ipynb` | Treinamento de modelos lineares | Equação Normal, descida do gradiente em lote, estocástica e em mini-lotes, regressão polinomial, curvas de aprendizado, Ridge, Lasso, Elastic Net, parada antecipada, regressão logística, fronteiras de decisão e regressão Softmax. | Estruturado |
| `04_exercicio12.ipynb` | Softmax do zero | Implementação manual de regressão Softmax com NumPy, incluindo one-hot encoding, escalonamento, entropia cruzada, regularização L2, descida do gradiente em lote e parada antecipada. | Implementado |

## Datasets e Arquivos Auxiliares

### Dados Sintéticos

O notebook principal gera dados sintéticos para regressão linear, regressão polinomial, curvas de aprendizado e comparação de métodos de otimização.

### Iris

Usado nas seções de regressão logística, regressão Softmax e no exercício 12. O capítulo usa atributos das pétalas para visualizar fronteiras de decisão e implementar um classificador Softmax manualmente.

## Imagens Geradas

Local: `images/training_linear_models/`

O diretório contém 18 figuras usadas ou geradas no estudo:

- dados sintéticos e previsões de regressão linear;
- trajetórias de descida do gradiente;
- comparação entre regressão linear e polinomial;
- curvas de aprendizado para subajuste e sobreajuste;
- regularização Ridge, Lasso e Elastic Net;
- parada antecipada;
- função logística e fronteiras de decisão;
- contornos da regressão Softmax.

## Roteiro de Estudo Recomendado

1. Execute `04_training_linear_models.ipynb` em ordem.
2. Compare a solução direta da Equação Normal com métodos iterativos de descida do gradiente.
3. Observe como regressão polinomial permite ajustar relações não lineares.
4. Use curvas de aprendizado para identificar subajuste e sobreajuste.
5. Compare Ridge, Lasso e Elastic Net para entender o efeito de cada regularização.
6. Estude parada antecipada como forma prática de regularização.
7. Entenda como regressão logística e Softmax transformam modelos lineares em classificadores.
8. Execute `04_exercicio12.ipynb` para implementar o treinamento da regressão Softmax manualmente com NumPy.

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

- Treinar regressão linear pela Equação Normal e por descida do gradiente.
- Diferenciar descida do gradiente em lote, estocástica e em mini-lotes.
- Criar atributos polinomiais para modelar relações não lineares.
- Interpretar curvas de aprendizado para diagnosticar subajuste e sobreajuste.
- Aplicar regularização com Ridge, Lasso e Elastic Net.
- Usar parada antecipada para controlar sobreajuste.
- Treinar classificadores com regressão logística e regressão Softmax.
- Implementar Softmax manualmente com NumPy.
- Calcular entropia cruzada e gradientes de forma vetorizada.

## Exercícios

As perguntas e respostas do capítulo estão organizadas em `Respostas.md`.

Status atual:

- Perguntas 1 a 11: respostas conceituais revisadas e traduzidas.
- Exercício 12: regressão Softmax implementada do zero em `04_exercicio12.ipynb`.
- Resumo textual do exercício 12 em `Respostas.md`: ainda pendente de revisão final.

## Status de Conclusão

- [x] Notebook principal estruturado.
- [x] Conceitos de otimização, regularização e classificação linear revisados.
- [x] Exercício 12 implementado com NumPy.
- [x] Parada antecipada aplicada no exercício prático.
- [ ] Revisar e completar o resumo textual do exercício 12 em `Respostas.md`.

**Última atualização**: 23 de maio de 2026
