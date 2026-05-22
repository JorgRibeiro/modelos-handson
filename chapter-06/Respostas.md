# Perguntas e Exercícios - Capítulo 6

<!-- Clique em "Minha Resposta" ou "Resposta Oficial (Resumo)" para expandir. -->

### 1 - Qual é a profundidade aproximada de uma árvore de decisão treinada(sem restrições) em um conjunto de treinamento com 1 milhão de instâncias?

<details>
<summary><strong>Minha Resposta</strong></summary>

Para uma árvore de decisão treinada **sem restrições**, a profundidade aproximada é `log2(m)`, em que `m` é o número de instâncias de treino. Para `m = 1.000.000`, temos `log2(1.000.000) ≈ 20`. Na prática, pode ser um pouco maior, porque a árvore geralmente não fica perfeitamente balanceada.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A profundidade de uma árvore binária bem balanceada contendo _m_ folhas é igual a log₂(_m_), arredondado para cima. log₂ é o logaritmo binário; log₂(_m_) = log(_m_) / log(2). Uma Árvore de Decisão binária, isto é, uma árvore que toma apenas decisões binárias, como ocorre com todas as árvores no Scikit-Learn, terminará mais ou menos bem balanceada ao final do treinamento, com uma folha por instância de treinamento se for treinada sem restrições. Portanto, se o conjunto de treinamento contém um milhão de instâncias, a Árvore de Decisão terá profundidade log₂(10<sup>6</sup>) ≈ 20, na verdade um pouco maior, já que a árvore geralmente não será perfeitamente balanceada.
</details>

---

### 2 - Perguntas conceituais sobre árvores de decisão.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam profundidade da árvore, impureza, fronteiras de decisão, probabilidades em folhas, regularização, escalonamento e alta variância.
</details>

---

### 3 - Perguntas conceituais sobre árvores de decisão.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam profundidade da árvore, impureza, fronteiras de decisão, probabilidades em folhas, regularização, escalonamento e alta variância.
</details>

---

### 4 - Perguntas conceituais sobre árvores de decisão.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam profundidade da árvore, impureza, fronteiras de decisão, probabilidades em folhas, regularização, escalonamento e alta variância.
</details>

---

### 5 - Perguntas conceituais sobre árvores de decisão.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam profundidade da árvore, impureza, fronteiras de decisão, probabilidades em folhas, regularização, escalonamento e alta variância.
</details>

---

### 6 - Perguntas conceituais sobre árvores de decisão.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam profundidade da árvore, impureza, fronteiras de decisão, probabilidades em folhas, regularização, escalonamento e alta variância.
</details>

---


### 7 - Treine e ajuste uma árvore no conjunto de dados moons.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício propõe gerar um conjunto com `make_moons`, dividir treino/teste, usar busca de hiperparâmetros em `DecisionTreeClassifier` e medir o desempenho no conjunto de teste.
</details>

---

### 8 - Crie uma floresta manual a partir de várias árvores.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A ideia é treinar várias árvores em subconjuntos aleatórios do treino, combinar suas previsões por votação majoritária e observar como a agregação melhora a estabilidade.
</details>
