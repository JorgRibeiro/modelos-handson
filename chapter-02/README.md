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
| `02_Resposta_exercicio1.ipynb` | Testa `SVR` como novo regressor usando `GridSearchCV`. | Intermediário |
| `02_Resposta_exercicio2.ipynb` | Substitui busca em grade por `RandomizedSearchCV` para explorar melhor os hiperparâmetros do `SVR`. | Intermediário |
| `02_Resposta_exercicio3.ipynb` | Adiciona `SelectFromModel` ao pipeline para selecionar atributos antes do regressor final. | Intermediário |
| `02_Resposta_exercicio4.ipynb` | Cria um transformador supervisionado que usa `KNeighborsRegressor` para gerar uma característica geográfica baseada em `latitude` e `longitude`. | Avançado |
| `02_Resposta_exercicio5.ipynb` | Usa `GridSearchCV` para explorar opções de preparação dentro do pipeline, incluindo parâmetros do transformador geográfico. | Avançado |
| `02_Resposta_exercicio6.ipynb` | Implementa `StandardScalerClone` com `fit()`, `transform()`, `inverse_transform()` e suporte a nomes de atributos. | Avançado |
| `Respostas.md` | Resumo comparativo dos exercícios, com ponto principal de cada implementação e avaliação qualitativa. | Leitura |

## Roteiro de Estudo Recomendado

1. **Leitura**: Capítulo 02 do livro (Project Checklist).
2. **Prática**:
   - Acompanhe e execute o notebook `02_Projeto_End_to_End_de_Machine_Learning.ipynb`.
   - Entenda a criação do conjunto de teste e a amostragem estratificada por categoria de renda.
   - Analise os transformadores personalizados e os encadeamentos de pré-processamento.
   - Compare os resultados de Regressão Linear, Árvore de Decisão e Floresta Aleatória.
   - Observe a diferença entre erro de treino, erro de validação cruzada e erro final no conjunto de teste.
   - Execute os exercícios em ordem, pois os exercícios 4 e 5 reaproveitam ideias dos exercícios anteriores.
3. **Reflexão**:
   - Como os encadeamentos ajudam a evitar vazamento de dados?
   - Qual a diferença entre busca em grade e busca aleatória?
   - Por que o conjunto de teste só deve ser usado no final?
   - Quando vale a pena otimizar a preparação dos dados, e não apenas o modelo final?
   - Uma característica nova precisa necessariamente melhorar o RMSE para ser útil como aprendizado?

## Roteiro dos Exercícios

| Ordem | Arquivo | Foco | Observação |
|-------|---------|------|------------|
| 1 | `02_Resposta_exercicio1.ipynb` | `SVR` com `GridSearchCV` | Base para comparar busca em grade e busca aleatória. |
| 2 | `02_Resposta_exercicio2.ipynb` | `RandomizedSearchCV` | Mais flexível para espaços grandes de hiperparâmetros. |
| 3 | `02_Resposta_exercicio3.ipynb` | `SelectFromModel` | Seleciona atributos, mas pode não melhorar o resultado. |
| 4 | `02_Resposta_exercicio4.ipynb` | Transformador com KNN | Cria uma característica supervisionada a partir de localização. |
| 5 | `02_Resposta_exercicio5.ipynb` | Preparação com `GridSearchCV` | Ajusta parâmetros internos do pipeline de preparação. |
| 6 | `02_Resposta_exercicio6.ipynb` | API de transformadores | Recria uma versão didática do `StandardScaler`. |

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

## Resultados dos Exercícios

Após a execução completa dos notebooks de exercícios, os principais resultados foram:

| Exercício | Abordagem | Melhor validação | Teste final | Leitura rápida |
|-----------|-----------|------------------|-------------|----------------|
| 1 | `SVR` + `GridSearchCV` | RMSE 78.666 | RMSE 77.065 | Grade pequena ficou limitada. |
| 2 | `SVR` + `RandomizedSearchCV` | RMSE 55.805 | RMSE 57.198 | Melhor resultado entre os exercícios. |
| 3 | `SelectFromModel` + `SVR` | RMSE 56.159 | RMSE 57.219 | Seleção de atributos não melhorou o exercício 2. |
| 4 | KNN geográfico como característica | RMSE 104.866 | RMSE 101.973 | Ideia didática, mas resultado fraco. |
| 5 | Preparação com `GridSearchCV` | RMSE 72.448 | RMSE 70.495 | Melhorou o KNN geográfico, mas não superou o exercício 2. |
| 6 | `StandardScalerClone` | Testes passaram | Não se aplica | Exercício de compatibilidade com a API. |

Para a comparação comentada, veja `Respostas.md`.

## Exercícios

- **Resumo comparativo**: consulte `Respostas.md` para ver o ponto principal de cada exercício e uma comparação simples entre as abordagens.
- **Notebooks práticos**: os exercícios 1 a 6 estão em notebooks separados para manter o notebook principal limpo.
- **Soluções finais do livro**: permanecem fora do notebook principal, seguindo a organização dos demais capítulos.

## Status de Conclusão

- [ ] Conceitos fundamentais revisados.
- [x] Notebook principal estruturado até a persistência do modelo.
- [x] Exercícios 1 a 6 separados em notebooks próprios.
- [x] `Respostas.md` atualizado com resumo e comparação.
- [x] Revisão final dos resultados numéricos após execução completa dos exercícios.

**Última atualização**: Maio de 2026
