# Perguntas e Exercícios - Capítulo 4

<!-- Clique em "Minha Resposta" ou "Resposta Oficial (Resumo)" para expandir. -->

### 1 - Qual algoritmo de treinamento de regressao linear podemos utilizar se temos um conjunto de treinamento com milhoes de caracteristicas?.

<details>
<summary><strong>Minha Resposta</strong></summary>
Podemos usar o gradiente descendente, focando mais no tipo estocástico e minibatch.
A Equação Normal e a decomposição SVD são muito custosas quando a quantidade de características escala.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>
Se você tem um conjunto de treinamento com milhões de características, pode usar a descida do gradiente estocástica ou a descida do gradiente em mini-lotes, e talvez a descida do gradiente em lote se o conjunto de treinamento couber na memória. Mas você não pode usar a Equação Normal nem a abordagem por SVD, porque a complexidade computacional cresce rapidamente, mais do que quadraticamente, com o número de características.

</details>

---

### 1 a 11 - Perguntas conceituais sobre treinamento de modelos lineares.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam os conceitos centrais do capítulo: Equação Normal, descida do gradiente, taxa de aprendizado, escalonamento de atributos, regressão polinomial, curvas de aprendizado, regularização, Ridge, Lasso, Elastic Net, regressão logística e regressão Softmax.
</details>

---

### 12 - Implemente descida do gradiente em lote com parada antecipada para regressão Softmax.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício propõe implementar a regressão Softmax manualmente: calcular as pontuações, aplicar Softmax, computar a entropia cruzada, calcular gradientes, atualizar os pesos por descida do gradiente em lote e usar um conjunto de validação para aplicar parada antecipada.
</details>
