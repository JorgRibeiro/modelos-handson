# Capítulo 04: Treinando Modelos

## Objetivo

Entender como modelos lineares são treinados e otimizados, cobrindo regressão linear, descida do gradiente, regressão polinomial, curvas de aprendizado, regularização, parada antecipada, regressão logística e regressão Softmax.

## Pré-requisitos

- Conceitos dos Capítulos 01 a 03: treino/teste, validação, sobreajuste, métricas e classificação.
- Noções básicas de álgebra linear, derivadas e otimização.
- Familiaridade com NumPy, Matplotlib e Scikit-Learn.

## Estrutura do Capítulo

### Notebooks

| Experimento | Descrição | Dificuldade |
|-------------|-----------|------------|
| `04_training_linear_models.ipynb` | Fluxo de treinamento de modelos: Equação Normal, descida do gradiente em lote, estocástica e mini-lotes, regressão polinomial, curvas de aprendizado, Ridge, Lasso, Elastic Net, parada antecipada, regressão logística, fronteiras de decisão e regressão Softmax. | Intermediário |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 04 do livro, com atenção especial à intuição por trás de otimização e regularização.
2. **Prática**:
   - Execute o notebook `04_training_linear_models.ipynb` em ordem.
   - Compare a solução direta da Equação Normal com métodos iterativos de descida do gradiente.
   - Observe como regressão polinomial permite ajustar relações não lineares.
   - Use curvas de aprendizado para identificar subajuste e sobreajuste.
   - Compare Ridge, Lasso e Elastic Net.
   - Entenda como regressão logística e Softmax transformam modelos lineares em classificadores.
3. **Reflexão**:
   - Quando vale mais usar uma solução fechada e quando vale usar descida do gradiente?
   - Como regularização altera a complexidade do modelo?
   - Por que parada antecipada pode funcionar como regularização?
   - Qual a diferença entre regressão logística binária e regressão Softmax?

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

- ✅ Treinar regressão linear pela Equação Normal e por descida do gradiente.
- ✅ Diferenciar descida do gradiente em lote, estocástica e em mini-lotes.
- ✅ Criar atributos polinomiais para modelar relações não lineares.
- ✅ Interpretar curvas de aprendizado para diagnosticar o comportamento do modelo.
- ✅ Aplicar regularização com Ridge, Lasso e Elastic Net.
- ✅ Usar parada antecipada para controlar sobreajuste.
- ✅ Treinar classificadores com regressão logística e regressão Softmax.

## Exercícios

- **Perguntas do Capítulo 4**: as soluções finais foram deixadas fora do notebook principal e serão organizadas em `Respostas.md`.

## Status de Conclusão

- [ ] Conceitos fundamentais revisados.
- [x] Notebook principal estruturado até regressão Softmax.
- [ ] Exercícios completos.

**Última atualização**: Maio de 2026
