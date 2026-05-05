# Capítulo 07: Aprendizado por Ensemble e Florestas Aleatórias

## Objetivo

Entender como combinar múltiplos modelos para melhorar desempenho e estabilidade, cobrindo votação, bagging, pasting, avaliação out-of-bag, Random Forests, importância de atributos, boosting, gradient boosting e stacking.

## Pré-requisitos

- Conceitos dos Capítulos 01 a 06: classificação, regressão, validação, árvores de decisão e sobreajuste.
- Familiaridade com Scikit-Learn, NumPy e Matplotlib.

## Estrutura do Capítulo

### Notebooks

| Experimento | Descrição | Dificuldade |
|-------------|-----------|------------|
| `07_ensemble_learning_and_random_forests.ipynb` | Fluxo de ensembles: classificadores por votação, bagging, pasting, avaliação out-of-bag, Random Forests, importância de atributos, AdaBoost, Gradient Boosting, HistGradientBoosting e stacking. | Intermediário |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 07 do livro, com atenção a variância, diversidade de modelos e agregação.
2. **Prática**:
   - Execute o notebook `07_ensemble_learning_and_random_forests.ipynb` em ordem.
   - Compare votação rígida e votação suave.
   - Observe como bagging estabiliza árvores de decisão.
   - Use out-of-bag como estimativa interna de validação.
   - Compare Random Forests, AdaBoost, Gradient Boosting e Stacking.
3. **Reflexão**:
   - Por que ensembles reduzem variância?
   - Quando votação suave tende a superar votação rígida?
   - Como boosting difere de bagging?
   - Qual o papel do estimador final em stacking?

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

- ✅ Combinar modelos com votação rígida e suave.
- ✅ Treinar ensembles com bagging e pasting.
- ✅ Usar avaliação out-of-bag.
- ✅ Treinar Random Forests e interpretar importância de atributos.
- ✅ Entender AdaBoost, Gradient Boosting e Stacking.

## Exercícios

- **Perguntas do Capítulo 7**: as soluções finais foram deixadas fora do notebook principal e serão organizadas em `Respostas.md`.

## Status de Conclusão

- [ ] Conceitos fundamentais revisados.
- [x] Notebook principal estruturado até stacking.
- [ ] Exercícios completos.

**Última atualização**: Maio de 2026
