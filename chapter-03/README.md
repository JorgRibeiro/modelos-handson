# Capítulo 03: Classificação

## Objetivo

Estudar problemas de classificação usando o MNIST como base, passando por classificação binária, métricas de desempenho, classificação multiclasse, análise de erros, classificação multirrótulo e classificação com múltiplas saídas.

## Pré-requisitos

- Conceitos dos Capítulos 01 e 02: treino/teste, validação, sobreajuste e encadeamentos de pré-processamento.
- Familiaridade com NumPy, Matplotlib e Scikit-Learn.
- Noções iniciais de validação cruzada e métricas de avaliação.

## Estrutura do Capítulo

### Notebooks

| Experimento | Descrição | Dificuldade |
|-------------|-----------|------------|
| `03_classification_pt.ipynb` | Fluxo de classificação com MNIST: configuração, visualização dos dígitos, classificador binário para o dígito 5, validação cruzada, matriz de confusão, precisão, revocação, F1, curvas precisão-revocação e ROC, classificação multiclasse, análise de erros, classificação multirrótulo e classificação com múltiplas saídas. | Intermediário |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 03 do livro, com atenção especial às métricas de classificação.
2. **Prática**:
   - Execute o notebook `03_classification_pt.ipynb` em ordem.
   - Entenda por que a acurácia pode ser enganosa em problemas desbalanceados.
   - Compare matriz de confusão, precisão, revocação, F1, curva precisão-revocação e ROC-AUC.
   - Observe como classificadores binários podem ser combinados para classificação multiclasse.
   - Use a análise de erros para identificar quais classes são mais confundidas.
3. **Reflexão**:
   - Quando é melhor priorizar precisão em vez de revocação?
   - Por que a curva precisão-revocação pode ser mais informativa que ROC em alguns cenários?
   - Qual a diferença entre classificação multiclasse, multirrótulo e com múltiplas saídas?

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

- ✅ Treinar classificadores binários e multiclasse com Scikit-Learn.
- ✅ Avaliar modelos com validação cruzada e matriz de confusão.
- ✅ Calcular e interpretar precisão, revocação, F1 e ROC-AUC.
- ✅ Ajustar o limiar de decisão para controlar o equilíbrio entre precisão e revocação.
- ✅ Fazer análise de erros em classificação multiclasse.
- ✅ Diferenciar classificação multiclasse, multirrótulo e com múltiplas saídas.

## Exercícios

- **Perguntas do Capítulo 3**: as soluções finais foram deixadas fora do notebook principal e serão organizadas em `Respostas.md`.

## Status de Conclusão

- [ ] Conceitos fundamentais revisados.
- [x] Notebook principal estruturado até classificação com múltiplas saídas.
- [ ] Exercícios completos.

**Última atualização**: Maio de 2026
