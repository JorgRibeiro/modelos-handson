# Perguntas e Exercícios - Capítulo 7

<!-- Clique em "Minha Resposta" ou "Resposta Oficial (Resumo)" para expandir. -->

### 1 - Se você treinou cinco modelos diferentes com exatamente os mesmos dados de treinamento e todos alcançaram 95% de precisão, há alguma chance de combinar esses modelos para obter melhores resultados? Em caso afirmativo, como? Se não, por quê?

<details>
<summary><strong>Minha Resposta</strong></summary>

Sim. Podemos combinar os cinco modelos usando um ensemble por votação. Nesse caso, cada modelo faz sua predição e a classe mais votada é escolhida como a saída final. Esse método pode produzir resultados melhores do que os modelos individuais, principalmente se os modelos forem bem diferentes entre si, pois seus erros tendem a ser menos correlacionados. O ensemble pode melhorar ainda mais se os modelos também forem treinados em subconjuntos diferentes dos dados, como acontece em métodos de bagging e pasting.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Se você treinou cinco modelos diferentes e todos alcançaram 95% de precisão, pode tentar combiná-los em um ensemble por votação, o que frequentemente produzirá resultados ainda melhores. Isso funciona melhor quando os modelos são bem diferentes entre si, por exemplo, um classificador SVM, uma Árvore de Decisão, uma Regressão Logística e assim por diante. É ainda melhor se eles forem treinados em instâncias de treinamento diferentes, que é justamente a ideia dos ensembles de bagging e pasting. Mesmo assim, se isso não for possível, a combinação ainda pode ser eficaz desde que os modelos sejam bastante diferentes.
</details>

---

### 2 - Qual é a diferença entre classificadores por votação rígida e votação suave?

<details>
<summary><strong>Minha Resposta</strong></summary>

Em um classificador por votação rígida, cada modelo vota em uma classe, e a classe mais votada é escolhida como a resposta final. Ou seja, a decisão considera apenas a classe prevista por cada modelo.

Já em um classificador por votação suave, cada modelo informa as probabilidades estimadas para cada classe. Essas probabilidades são combinadas, geralmente pela média, e a classe com a maior probabilidade média é escolhida como resposta final. Esse método dá mais peso às predições em que os modelos estão mais confiantes, mas só funciona se todos os classificadores conseguirem estimar probabilidades.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Um classificador por votação rígida simplesmente conta os votos de cada classificador no ensemble e escolhe a classe que recebe mais votos. Um classificador por votação suave calcula a média das probabilidades estimadas por cada classificador para cada classe e escolhe a classe com a maior probabilidade. Isso dá mais peso aos votos de alta confiança e geralmente apresenta melhor desempenho, mas só funciona se todos os classificadores forem capazes de estimar probabilidades de classe. Por exemplo, em classificadores SVM no Scikit-Learn, é necessário definir `probability=True`.
</details>

---

### 8 - Treine um classificador por votação.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício propõe treinar vários classificadores no MNIST, combinar suas previsões com `VotingClassifier` e comparar o ensemble com os modelos individuais.
</details>

---

### 9 - Treine um ensemble com stacking.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A proposta é usar previsões de modelos de base como atributos para um classificador final, treinando um ensemble de stacking e comparando seu desempenho.
</details>
