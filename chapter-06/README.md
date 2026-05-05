# Capítulo 06: Árvores de Decisão

## Objetivo

Aprender como árvores de decisão são treinadas, visualizadas e regularizadas, além de entender como elas fazem previsões, estimam probabilidades, resolvem regressão e por que apresentam alta variância.

## Pré-requisitos

- Conceitos dos Capítulos 01 a 05: classificação, regressão, validação e sobreajuste.
- Noções básicas de impureza, probabilidade e visualização de modelos.
- Familiaridade com NumPy, Matplotlib, Scikit-Learn e Graphviz.

## Estrutura do Capítulo

### Notebooks

| Experimento | Descrição | Dificuldade |
|-------------|-----------|------------|
| `06_decision_trees.ipynb` | Fluxo com árvores de decisão: treino e visualização, previsões, probabilidades, regularização, regressão, sensibilidade à orientação dos eixos, alta variância e acesso à estrutura interna da árvore. | Intermediário |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 06 do livro, com atenção a divisões, impureza e regularização.
2. **Prática**:
   - Execute o notebook `06_decision_trees.ipynb` em ordem.
   - Visualize a árvore do Iris com Graphviz.
   - Compare árvores sem restrição e árvores regularizadas.
   - Observe como rotação dos dados afeta fronteiras de decisão.
   - Inspecione o atributo `tree_` para entender a estrutura interna.
3. **Reflexão**:
   - Por que árvores são interpretáveis, mas instáveis?
   - Como `max_depth` e `min_samples_leaf` reduzem sobreajuste?
   - Por que Random Forests ajudam a controlar alta variância?

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

- ✅ Treinar árvores de decisão para classificação e regressão.
- ✅ Visualizar e interpretar árvores treinadas.
- ✅ Estimar probabilidades de classe em folhas.
- ✅ Controlar sobreajuste com hiperparâmetros de regularização.
- ✅ Entender sensibilidade à orientação dos eixos e alta variância.

## Exercícios

- **Perguntas do Capítulo 6**: as soluções finais foram deixadas fora do notebook principal e serão organizadas em `Respostas.md`.

## Status de Conclusão

- [ ] Conceitos fundamentais revisados.
- [x] Notebook principal estruturado até o material extra de estrutura interna da árvore.
- [ ] Exercícios completos.

**Última atualização**: Maio de 2026
