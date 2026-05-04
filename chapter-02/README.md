# Capítulo 02: Projeto de Aprendizado de Máquina de Ponta a Ponta

## Objetivo

Aplicar um fluxo completo de aprendizado de máquina, desde a obtenção dos dados até a avaliação final e persistência do modelo, usando o conjunto de dados imobiliários California Housing Prices.

## Pré-requisitos

- Conceitos do Capítulo 01: tipos de aprendizado de máquina, sobreajuste, subajuste e avaliação de modelos.
- Familiaridade com Pandas, NumPy, Scikit-Learn e Matplotlib.
- Jupyter Lab com ambiente Python adequado ativado.

## Estrutura do Capítulo

### Notebooks

| Experimento | Descrição | Dificuldade |
|-------------|-----------|------------|
| `02_Projeto_End_to_End_de_Machine_Learning.ipynb` | Fluxo fim a fim: configuração, download dos dados, análise exploratória, criação do conjunto de teste, limpeza, atributos categóricos, escalonamento, transformadores personalizados, encadeamentos de transformação, treinamento, validação cruzada, busca em grade, busca aleatória, avaliação no teste e persistência com `joblib`. | Intermediário |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 02 do livro (Project Checklist).
2. **Prática**:
   - Acompanhe e execute o notebook `02_Projeto_End_to_End_de_Machine_Learning.ipynb`.
   - Entenda a criação do conjunto de teste e a amostragem estratificada por categoria de renda.
   - Analise os transformadores personalizados e os encadeamentos de pré-processamento.
   - Compare os resultados de Regressão Linear, Árvore de Decisão e Floresta Aleatória.
   - Observe a diferença entre erro de treino, erro de validação cruzada e erro final no conjunto de teste.
3. **Reflexão**:
   - Como os encadeamentos ajudam a evitar vazamento de dados?
   - Qual a diferença entre busca em grade e busca aleatória?
   - Por que o conjunto de teste só deve ser usado no final?

## Como Executar os Notebooks

```bash
# Ativar ambiente
source ../.venv/bin/activate

# Iniciar Jupyter Lab
jupyter lab
```

Se estiver usando o shell Fish, ative o ambiente com:

```fish
source ../.venv/bin/activate.fish
```

## Resultados Esperados

Após completar este capítulo, você deverá ser capaz de:

- ✅ Realizar análise exploratória de dados (EDA) focada em Machine Learning.
- ✅ Criar um conjunto de teste com amostragem estratificada.
- ✅ Tratar dados ausentes, valores atípicos e criar novos atributos.
- ✅ Criar encadeamentos do Scikit-Learn para padronizar transformações.
- ✅ Treinar, avaliar e otimizar múltiplos modelos com `GridSearchCV` e `RandomizedSearchCV`.
- ✅ Avaliar o modelo final no conjunto de teste e salvá-lo com `joblib`.

## Exercícios

- **Perguntas do Capítulo 2**: as respostas e os exercícios finais foram deixados fora do notebook principal e estão sendo estruturados em `Respostas.md`.

## Status de Conclusão

- [ ] Conceitos fundamentais revisados.
- [x] Notebook principal estruturado até a persistência do modelo.
- [ ] Exercícios completos.

**Última atualização**: Maio de 2026
