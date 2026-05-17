# Perguntas e Exercícios - Capítulo 3

<!-- Clique em "Minha Resposta" ou "Resposta Oficial (Resumo)" para expandir. -->

### 1 - Tente construir um classificador para o MNIST com mais de 97% de acurácia.

<details>
<summary><strong>Minha Resposta</strong></summary>

Resolvi com `KNeighborsClassifier` usando a divisão padrão do MNIST: 60.000 imagens para treino e 10.000 para teste.

Primeiro testei o classificador binário para detectar o dígito 5:

- validação cruzada inicial: `0.9941`, `0.9930`, `0.9931`;
- melhores parâmetros no `GridSearchCV`: `n_neighbors=5`, `weights="uniform"`;
- acurácia final no teste binário: `0.9939`.

Depois apliquei o mesmo processo ao problema multiclasse, classificando os dígitos de 0 a 9:

- validação cruzada inicial: `0.9676`, `0.9671`, `0.96755`;
- melhores parâmetros no `GridSearchCV`: `n_neighbors=3`, `weights="distance"`;
- acurácia média na validação cruzada: `0.9693`;
- acurácia final no conjunto de teste: `0.9717`.

O modelo final ficou acima da meta de 97% de acurácia.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O livro sugere usar `KNeighborsClassifier` e ajustar hiperparâmetros como `weights` e `n_neighbors`, por exemplo com `GridSearchCV`, para ultrapassar 97% de acurácia no conjunto de teste.
</details>

---

### 2 - Faça aumento de dados deslocando imagens do MNIST.

<details>
<summary><strong>Minha Resposta</strong></summary>

Usei aumento de dados no MNIST deslocando cada imagem de treino em 1 pixel para quatro direções: baixo, cima, direita e esquerda.

O conjunto de treino passou de `60.000` para `300.000` imagens. Depois embaralhei o conjunto aumentado e treinei o `KNeighborsClassifier` com os melhores hiperparâmetros encontrados no exercício anterior:

```python
KNeighborsClassifier(n_neighbors=3, weights="distance")
```

A avaliação foi feita no conjunto de teste original, sem aumento de dados. A acurácia final foi:

```text
0.9763
```

Esse resultado melhorou a acurácia do exercício anterior, que havia sido `0.9717`, confirmando que os deslocamentos ajudaram o classificador a generalizar melhor.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A ideia é criar cópias deslocadas das imagens para cima, baixo, esquerda e direita, aumentando o conjunto de treino. Depois, treina-se novamente o classificador e compara-se o desempenho.
</details>

---

### 3 - Enfrente o conjunto de dados Titanic.

<details>
<summary><strong>Minha Resposta</strong></summary>

Montei um pipeline de preparação para o Titanic usando:

- atributos numéricos: `Age`, `SibSp`, `Parch`, `Fare`;
- atributos categóricos: `Pclass`, `Sex`, `Embarked`;
- imputação pela mediana para atributos numéricos;
- imputação pelo valor mais frequente para atributos categóricos;
- `StandardScaler` nos números;
- `OneHotEncoder(handle_unknown="ignore")` nas categorias.

Comparei dois modelos.

Para `RandomForestClassifier`, a validação cruzada inicial retornou:

```text
0.7744, 0.8182, 0.7811
```

Depois do `GridSearchCV`, os melhores parâmetros foram:

```python
{
    "classifier__max_depth": None,
    "classifier__min_samples_leaf": 4,
    "classifier__min_samples_split": 2,
    "classifier__n_estimators": 100,
}
```

A melhor acurácia média na validação cruzada foi `0.8316`. Usando `gender_submission.csv` como referência didática para avaliar o arquivo de teste, a acurácia foi `0.8971`.

Também testei `KNeighborsClassifier`. A validação cruzada inicial ficou em torno de `0.806`, e o melhor `GridSearchCV` encontrou:

```python
{
    "classifier__n_neighbors": 20,
    "classifier__p": 1,
    "classifier__weights": "uniform",
}
```

A melhor acurácia média do KNN foi `0.8205`, e a avaliação contra `gender_submission.csv` foi `0.8660`.

O melhor modelo neste exercício foi o `RandomForestClassifier`.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício propõe criar um encadeamento de preparação para atributos numéricos e categóricos, treinar um classificador e avaliar a previsão de sobrevivência dos passageiros.
</details>

---

### 4 - Construa um classificador de spam.

<details>
<summary><strong>Minha Resposta</strong></summary>

Construí um detector de spam com um pipeline completo do scikit-learn.

Primeiro carreguei os e-mails `easy_ham` e `spam_1`. O conjunto usado tinha proporção aproximada de:

- `ham`: `83.6%`;
- `spam`: `16.4%`.

Fiz uma divisão estratificada em treino e teste, mantendo essa proporção nas duas partes.

O pré-processamento extraiu sinais dos e-mails brutos, incluindo:

- assunto, remetente, domínio e diferença entre `From` e `Reply-to`;
- corpo em texto puro, com conversão simples de HTML para texto;
- presença de HTML, imagens, GIFs e anexos;
- quantidade de links e domínios de links;
- contagem de palavras promocionais;
- menções a dinheiro;
- exclamações e proporção de letras maiúsculas;
- flags explicáveis como `many_links`, `has_money`, `many_promo_words`, `html_with_links` e `link_domain_diff_from_sender`.

O pipeline final combinou:

- `EmailFeatureExtractor`;
- `EmailFeatureEngineer`;
- `ColumnTransformer`;
- `TfidfVectorizer` para o texto;
- imputação e escala para atributos numéricos;
- `OneHotEncoder` para atributos categóricos;
- `LogisticRegression(class_weight="balanced")`.

Na validação cruzada do pipeline inicial, obtive:

```text
Accuracy CV: 0.9865, 0.9692, 0.9668
Accuracy média: 0.9742
F1 macro médio: 0.9532
```

Depois usei `GridSearchCV` otimizando `f1_macro`. Os melhores parâmetros foram:

```python
{
    "classificador__C": 2.0,
    "preprocessar__texto__min_df": 1,
    "preprocessar__texto__ngram_range": (1, 1),
}
```

O melhor `f1_macro` médio na validação cruzada foi `0.9610`.

No conjunto de teste, o melhor modelo alcançou:

```text
Accuracy no teste: 0.9820
```

A matriz de confusão foi:

```text
           previsto_ham  previsto_spam
real_ham            507              4
real_spam             7             93
```

O relatório final ficou com `precision=0.96`, `recall=0.93` e `f1-score=0.94` para a classe `spam`. O modelo cometeu `4` falsos positivos e `7` falsos negativos.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O objetivo é baixar um conjunto de emails, separar treino/teste, transformar textos em atributos numéricos e treinar um classificador capaz de distinguir spam de emails legítimos.
</details>
