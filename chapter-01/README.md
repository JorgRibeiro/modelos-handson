# Capitulo 01: Panorama do Aprendizado de Maquina

## Objetivo

Compreender o que e aprendizado de maquina, quando ele e util, quais sao os principais tipos de sistemas de ML e quais riscos aparecem ao treinar modelos com dados reais.

O notebook do capitulo usa o exemplo de satisfacao de vida e PIB per capita para mostrar, na pratica, como um modelo aprende parametros, como a escolha da amostra influencia o resultado e por que modelos muito simples ou muito complexos podem falhar.

## Pre-requisitos

- Python 3.12+
- Ambiente `.venv` criado a partir de `requirements.txt`
- Jupyter Lab
- Noções basicas de Python, Pandas, Matplotlib e Scikit-Learn

## Estrutura do Capitulo

### Notebooks e materiais

| Arquivo | Conteudo | Dificuldade |
|---------|----------|-------------|
| `01_Aprendizado_de_Maquina.ipynb` | Notebook principal com configuracao, carga dos dados, visualizacoes, regressao linear, comparacao de modelos, sobreajuste e regularizacao. | Iniciante |
| `Respostas.md` | Perguntas do capitulo em formato de flashcards, com respostas comentadas e respostas do livro. | Revisao |
| `images/fundamentals/` | Figuras geradas pelo notebook para dispersao, ajuste manual, melhor ajuste, sobreajuste e regularizacao. | Apoio |

## Roteiro de Estudo Recomendado

1. **Fundamentos**
   - Entenda a definicao de Machine Learning como sistemas que aprendem com dados.
   - Diferencie aprendizado supervisionado, nao supervisionado, semissupervisionado, auto-supervisionado e por reforco.
   - Revise tarefas comuns: classificacao, regressao, agrupamento, reducao de dimensionalidade e deteccao de anomalias.

2. **Pratica no notebook**
   - Execute `01_Aprendizado_de_Maquina.ipynb` celula por celula.
   - Observe a relacao entre PIB per capita e satisfacao de vida.
   - Compare o ajuste manual dos parametros com o ajuste automatico da `LinearRegression`.
   - Analise como dados ausentes ou uma amostra pouco representativa mudam a conclusao.
   - Veja por que modelos polinomiais muito flexiveis podem sobreajustar.
   - Compare a regressao linear simples com Ridge para entender regularizacao.

3. **Reflexao**
   - O que muda quando o conjunto de treinamento nao representa bem os dados futuros?
   - Por que um modelo que acerta demais o treino pode generalizar mal?
   - Quando faz sentido preferir um modelo mais simples?
   - Qual e a diferenca entre aprender parametros e ajustar hiperparametros?

## Topicos Cobertos

- Definicao de Machine Learning
- Tipos de aprendizado: supervisionado, nao supervisionado, semissupervisionado, auto-supervisionado, online, batch, baseado em instancia e baseado em modelo
- Tarefas comuns de ML: classificacao, regressao, clustering, reducao de dimensionalidade e deteccao de anomalias
- Qualidade e representatividade dos dados
- Sobreajuste e subajuste
- Regularizacao com Ridge
- Visualizacao de dados com Matplotlib
- Modelagem simples com Scikit-Learn

## Como Executar

No diretorio `modelos-handson`, ative o ambiente e abra o Jupyter Lab:

```bash
source .venv/bin/activate
jupyter lab
```

Se estiver usando Fish:

```fish
source .venv/bin/activate.fish
jupyter lab
```

Depois abra:

```text
chapter-01/01_Aprendizado_de_Maquina.ipynb
```

## Resultados Esperados

Ao concluir este capitulo, voce devera ser capaz de:

- Explicar o que e Machine Learning e quando ele e uma boa escolha.
- Diferenciar tarefas supervisionadas, nao supervisionadas e por reforco.
- Identificar problemas de qualidade de dados, amostragem, sobreajuste e subajuste.
- Treinar e interpretar um modelo simples de regressao linear.
- Explicar por que regularizacao ajuda um modelo a generalizar melhor.
- Usar `Respostas.md` como revisao ativa dos conceitos teoricos.

## Exercicios

- As perguntas do Capitulo 1 estao em `Respostas.md`.
- O arquivo esta organizado em flashcards expansivos para revisao rapida.
- Use as respostas para comparar sua explicacao com a resposta do livro e reforcar os conceitos-chave.

## Status de Conclusao

- [x] Notebook principal revisado.
- [x] Figuras principais geradas e salvas em `images/fundamentals/`.
- [x] Perguntas do capitulo documentadas em `Respostas.md`.
- [x] README atualizado com a estrutura real do capitulo.

**Ultima atualizacao**: 7 de maio de 2026
