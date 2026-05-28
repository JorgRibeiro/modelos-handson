# Perguntas e Exercícios - Capítulo 7

<!-- Clique em "Minha Resposta" ou "Resposta do Livro" para expandir. -->

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

### 3 - É possível acelerar o treinamento de um ensemble de bagging distribuindo-o em diversos servidores? E quanto aos ensembles de pasting, boosting, florestas aleatórias ou stacking?

<details>
<summary><strong>Minha Resposta</strong></summary>

Sim. É possível acelerar o treinamento de um ensemble de bagging distribuindo seus preditores em diversos servidores, pois cada preditor é treinado de forma independente dos outros, geralmente usando subconjuntos diferentes do conjunto de treinamento.

O mesmo vale para ensembles de pasting e florestas aleatórias, já que seus preditores também podem ser treinados em paralelo. Já em ensembles de boosting, o treinamento é sequencial, pois cada novo preditor depende dos resultados do preditor anterior. Por isso, distribuir o treinamento em vários servidores não traz o mesmo ganho.

No caso de stacking, os preditores de uma mesma camada podem ser treinados em paralelo, mas uma camada só pode ser treinada depois que a camada anterior estiver concluída.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

É perfeitamente possível acelerar o treinamento de um ensemble de bagging distribuindo-o entre vários servidores, pois cada preditor do ensemble é independente dos demais. O mesmo vale para ensembles de pasting e para florestas aleatórias, pelo mesmo motivo. No entanto, em um ensemble de boosting, cada preditor é construído com base no preditor anterior; portanto, o treinamento é necessariamente sequencial, e não há ganho ao distribuir esse treinamento entre vários servidores. Em relação aos ensembles de stacking, todos os preditores de uma mesma camada são independentes entre si, então podem ser treinados em paralelo em vários servidores. Porém, os preditores de uma camada só podem ser treinados depois que todos os preditores da camada anterior tiverem sido treinados.
</details>

---

### 4 - Qual é a vantagem da avaliação OOB?

<details>
<summary><strong>Minha Resposta</strong></summary>

A principal vantagem da avaliação OOB é que ela permite estimar o desempenho de um ensemble de bagging sem precisar separar um conjunto de validação. Como cada preditor é treinado apenas em uma amostra do conjunto de treinamento, algumas instâncias ficam de fora do treino desse preditor. Essas instâncias OOB podem ser usadas para avaliá-lo.

Com estimadores suficientes, cada instância tende a ser OOB para vários preditores. Assim, é possível combinar as predições desses preditores para obter uma avaliação razoavelmente imparcial do ensemble, mantendo mais dados disponíveis para o treinamento.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Com a avaliação out-of-bag, cada preditor em um ensemble de bagging é avaliado usando instâncias nas quais ele não foi treinado, pois elas ficaram de fora da sua amostra de treinamento. Isso permite obter uma avaliação razoavelmente imparcial do ensemble sem a necessidade de um conjunto de validação adicional. Assim, há mais instâncias disponíveis para o treinamento, e o ensemble pode ter um desempenho ligeiramente melhor.
</details>

---

### 5 - O que faz com que os ensembles de árvores extras sejam mais aleatórios que as florestas aleatórias comuns? Como essa aleatoriedade extra pode ajudar? Os classificadores de árvores extras são mais lentos ou mais rápidos que as florestas aleatórias comuns?

<details>
<summary><strong>Minha Resposta</strong></summary>

Os ensembles de árvores extras são mais aleatórios porque, além de considerarem apenas um subconjunto aleatório de características em cada nó, eles também escolhem limites aleatórios para dividir os dados, em vez de procurar os melhores limites possíveis.

Essa aleatoriedade extra funciona como uma forma de regularização. Ela pode ajudar quando uma floresta aleatória está sobreajustando os dados de treinamento, pois tende a reduzir a variância, embora possa aumentar o viés. Os classificadores de árvores extras costumam ser mais rápidos de treinar do que as florestas aleatórias, porque não precisam procurar os melhores limites de divisão. Porém, na hora de fazer predições, eles não são necessariamente mais rápidos nem mais lentos.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Ao construir uma árvore em uma floresta aleatória, apenas um subconjunto aleatório das características é considerado para a divisão em cada nó. Isso também acontece com as árvores extras, mas elas vão um passo além: em vez de procurar os melhores limites possíveis, como fazem as árvores de decisão comuns, elas usam limites aleatórios para cada característica. Essa aleatoriedade extra atua como uma forma de regularização: se uma floresta aleatória estiver sobreajustando os dados de treinamento, as árvores extras podem ter desempenho melhor. Além disso, como as árvores extras não procuram os melhores limites possíveis, elas são muito mais rápidas de treinar do que as florestas aleatórias. No entanto, ao fazer predições, elas não são nem mais rápidas nem mais lentas que as florestas aleatórias.
</details>

---

### 6 - Se o seu ensemble do AdaBoost subajusta os dados de treinamento, quais hiperparâmetros você deve ajustar e como?

<details>
<summary><strong>Minha Resposta</strong></summary>

Se um ensemble do AdaBoost está subajustando os dados de treinamento, podemos tentar aumentar o número de estimadores. Também podemos reduzir a regularização do estimador base, permitindo que cada modelo individual seja um pouco mais flexível.

Outra opção é aumentar levemente a taxa de aprendizado, mas com cuidado, pois uma taxa muito alta pode prejudicar a generalização.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Se o seu ensemble do AdaBoost subajusta os dados de treinamento, você pode tentar aumentar o número de estimadores ou reduzir os hiperparâmetros de regularização do estimador base. Também pode tentar aumentar levemente a taxa de aprendizado.
</details>

---

### 7 - Caso o seu ensemble de Gradient Boosting sobreajuste o conjunto de treinamento, você deve aumentar ou diminuir a taxa de aprendizado?

<details>
<summary><strong>Minha Resposta</strong></summary>

Se um ensemble de Gradient Boosting está sobreajustando o conjunto de treinamento, devemos diminuir a taxa de aprendizado. Uma taxa menor faz com que cada novo preditor contribua de forma mais gradual, o que pode melhorar a generalização.

Também é possível usar early stopping para encontrar um número adequado de preditores, pois o sobreajuste pode indicar que há preditores demais no ensemble.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Se o seu ensemble de Gradient Boosting sobreajusta o conjunto de treinamento, você deve tentar diminuir a taxa de aprendizado. Também pode usar early stopping para encontrar o número adequado de preditores, pois provavelmente há preditores demais.
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
