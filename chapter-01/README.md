# Chapter 01: The Machine Learning Landscape

## Objetivo

Compreender os fundamentos de Machine Learning, tipos de sistemas e arquiteturas, e preparar o caminho para modelos práticos nos capítulos seguintes.

## Pré-requisitos

- Conceitos básicos de Python 3.12+
- Jupyter Lab instalado
- Ambiente `.venv` ativado com `requirements.txt` instalado

## Estrutura do Capítulo

### Notebooks

| Experimento | Descrição | Dificuldade |
|-------------|-----------|------------|
| `exp-01-linear-regression.ipynb` | Regressão Linear e K-Nearest Neighbors com dados reais (Life Satisfaction) | Iniciante |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 01 do livro (seções 1-4)
   - Machine Learning types (Supervised, Unsupervised, Reinforcement)
   - Main challenges (overfitting, underfitting, data quality)

2. **Prática**:
   - Abra `exp-01-linear-regression.ipynb`
   - Execute célula por célula
   - Experimente variar `n_neighbors` no KNeighborsRegressor

3. **Reflexão**:
   - Por que a regressão linear é diferente de KNN?
   - Quando usar cada modelo?
   - Como validar qual é melhor?

## Como Executar os Notebooks

```bash
# Ativar ambiente
source .venv/bin/activate.fish

# Iniciar Jupyter Lab
jupyter lab

# Abrir os notebooks em chapter-01/
```

### Kernel Correto

Certifique-se de que o kernel selecionado é **Python (.venv modelos-handson)** (canto superior direito do notebook).

## Resultados Esperados

Após completar este capítulo, você deverá:

- ✅ Diferenciar tipos de sistemas de ML (Supervised, Unsupervised, Semi-supervised, Reinforcement)
- ✅ Entender overfitting e underfitting
- ✅ Treinar e fazer predições com modelos simples (Linear Regression, KNN)
- ✅ Visualizar dados e resultados com Matplotlib/Pandas

## Exercícios

- **Perguntas do Capítulo 1**: Todas as perguntas e respostas estão documentadas em [Respostas.md](Respostas.md). O arquivo foi organizado em um formato interativo de **Flashcards** (expansível). Nele, você encontrará suas respostas corrigidas e aprofundadas (com exemplos e palavras-chave), além das respostas oficiais do autor do livro. É uma excelente ferramenta de revisão e consulta rápida.

## Recursos Adicionais

- [Documentação scikit-learn: Linear Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
- [Documentação scikit-learn: K-Neighbors](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsRegressor.html)
- Capítulo 01 do livro Hands-On ML

## Status de Conclusão

- [x] Conceitos fundamentais cobertos
- [x] Primeiro experimento implementado
- [x] Todos os exercícios completos
- [ ] Todos os notebooks do capítulo finalizados

**Última atualização**: 2 de maio de 2026