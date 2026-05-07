# Perguntas e Exercícios - Capítulo 2

Este arquivo resume os exercícios práticos do capítulo 2. A ideia aqui não é repetir todo o código dos notebooks, mas deixar claro o ponto principal de cada experimento e comparar, de forma simples, a qualidade das abordagens.

## Comparação Geral

Revisão numérica feita após executar os notebooks `02_Resposta_exercicio1.ipynb` a `02_Resposta_exercicio6.ipynb` de ponta a ponta.

| Exercício | Notebook | Ponto principal | Melhor validação | Teste final | Qualidade prática |
|-----------|----------|-----------------|------------------|-------------|-------------------|
| 1 | `02_Resposta_exercicio1.ipynb` | Testar `SVR` com `GridSearchCV`. | RMSE 78.666 | RMSE 77.065 | Útil para aprender busca em grade, mas ficou bem abaixo das melhores alternativas. |
| 2 | `02_Resposta_exercicio2.ipynb` | Trocar `GridSearchCV` por `RandomizedSearchCV`. | RMSE 55.805 | RMSE 57.198 | Melhor resultado geral entre estes exercícios. |
| 3 | `02_Resposta_exercicio3.ipynb` | Adicionar `SelectFromModel` antes do regressor final. | RMSE 56.159 | RMSE 57.219 | Quase empatou com o exercício 2, mas não melhorou de fato. |
| 4 | `02_Resposta_exercicio4.ipynb` | Criar uma característica geográfica com `KNeighborsRegressor`. | RMSE 104.866 | RMSE 101.973 | Didaticamente valioso, mas numericamente fraco nesta configuração. |
| 5 | `02_Resposta_exercicio5.ipynb` | Usar `GridSearchCV` para explorar opções de preparação. | RMSE 72.448 | RMSE 70.495 | Melhorou muito o exercício 4, mas ainda ficou pior que a abordagem com busca aleatória do `SVR`. |
| 6 | `02_Resposta_exercicio6.ipynb` | Implementar `StandardScalerClone`. | Testes passaram | Não se aplica | Exercício de API, não de desempenho preditivo. |

---

## 1 - Usar um Support Vector Machine regressor

### Minha Resposta

Foi criado um pipeline com o pré-processamento completo do capítulo e um `SVR` como regressor final. Em seguida, usei `GridSearchCV` para testar combinações de `kernel`, `C` e `gamma`.

O ponto principal é entender como trocar o estimador final sem refazer todo o pré-processamento. Como o `SVR` está dentro do `Pipeline`, a validação cruzada aplica as transformações corretamente em cada divisão dos dados.

Resultado após execução:

- melhor configuração: `C=100`, `kernel="linear"`;
- RMSE médio de validação cruzada: **78.666**;
- RMSE no conjunto de teste: **77.065**.

### Qualidade em relação às outras abordagens

O `SVR` é uma boa opção para testar, mas neste conjunto de dados ele costuma ser menos competitivo que `RandomForestRegressor`. Além disso, `GridSearchCV` testa uma lista fixa de valores; se a grade for mal escolhida, a busca pode gastar tempo em regiões pouco úteis.

Na comparação com o exercício 2, este resultado mostra a limitação de uma grade pequena: ela não encontrou a região de hiperparâmetros muito melhor que a busca aleatória encontrou.

### Resposta Oficial - Resumo

O livro propõe usar `GridSearchCV` com kernels `linear` e `rbf`. A conclusão principal é que o `SVR` pode ser ajustado, mas não supera facilmente a floresta aleatória usada no projeto principal.

---

## 2 - Substituir `GridSearchCV` por `RandomizedSearchCV`

### Minha Resposta

O exercício troca a busca em grade por `RandomizedSearchCV`. Em vez de testar valores fixos, usamos distribuições:

- `loguniform` para `C`, pois esse hiperparâmetro pode variar em várias ordens de grandeza.
- `expon` para `gamma`, pois queremos testar valores contínuos em uma escala provável.

Resultado após execução:

- melhor configuração: `kernel="rbf"`, `C≈157055.11`, `gamma≈0.26497`;
- RMSE médio de validação cruzada: **55.805**;
- RMSE no conjunto de teste: **57.198**.

### Qualidade em relação às outras abordagens

Essa abordagem é geralmente melhor que `GridSearchCV` quando não sabemos exatamente quais valores testar. Com o mesmo número de tentativas, a busca aleatória cobre melhor espaços grandes e contínuos.

Ela não garante testar todas as combinações, mas isso é justamente a vantagem: evita gastar tempo demais em uma grade arbitrária.

Neste conjunto de exercícios, foi a melhor abordagem numérica. A busca aleatória encontrou uma região de hiperparâmetros que a grade simples do exercício 1 não testava.

### Resposta Oficial - Resumo

O livro usa `RandomizedSearchCV` para mostrar que a busca aleatória pode encontrar boas combinações de hiperparâmetros com menos rigidez que a busca em grade.

---

## 3 - Adicionar `SelectFromModel`

### Minha Resposta

Foi adicionado um `SelectFromModel` depois do `preprocessing` e antes do `SVR`:

```python
Pipeline([
    ("preprocessing", preprocessing),
    ("selector", SelectFromModel(RandomForestRegressor(...))),
    ("svr", SVR(...)),
])
```

O seletor usa um `RandomForestRegressor` para estimar a importância dos atributos já preparados. Depois ele mantém apenas os atributos acima de um limiar de importância.

Resultado após execução:

- configuração do `SVR`: a mesma melhor configuração encontrada pela busca aleatória do exercício 2;
- RMSE médio com `SelectFromModel`: **56.159**;
- RMSE no conjunto de teste: **57.219**.

### Qualidade em relação às outras abordagens

A seleção de atributos pode simplificar o modelo e reduzir ruído, mas não é garantia de melhora. Neste caso, ela pode até piorar se remover atributos úteis ou se o limiar escolhido não for adequado.

Comparada aos exercícios 1 e 2, essa abordagem mexe mais na representação dos dados do que no regressor em si. É útil para estudar engenharia de atributos, mas deve ser validada com cuidado.

Na comparação direta com o exercício 2, o `SelectFromModel` não trouxe ganho: o RMSE de teste ficou praticamente igual, ligeiramente pior. Isso sugere que os atributos removidos ainda carregavam informação útil, ou que o limiar `threshold=0.005` não era o ideal.

### Resposta Oficial - Resumo

O livro mostra que `SelectFromModel` não parece melhorar muito nesse caso. A observação importante é que o limiar usado pode não ser ideal, então seria possível ajustá-lo com busca em grade ou busca aleatória.

---

## 4 - Criar uma característica com `KNeighborsRegressor`

### Minha Resposta

Foi criado o transformador `FeatureFromRegressor`. Ele treina um regressor no método `fit()` e retorna as predições no método `transform()`.

No exercício, o regressor usado é:

```python
KNeighborsRegressor(n_neighbors=3, weights="distance")
```

Ele recebe apenas `latitude` e `longitude`. Assim, a nova característica representa uma estimativa do preço mediano dos imóveis em regiões próximas.

Resultado após execução:

- característica gerada: `kneighborsregressor_prediction_0`;
- RMSE médio de validação cruzada: **104.866**;
- RMSE no conjunto de teste: **101.973**.

### Qualidade em relação às outras abordagens

Esse exercício é muito bom para entender transformadores supervisionados dentro de um pipeline. A característica criada usa o alvo durante o `fit()`, então ela precisa obrigatoriamente estar dentro do pipeline para evitar vazamento de dados.

Na prática, o livro observa que essa ideia tende a ficar pior que a abordagem de similaridade por clusters (`ClusterSimilarity`). Mesmo assim, ela é conceitualmente valiosa porque mostra como criar atributos aprendidos a partir dos dados.

Numericamente, este foi o pior resultado entre os exercícios com RMSE. O motivo provável é que uma única predição baseada só em vizinhos geográficos perdeu informação que a etapa original de similaridade por clusters representava melhor.

### Resposta Oficial - Resumo

O livro implementa uma classe genérica que aceita qualquer regressor, não apenas KNN. Depois substitui a etapa geográfica do `ColumnTransformer` por esse novo transformador.

---

## 5 - Explorar opções de preparação com `GridSearchCV`

### Minha Resposta

O exercício usa `GridSearchCV` para testar opções internas do pipeline. A parte mais importante é ajustar hiperparâmetros de preparação usando nomes compostos:

```python
preprocessing__geo__estimator__n_neighbors
preprocessing__geo__estimator__weights
```

Esses nomes entram no pipeline assim:

- `preprocessing`: etapa principal do `Pipeline`.
- `geo`: transformador geográfico dentro do `ColumnTransformer`.
- `estimator`: regressor encapsulado por `FeatureFromRegressor`.
- `n_neighbors` e `weights`: hiperparâmetros do `KNeighborsRegressor`.

Resultado após execução:

- melhor configuração: `n_neighbors=1`, `weights="distance"`, `SVR(C=100000, gamma=0.03, kernel="rbf")`;
- RMSE médio de validação cruzada: **72.448**;
- RMSE no conjunto de teste: **70.495**.

### Qualidade em relação às outras abordagens

Esse é um dos exercícios mais importantes do capítulo em termos de prática profissional. Ele mostra que não devemos otimizar apenas o modelo final; também podemos otimizar decisões de preparação dos dados.

A desvantagem é o custo. `GridSearchCV` cresce rapidamente: poucos valores a mais em cada parâmetro multiplicam o número de treinamentos. Por isso, para espaços maiores, `RandomizedSearchCV` costuma ser mais prático.

Comparado ao exercício 4, a busca em grade melhorou muito a característica geográfica com KNN. Mesmo assim, o resultado ainda ficou pior que o exercício 2, então a otimização da preparação não compensou a perda causada por trocar a similaridade por clusters.

### Resposta Oficial - Resumo

O livro usa busca automática para testar parâmetros do novo transformador geográfico e do `SVR`. A conclusão é que a característica KNN ainda pode não superar a similaridade por clusters, mas o exercício ensina como expor opções de preparação para busca.

---

## 6 - Implementar `StandardScalerClone`

### Minha Resposta

Foi implementada uma classe `StandardScalerClone` compatível com a API do Scikit-Learn. Ela inclui:

- `fit()` para aprender média, escala e número de atributos.
- `transform()` para padronizar os dados.
- `inverse_transform()` para voltar à escala original.
- `get_feature_names_out()` para lidar com nomes de atributos.
- suporte a `DataFrame` por meio de `feature_names_in_`.

Resultado após execução:

- `transform()` bateu com a fórmula manual: **passou**;
- `with_mean=False`: **passou**;
- `inverse_transform()`: **passou**;
- nomes genéricos (`x0`, `x1`, `x2`): **passou**;
- nomes vindos de `DataFrame`: **passou**;
- validação de nomes incompatíveis: **passou**.

### Qualidade em relação às outras abordagens

Esse exercício não tem o objetivo de melhorar o RMSE. Ele é importante por outro motivo: entender como o Scikit-Learn espera que estimadores e transformadores se comportem.

Em termos de modelagem, ele não compete com `SVR`, `RandomForest`, `SelectFromModel` ou KNN. Em termos de aprendizado técnico, é um dos exercícios mais importantes, porque ajuda a criar transformadores reutilizáveis e compatíveis com `Pipeline`, `ColumnTransformer` e ferramentas de validação.

Na comparação geral, este exercício deve ser avaliado pela correção da API, não por RMSE. Ele ficou completo para o objetivo proposto.

### Resposta Oficial - Resumo

O livro implementa um clone do `StandardScaler`, adicionando `inverse_transform()` e suporte a nomes de atributos. A classe deve conseguir passar nos testes básicos da API do Scikit-Learn.
