# Perguntas e Exercícios - Capítulo 6

<!-- Clique em "Minha Resposta" ou "Resposta Oficial (Resumo)" para expandir. -->

### 1 - Qual é a profundidade aproximada de uma Árvore de Decisão treinada sem restrições em um conjunto de treinamento com 1 milhão de instâncias?

<details>
<summary><strong>Minha Resposta</strong></summary>

Para uma Árvore de Decisão treinada **sem restrições**, a profundidade aproximada é `log2(m)`, em que `m` é o número de instâncias de treino. Para `m = 1.000.000`, temos `log2(1.000.000) ≈ 20`. Na prática, pode ser um pouco maior, porque a árvore geralmente não fica perfeitamente balanceada.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A profundidade de uma árvore binária bem balanceada contendo _m_ folhas é igual a log₂(_m_), arredondado para cima. log₂ é o logaritmo binário; log₂(_m_) = log(_m_) / log(2). Uma Árvore de Decisão binária, isto é, uma árvore que toma apenas decisões binárias, como ocorre com todas as árvores no Scikit-Learn, terminará mais ou menos bem balanceada ao final do treinamento, com uma folha por instância de treinamento se for treinada sem restrições. Portanto, se o conjunto de treinamento contém um milhão de instâncias, a Árvore de Decisão terá profundidade log₂(10<sup>6</sup>) ≈ 20, na verdade um pouco maior, já que a árvore geralmente não será perfeitamente balanceada.
</details>

---

### 2 - A impureza de Gini de um nó costuma ser menor ou maior que a de seu pai? Ela é sempre menor?

<details>
<summary><strong>Minha Resposta</strong></summary>

Geralmente, a impureza de Gini de um nó filho é menor que a do nó pai, porque o algoritmo CART escolhe divisões que minimizam a soma ponderada das impurezas dos nós filhos.

Mas isso não é sempre verdade para cada filho individualmente. Um dos nós filhos pode ter impureza maior que a do pai, desde que o outro filho tenha uma impureza baixa o suficiente para compensar. O que precisa diminuir é a impureza ponderada total após a divisão.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A impureza de Gini de um nó geralmente é menor que a de seu pai. Isso acontece por causa da função de custo do algoritmo CART, que divide cada nó de uma forma que minimiza a soma ponderada das impurezas de Gini dos seus filhos.

No entanto, é possível que um nó tenha impureza de Gini maior que a de seu pai, desde que esse aumento seja mais do que compensado por uma diminuição na impureza do outro filho. Por exemplo, considere um nó contendo quatro instâncias da classe A e uma da classe B. Sua impureza de Gini é 1 - (1/5)^2 - (4/5)^2 = 0,32.

Agora suponha que o conjunto de dados seja unidimensional e que as instâncias estejam alinhadas nesta ordem: A, B, A, A, A. O algoritmo dividirá esse nó após a segunda instância, produzindo um nó filho com as instâncias A e B, e outro nó filho com as instâncias A, A e A. A impureza de Gini do primeiro filho é 1 - (1/2)^2 - (1/2)^2 = 0,5, maior que a impureza de seu pai. Isso é compensado pelo fato de que o outro nó é puro, então a impureza de Gini ponderada total é 2/5 x 0,5 + 3/5 x 0 = 0,2, que é menor que a impureza de Gini do pai.
</details>

---

### 3 - Caso uma Árvore de Decisão esteja sobreajustando o conjunto de treinamento, é uma boa ideia tentar diminuir `max_depth`?

<details>
<summary><strong>Minha Resposta</strong></summary>

Sim. Se uma Árvore de Decisão está sobreajustando o conjunto de treinamento, diminuir `max_depth` pode ajudar, pois limita a profundidade da árvore, reduz a complexidade do modelo e funciona como regularização. Com uma árvore menos profunda, as fronteiras de decisão tendem a ficar menos específicas ao conjunto de treino, o que pode melhorar a generalização.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Se uma Árvore de Decisão estiver sobreajustando o conjunto de treinamento, pode ser uma boa ideia diminuir `max_depth`, pois isso restringirá o modelo, regularizando-o.
</details>

---

### 4 - Se uma Árvore de Decisão subajusta o conjunto de treinamento, é uma boa ideia escalonar as características de entrada?

<details>
<summary><strong>Minha Resposta</strong></summary>

Não. Escalonar ou centralizar as características de entrada não deve resolver o subajuste de uma Árvore de Decisão, porque esse tipo de modelo não é sensível à escala dos atributos. Se a árvore está subajustando, o problema provavelmente está ligado a restrições excessivas ou baixa complexidade do modelo, como `max_depth` muito baixo, `min_samples_leaf` muito alto ou `max_leaf_nodes` muito baixo.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Árvores de Decisão não se importam se os dados de treinamento estão escalonados ou centralizados; essa é uma das vantagens delas. Portanto, se uma Árvore de Decisão está subajustando o conjunto de treinamento, escalonar as características de entrada será apenas uma perda de tempo.
</details>

---

### 5 - Se leva uma hora para treinar uma Árvore de Decisão em um conjunto de treinamento com 1 milhão de instâncias, quanto tempo levará aproximadamente para treinar outra Árvore de Decisão em um conjunto com 10 milhões de instâncias?

<details>
<summary><strong>Minha Resposta</strong></summary>

Levará aproximadamente 11,7 horas. O tempo não aumenta apenas 10 vezes, porque a complexidade de treino de uma Árvore de Decisão pelo CART é aproximadamente _O_(_n_ x _m_ log2(_m_)), em que _n_ é o número de características e _m_ é o número de instâncias. Mantendo _n_ constante e aumentando _m_ de 1 milhão para 10 milhões, o fator de aumento fica perto de 11,7.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A complexidade computacional para treinar uma Árvore de Decisão é _O_(_n_ x _m_ log2(_m_)). Então, se você multiplicar o tamanho do conjunto de treinamento por 10, o tempo de treinamento será multiplicado por `K = (n x 10m x log2(10m)) / (n x m x log2(m)) = 10 x log2(10m) / log2(m)`. Se _m_ = 10<sup>6</sup>, então _K_ ≈ 11,7. Portanto, você pode esperar que o tempo de treinamento seja aproximadamente 11,7 horas.
</details>

---

### 6 - Se leva uma hora para treinar uma Árvore de Decisão em determinado conjunto de treinamento, aproximadamente quanto tempo levará se você dobrar o número de características?

<details>
<summary><strong>Minha Resposta</strong></summary>

Irá demorar aproximadamente o dobro do tempo, ou seja, cerca de 2 horas. Isso acontece porque a complexidade de treinamento do algoritmo CART é aproximadamente _O_(_n_ x _m_ log2(_m_)), em que _n_ é o número de características e _m_ é o número de instâncias. Se apenas _n_ dobra, mantendo _m_ igual, o tempo de treinamento também tende a dobrar.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Se o número de características dobrar, então o tempo de treinamento também será aproximadamente dobrado.
</details>

---


### 7 - Treine e aperfeiçoe uma Árvore de Decisão no conjunto moons

**Etapas:**

a. Use `make_moons(n_samples=1000, noise=0.4)` para gerar um conjunto de treinamento moons.

b. Utilize `train_test_split()` para dividir os dados em conjunto de treinamento e conjunto de teste.

c. Use grid search com validação cruzada, por meio da classe `GridSearchCV`, para encontrar bons valores de hiperparâmetros para `DecisionTreeClassifier`. Dica: experimente diversos valores para `max_leaf_nodes`.

d. Treine o modelo em todo o conjunto de treinamento usando esses hiperparâmetros e avalie a performance no conjunto de teste. Você deve obter aproximadamente de 85% a 87% de acurácia.


<details>
<summary><strong>Minha Resposta</strong></summary>

Foi gerado um conjunto de dados moons com `make_moons(n_samples=1000, noise=0.4)` e, em seguida, os dados foram divididos em treino e teste com `train_test_split`. Depois, foi usado `GridSearchCV` com validação cruzada para testar diferentes valores de `max_leaf_nodes` e de `max_depth` em uma `DecisionTreeClassifier`.

O melhor modelo encontrado foi avaliado no conjunto de teste usando `accuracy_score`, obtendo acurácia de aproximadamente 85,5%, dentro da faixa esperada pelo exercício. Também foi treinada uma árvore padrão, sem ajuste de hiperparâmetros, para comparação. A árvore ajustada teve desempenho melhor, mostrando que a busca de hiperparâmetros ajudou a reduzir o sobreajuste e melhorar a generalização.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício propõe gerar um conjunto com `make_moons`, dividir treino/teste, usar busca de hiperparâmetros em `DecisionTreeClassifier` e medir o desempenho no conjunto de teste.
</details>

---

### 8 - Crie uma floresta manual a partir de várias Árvores de Decisão

**Etapas:**

a. Dando continuidade ao exercício anterior, gere 1000 subconjuntos do conjunto de treinamento, cada um contendo 100 instâncias selecionadas aleatoriamente. Dica: você pode usar a classe `ShuffleSplit` do Scikit-Learn.

b. Treine uma Árvore de Decisão em cada subconjunto, usando os melhores valores de hiperparâmetros encontrados no exercício anterior. Avalie essas 1000 árvores no conjunto de teste. Como foram treinadas em conjuntos menores, elas provavelmente terão desempenho pior que o da primeira Árvore de Decisão, atingindo cerca de 80% de acurácia.

c. Para cada instância do conjunto de teste, gere as predições das 1000 Árvores de Decisão e mantenha apenas a predição mais frequente. Você pode usar a função `mode()` do SciPy. Essa abordagem fornece as predições por voto majoritário no conjunto de teste.

d. Avalie essas predições no conjunto de teste. Você deve obter uma acurácia um pouco maior que a do primeiro modelo, cerca de 0,5% a 1,5% maior. Com isso, você treinou manualmente um classificador de Floresta Aleatória.

<details>
<summary><strong>Minha Resposta</strong></summary>

Foi criada uma floresta manual a partir de 1000 Árvores de Decisão. Primeiro, foram gerados 1000 subconjuntos aleatórios do conjunto de treinamento com `ShuffleSplit`, cada um contendo 100 instâncias. Em seguida, foi treinada uma árvore em cada subconjunto usando os melhores hiperparâmetros encontrados no exercício anterior.

Cada árvore individual foi avaliada no conjunto de teste, obtendo em média cerca de 81,1% de acurácia, abaixo da árvore ajustada treinada com todo o conjunto de treinamento. Depois, as previsões das 1000 árvores foram combinadas por voto majoritário usando `mode()` do SciPy. Com essa agregação, a acurácia final subiu para aproximadamente 86,0%, um ganho de 0,5 ponto percentual em relação ao primeiro modelo, que tinha cerca de 85,5% de acurácia.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A ideia é treinar várias árvores em subconjuntos aleatórios do treino, combinar suas previsões por votação majoritária e observar como a agregação melhora a estabilidade.
</details>
