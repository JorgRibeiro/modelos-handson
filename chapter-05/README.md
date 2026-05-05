# Capítulo 05: Máquinas de Vetores de Suporte

## Objetivo

Compreender Support Vector Machines para classificação e regressão, incluindo margens, margem suave, kernels polinomiais, kernel RBF, atributos de similaridade e a intuição geométrica por trás do modelo.

## Pré-requisitos

- Conceitos dos Capítulos 01 a 04: treino/teste, validação, escalonamento, classificação e otimização.
- Noções básicas de vetores, produto escalar e regularização.
- Familiaridade com NumPy, Matplotlib e Scikit-Learn.

## Estrutura do Capítulo

### Notebooks

| Experimento | Descrição | Dificuldade |
|-------------|-----------|------------|
| `05_support_vector_machines.ipynb` | Fluxo de SVMs: classificação linear, margem suave, SVM não linear, kernel polinomial, atributos de similaridade, kernel RBF, regressão com SVM, visualização do funcionamento interno e implementação didática com descida do gradiente em lote. | Intermediário |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 05 do livro, com atenção à intuição de margem e kernels.
2. **Prática**:
   - Execute o notebook `05_support_vector_machines.ipynb` em ordem.
   - Observe como escalonamento altera a fronteira de decisão da SVM.
   - Compare o efeito de `C`, `gamma`, `degree` e `epsilon`.
   - Entenda quando usar `LinearSVC`, `SVC`, `LinearSVR` e `SVR`.
3. **Reflexão**:
   - Como `C` controla o equilíbrio entre margem larga e violações?
   - Por que kernels permitem fronteiras não lineares sem criar todos os atributos manualmente?
   - Quando SVMs deixam de ser uma boa escolha por custo computacional?

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

- ✅ Treinar SVMs lineares e não lineares.
- ✅ Interpretar margem, vetores de suporte e margem suave.
- ✅ Usar kernels polinomial e RBF.
- ✅ Ajustar hiperparâmetros como `C`, `gamma`, `degree` e `epsilon`.
- ✅ Aplicar SVMs em regressão.

## Exercícios

- **Perguntas do Capítulo 5**: as soluções finais foram deixadas fora do notebook principal e serão organizadas em `Respostas.md`.

## Status de Conclusão

- [ ] Conceitos fundamentais revisados.
- [x] Notebook principal estruturado até o material extra de SVM linear.
- [ ] Exercícios completos.

**Última atualização**: Maio de 2026
