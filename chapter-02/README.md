# Capitulo 02: Projeto de Aprendizado de Maquina de Ponta a Ponta

## Objetivo

Aplicar um fluxo completo de aprendizado de maquina usando o conjunto California Housing Prices: obter dados, criar conjunto de teste, explorar padroes, preparar atributos, treinar modelos, ajustar hiperparametros, avaliar no teste final e persistir o modelo.

Este capitulo transforma os conceitos do Capitulo 1 em um projeto pratico com encadeamentos reutilizaveis do Scikit-Learn.

## Pre-requisitos

- Conceitos do Capitulo 1: tipos de aprendizado, generalizacao, sobreajuste, subajuste e avaliacao.
- Familiaridade com Pandas, NumPy, Matplotlib e Scikit-Learn.
- Ambiente `.venv` ativo com as dependencias do projeto instaladas.

## Estrutura do Capitulo

### Notebook principal

| Arquivo | Conteudo | Dificuldade |
|---------|----------|-------------|
| `02_Projeto_End_to_End_de_Machine_Learning.ipynb` | Projeto completo: configuracao, download dos dados, analise exploratoria, conjunto de teste, limpeza, atributos categoricos, escalonamento, transformadores personalizados, pipelines, treinamento, validacao cruzada, `GridSearchCV`, `RandomizedSearchCV`, avaliacao final e persistencia com `joblib`. | Intermediario |

### Exercicios

| Ordem | Arquivo | Foco | Dificuldade |
|-------|---------|------|-------------|
| 1 | `02_Resposta_exercicio1.ipynb` | Testar `SVR` com `GridSearchCV`. | Intermediario |
| 2 | `02_Resposta_exercicio2.ipynb` | Substituir grade fixa por `RandomizedSearchCV`. | Intermediario |
| 3 | `02_Resposta_exercicio3.ipynb` | Inserir `SelectFromModel` antes do regressor final. | Intermediario |
| 4 | `02_Resposta_exercicio4.ipynb` | Criar um transformador supervisionado com `KNeighborsRegressor` para atributos geograficos. | Avancado |
| 5 | `02_Resposta_exercicio5.ipynb` | Otimizar parametros da preparacao e do modelo dentro do pipeline. | Avancado |
| 6 | `02_Resposta_exercicio6.ipynb` | Implementar `StandardScalerClone` compativel com a API do Scikit-Learn. | Avancado |
| - | `Respostas.md` | Comparacao comentada dos exercicios e resultados. | Revisao |

## Fluxo do Notebook Principal

1. **Obter os dados**
   - Baixa e extrai `housing.tgz`.
   - Carrega os dados em um `DataFrame`.

2. **Inspecionar a estrutura**
   - Analisa colunas, tipos, valores ausentes e distribuicoes.
   - Examina `ocean_proximity` como atributo categorico.

3. **Criar conjunto de teste**
   - Separa teste antes da exploracao detalhada.
   - Usa amostragem estratificada com base em categorias de renda.

4. **Explorar e visualizar**
   - Gera visualizacoes geograficas.
   - Analisa correlacoes com `median_house_value`.
   - Cria combinacoes de atributos como quartos por residencia e pessoas por residencia.

5. **Preparar dados**
   - Trata valores ausentes.
   - Codifica categorias com one-hot encoding.
   - Escalona atributos numericos.
   - Cria transformadores personalizados.
   - Organiza tudo com `Pipeline` e `ColumnTransformer`.

6. **Treinar e avaliar modelos**
   - Compara regressores simples e modelos mais flexiveis.
   - Usa validacao cruzada para medir generalizacao.

7. **Ajustar hiperparametros**
   - Usa `GridSearchCV` para uma busca sistematica.
   - Usa `RandomizedSearchCV` para explorar espacos maiores.
   - Analisa importancia de atributos.

8. **Avaliar e persistir**
   - Avalia o modelo final no conjunto de teste.
   - Salva o pipeline completo com `joblib`.

## Resultados dos Exercicios

| Exercicio | Abordagem | Melhor validacao | Teste final | Leitura rapida |
|-----------|-----------|------------------|-------------|----------------|
| 1 | `SVR` + `GridSearchCV` | RMSE 78.666 | RMSE 77.065 | Grade pequena ficou limitada. |
| 2 | `SVR` + `RandomizedSearchCV` | RMSE 55.805 | RMSE 57.198 | Melhor resultado entre os exercicios. |
| 3 | `SelectFromModel` + `SVR` | RMSE 56.159 | RMSE 57.219 | Selecao de atributos nao melhorou o exercicio 2. |
| 4 | KNN geografico como caracteristica | RMSE 104.866 | RMSE 101.973 | Ideia didatica, mas resultado fraco. |
| 5 | Preparacao com `GridSearchCV` | RMSE 72.448 | RMSE 70.495 | Melhorou o KNN geografico, mas nao superou o exercicio 2. |
| 6 | `StandardScalerClone` | Testes passaram | Nao se aplica | Exercicio de compatibilidade com a API. |

Para os comentarios completos, consulte `Respostas.md`.

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
chapter-02/02_Projeto_End_to_End_de_Machine_Learning.ipynb
```

Os notebooks de exercicios podem ser executados em ordem, de `02_Resposta_exercicio1.ipynb` ate `02_Resposta_exercicio6.ipynb`.

## Resultados Esperados

Ao concluir este capitulo, voce devera ser capaz de:

- Montar um fluxo completo de ML para regressao.
- Criar conjuntos de treino e teste com amostragem estratificada.
- Fazer EDA orientada a modelagem.
- Criar atributos derivados e transformadores personalizados.
- Usar `Pipeline` e `ColumnTransformer` para evitar vazamento de dados.
- Comparar modelos com validacao cruzada.
- Ajustar hiperparametros com `GridSearchCV` e `RandomizedSearchCV`.
- Avaliar o modelo final apenas no conjunto de teste.
- Persistir o pipeline final com `joblib`.

## Status de Conclusao

- [x] Notebook principal estruturado ate a persistencia do modelo.
- [x] Exercicios 1 a 6 separados em notebooks proprios.
- [x] `Respostas.md` atualizado com comparacao numerica.
- [x] README atualizado com a estrutura real do capitulo.

**Ultima atualizacao**: 7 de maio de 2026
