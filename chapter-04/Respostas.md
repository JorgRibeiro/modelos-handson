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

### 2 - Suponha que as características do seu conjunto de treinamento tenham escalas muito diferentes. Quais tipos de algoritmos podem sofrer com isso e como? O que fazer a respeito?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam os conceitos centrais do capítulo: Equação Normal, descida do gradiente, taxa de aprendizado, escalonamento de atributos, regressão polinomial, curvas de aprendizado, regularização, Ridge, Lasso, Elastic Net, regressão logística e regressão Softmax.
</details>

---

### 3 - O gradiente descendente pode ficar empacado em um mínimo local quando treinamos um modelo de regressão logística?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam os conceitos centrais do capítulo: Equação Normal, descida do gradiente, taxa de aprendizado, escalonamento de atributos, regressão polinomial, curvas de aprendizado, regularização, Ridge, Lasso, Elastic Net, regressão logística e regressão Softmax.
</details>

---

### 4 - Todos os algoritmos do gradiente descendente resultam no mesmo modelo, contanto que você os execute por tempo suficiente?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam os conceitos centrais do capítulo: Equação Normal, descida do gradiente, taxa de aprendizado, escalonamento de atributos, regressão polinomial, curvas de aprendizado, regularização, Ridge, Lasso, Elastic Net, regressão logística e regressão Softmax.
</details>

---

### 5 - Suponha que você utilize o gradiente descendente em batch e plote o erro de validação em cada época. Caso perceba que o erro de validação aumenta constantemente, o que provavelmente está acontecendo? Como consertar isso?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam os conceitos centrais do capítulo: Equação Normal, descida do gradiente, taxa de aprendizado, escalonamento de atributos, regressão polinomial, curvas de aprendizado, regularização, Ridge, Lasso, Elastic Net, regressão logística e regressão Softmax.
</details>

---

### 6 - É uma boa parar o gradiente descendente em minibatch logo que o erro de validação aumenta?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam os conceitos centrais do capítulo: Equação Normal, descida do gradiente, taxa de aprendizado, escalonamento de atributos, regressão polinomial, curvas de aprendizado, regularização, Ridge, Lasso, Elastic Net, regressão logística e regressão Softmax.
</details>

---

### 7 - Qual o algoritmo do gradiente descendente (entre os que discutimos) chegará mais rápido e próximo da solução ideal? Qual deles convergirá? Como você pode fazer os outros convergirem também?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam os conceitos centrais do capítulo: Equação Normal, descida do gradiente, taxa de aprendizado, escalonamento de atributos, regressão polinomial, curvas de aprendizado, regularização, Ridge, Lasso, Elastic Net, regressão logística e regressão Softmax.
</details>

---

### 8 - Imagine que esteja usando a regressão polinomial. Você plota as curvas de aprendizado e percebe que existe uma lacuna enorme entre o erro de treinamento e o erro de validação. O que está acontecendo? Quais são as três formas de resolver isso?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam os conceitos centrais do capítulo: Equação Normal, descida do gradiente, taxa de aprendizado, escalonamento de atributos, regressão polinomial, curvas de aprendizado, regularização, Ridge, Lasso, Elastic Net, regressão logística e regressão Softmax.
</details>

---

### 9 - Suponha que você esteja usando a Regressão Ridge e note que o erro de treinamento e o erro de validação são quase iguais e bem altos. Você diria que o modelo tem um viés alto ou uma variância alta? Você deve aumentar o hiperparâmetro alpha da regularização ou reduzi-lo?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam os conceitos centrais do capítulo: Equação Normal, descida do gradiente, taxa de aprendizado, escalonamento de atributos, regressão polinomial, curvas de aprendizado, regularização, Ridge, Lasso, Elastic Net, regressão logística e regressão Softmax.
</details>

---

### 10 - Por que você usaria:
###    a. A regressão Ridge em vez da regressão linear simples (ou seja, sem qualquer regularização)?
###    b. A regressão Lasso em vez da regressão Ridge?
###    c. A regressão Elastic Net em vez da regressão Lasso?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam os conceitos centrais do capítulo: Equação Normal, descida do gradiente, taxa de aprendizado, escalonamento de atributos, regressão polinomial, curvas de aprendizado, regularização, Ridge, Lasso, Elastic Net, regressão logística e regressão Softmax.
</details>

---

### 11 - Suponha que você queira classificar as fotos como externas/internas e diurnas/noturnas. Você deve implementar dois classificadores de regressão logística ou um classificador de regressão Softmax.

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
