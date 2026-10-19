# Perguntas e Exercícios - Capítulo 8

Enunciados adaptados para português dos exercícios da terceira edição de *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow*, de Aurélien Géron. Referência: [notebook oficial do capítulo 8](https://github.com/ageron/handson-ml3/blob/main/08_dimensionality_reduction.ipynb#Exercise-solutions).

<!-- Clique em "Minha Resposta" ou "Resposta Oficial (Resumo)" para expandir. -->

### 1 - Quais são as principais razões para reduzir a dimensionalidade de um conjunto de dados? E as principais desvantagens.

<details>
<summary><strong>Minha Resposta</strong></summary>

As principais razões são diminuir o tempo e o custo de treinamento, além de facilitar a visualização dos dados. Contudo, a redução de dimensionalidade pode causar perda de informações, deterioração do desempenho do sistema e maior complexidade nos pipelines, tornando mais difícil mantê-los.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As principais razões para reduzir a dimensionalidade são acelerar o treinamento de modelos, facilitar a visualização dos dados e a identificação dos atributos mais importantes e economizar espaço de armazenamento por meio da compressão. Em alguns casos, a remoção de ruído e de atributos redundantes também pode melhorar o desempenho dos modelos.

As principais desvantagens são a perda de informação, que pode prejudicar o desempenho dos modelos; o custo computacional da redução; o aumento da complexidade do pipeline; e a dificuldade de interpretar os atributos transformados.
</details>

---

### 2 - O que é a maldição da dimensionalidade?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam a maldição da dimensionalidade, projeção, variedades, PCA, variância explicada, compressão, PCA incremental e técnicas não lineares.
</details>

---

### 3 - Após reduzir a dimensionalidade de um conjunto de dados, é possível reverter a operação? Se sim, como? Se não, por quê?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam a maldição da dimensionalidade, projeção, variedades, PCA, variância explicada, compressão, PCA incremental e técnicas não lineares.
</details>

---

### 4 - É possível usar PCA para reduzir a dimensionalidade de um conjunto de dados altamente não linear?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam a maldição da dimensionalidade, projeção, variedades, PCA, variância explicada, compressão, PCA incremental e técnicas não lineares.
</details>

---

### 5 - Suponha que você aplique PCA a um conjunto de dados com 1.000 dimensões, preservando 95% da variância. Quantas dimensões terá o conjunto resultante?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam a maldição da dimensionalidade, projeção, variedades, PCA, variância explicada, compressão, PCA incremental e técnicas não lineares.
</details>

---

### 6 - Em quais situações você usaria PCA convencional, PCA incremental, PCA randomizado ou projeção aleatória?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam a maldição da dimensionalidade, projeção, variedades, PCA, variância explicada, compressão, PCA incremental e técnicas não lineares.
</details>

---

### 7 - Como você pode avaliar o desempenho de um algoritmo de redução de dimensionalidade no seu conjunto de dados?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam a maldição da dimensionalidade, projeção, variedades, PCA, variância explicada, compressão, PCA incremental e técnicas não lineares.
</details>

---

### 8 - Faz sentido encadear dois algoritmos diferentes de redução de dimensionalidade?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam a maldição da dimensionalidade, projeção, variedades, PCA, variância explicada, compressão, PCA incremental e técnicas não lineares.
</details>

---

### 9 - Compare classificadores no MNIST com e sem PCA.

1. Carregue o MNIST, apresentado no capítulo 3. Separe as primeiras 60.000 instâncias para treinamento e as 10.000 restantes para teste.
2. Treine um classificador de floresta aleatória, meça o tempo de treinamento e avalie-o no conjunto de teste.
3. Aplique PCA para preservar 95% da variância. Treine outra floresta aleatória com os dados reduzidos e compare o tempo de treinamento. Houve aceleração?
4. Avalie o novo classificador no conjunto de teste e compare seu desempenho com o anterior.
5. Repita a comparação usando `SGDClassifier`. Quanto o PCA ajuda nesse caso?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício propõe reduzir o MNIST com PCA, treinar um classificador e comparar tempo de treinamento e desempenho com o conjunto original.
</details>

---

### 10 - Visualize o MNIST com t-SNE e compare outras técnicas.

1. Reduza as primeiras 5.000 imagens do MNIST a duas dimensões com t-SNE. Faça um gráfico de dispersão com Matplotlib, usando uma cor para cada dígito.
2. Experimente representar os pontos pelo número da classe ou por miniaturas das imagens. Evite sobreposição usando uma amostra aleatória ou exibindo uma instância apenas quando não houver outra próxima. Observe os agrupamentos formados.
3. Compare essa visualização com as obtidas usando PCA, LLE e MDS.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A proposta é reduzir uma amostra do MNIST para 2D com t-SNE e visualizar como os dígitos se agrupam no espaço reduzido.
</details>
