# Perguntas e Exercícios — Capítulo 2

<!-- Clique em 'Minha Resposta' ou 'Resposta do Livro' para expandir -->

### 1 - Tente usar um Support Vector Machine regressor (`sklearn.svm.SVR` com hiperparâmetros variados).

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção enquanto o notebook avança)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O livro propõe usar um `GridSearchCV` para testar kernels `linear` e `rbf` com vários valores de `C` e `gamma`. O objetivo é notar que, para esse dataset, `RandomForestRegressor` costuma ter uma performance muito superior à do `SVR` inicial.
</details>

---

### 2 - Tente substituir um `GridSearchCV` por um `RandomizedSearchCV`.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção enquanto o notebook avança)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A intenção é ver a eficiência do `RandomizedSearchCV` ao buscar hiperparâmetros num espaço maior, especialmente se usarmos distribuições contínuas (ex: `scipy.stats.expon` ou `reciprocal`).
</details>

---

*(Mais exercícios práticos no fim do notebook e anotações aqui posteriormente)*