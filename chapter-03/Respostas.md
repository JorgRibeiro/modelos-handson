# Perguntas e Exercícios - Capítulo 3

<!-- Clique em "Minha Resposta" ou "Resposta Oficial (Resumo)" para expandir. -->

### 1 - Tente construir um classificador para o MNIST com mais de 97% de acurácia.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O livro sugere usar `KNeighborsClassifier` e ajustar hiperparâmetros como `weights` e `n_neighbors`, por exemplo com `GridSearchCV`, para ultrapassar 97% de acurácia no conjunto de teste.
</details>

---

### 2 - Faça aumento de dados deslocando imagens do MNIST.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A ideia é criar cópias deslocadas das imagens para cima, baixo, esquerda e direita, aumentando o conjunto de treino. Depois, treina-se novamente o classificador e compara-se o desempenho.
</details>

---

### 3 - Enfrente o conjunto de dados Titanic.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício propõe criar um encadeamento de preparação para atributos numéricos e categóricos, treinar um classificador e avaliar a previsão de sobrevivência dos passageiros.
</details>

---

### 4 - Construa um classificador de spam.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O objetivo é baixar um conjunto de emails, separar treino/teste, transformar textos em atributos numéricos e treinar um classificador capaz de distinguir spam de emails legítimos.
</details>
