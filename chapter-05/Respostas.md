# Perguntas e Exercícios - Capítulo 5

<!-- Clique em "Minha Resposta" ou "Resposta Oficial (Resumo)" para expandir. -->

### 1 - Qual é a ideia fundamental das máquinas de vetores de suporte (SVM)?

<details>
<summary><strong>Minha Resposta</strong></summary>

Ser um modelo robusto e versátil, englobando várias técnicas de aprendizado de máquina. Seu conceito principal gira em torno da fronteira de decisão: encontrar o espaço adequado para essa fronteira é sua principal tarefa.

Mais especificamente, a SVM busca separar as classes com a maior margem possível entre a fronteira de decisão e as instâncias de treinamento mais próximas.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A ideia fundamental por trás das máquinas de vetores de suporte é ajustar a "rua" mais larga possível entre as classes. Em outras palavras, o objetivo é ter a maior margem possível entre a fronteira de decisão que separa as duas classes e as instâncias de treinamento. Ao realizar classificação com margem suave, a SVM busca um compromisso entre separar perfeitamente as duas classes e manter a rua mais larga possível, isto é, algumas instâncias podem acabar ficando dentro da rua. Outra ideia importante é usar kernels ao treinar em conjuntos de dados não lineares. As SVMs também podem ser ajustadas para realizar regressão linear e não linear, além de detecção de novidades.
</details>

---

### 2 - O que é um vetor de suporte?

<details>
<summary><strong>Minha Resposta</strong></summary>

São instâncias localizadas na margem, ou seja, na "rua" criada pela SVM, incluindo suas bordas. Elas determinam a fronteira de decisão do modelo.

As instâncias que não são vetores de suporte não influenciam diretamente a fronteira de decisão, desde que permaneçam fora da margem.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Depois de treinar uma SVM, um _vetor de suporte_ é qualquer instância localizada na "rua" mencionada na resposta anterior, incluindo suas bordas. A fronteira de decisão é inteiramente determinada pelos vetores de suporte. Qualquer instância que não seja um vetor de suporte, isto é, que esteja fora da rua, não tem influência alguma: você poderia removê-la, adicionar mais instâncias ou movê-la, e desde que ela permaneça fora da rua, não afetará a fronteira de decisão. Calcular previsões com uma SVM com kernel envolve apenas os vetores de suporte, não todo o conjunto de treinamento.
</details>

---

### 3 - Por qual motivo é importante escalonar as entradas ao utilizar SVMs?

<details>
<summary><strong>Minha Resposta</strong></summary>

As SVMs são bem sensíveis ao escalonamento, então é essencial para um bom modelo que os dados sejam escalonados. Isso evita que características com escalas maiores dominem características com escalas menores, deixando a fronteira de decisão mais equilibrada e factível.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As SVMs tentam ajustar a maior "rua" possível entre as classes, como vimos na primeira resposta. Portanto, se o conjunto de treinamento não estiver escalonado, a SVM tenderá a negligenciar atributos com valores menores.
</details>

---

### 4 - Um classificador SVM pode gerar uma pontuação de confiança ao classificar uma instância? E quanto a uma probabilidade?

<details>
<summary><strong>Minha Resposta</strong></summary>

Sim, um classificador SVM pode gerar uma pontuação de confiança usando o método `decision_function()`. Essa pontuação indica a distância da instância até a fronteira de decisão.

Por padrão, essa pontuação não é uma probabilidade. Para obter probabilidades em um `SVC`, é preciso definir `probability=True`, o que faz o modelo usar validação cruzada internamente para calibrar essas pontuações e permitir o uso de `predict_proba()`.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Você pode usar o método `decision_function()` para obter pontuações de confiança. Essas pontuações representam a distância entre a instância e a fronteira de decisão. No entanto, elas não podem ser convertidas diretamente em uma estimativa de probabilidade de classe. Se você definir `probability=True` ao criar um `SVC`, então, ao final do treinamento, ele usará validação cruzada com 5 folds para gerar pontuações fora da amostra para as instâncias de treinamento, e treinará um modelo de `LogisticRegression` para mapear essas pontuações para probabilidades estimadas. Os métodos `predict_proba()` e `predict_log_proba()` ficarão disponíveis.
</details>

---

### 5 - Como escolher entre `LinearSVC`, `SVC` e `SGDClassifier`?

<details>
<summary><strong>Minha Resposta</strong></summary>

Usaria `LinearSVC` quando o problema for de classificação linear e eu quiser uma implementação otimizada para SVM linear.

Usaria `SVC` quando precisasse de kernels, por exemplo, em problemas não lineares. Ele é mais flexível, mas não escala tão bem para datasets com muitas instâncias.

Usaria `SGDClassifier` quando o conjunto de dados fosse muito grande, quando eu precisasse de treinamento incremental ou quando quisesse mais flexibilidade no processo de otimização.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As três classes podem ser usadas para classificação linear de margem larga. A classe `SVC` também suporta o truque do kernel, o que a torna capaz de lidar com tarefas não lineares. No entanto, isso tem um custo: a classe `SVC` não escala bem para datasets com muitas instâncias. Por outro lado, ela escala bem para um grande número de atributos. A classe `LinearSVC` implementa um algoritmo otimizado para SVMs lineares, enquanto `SGDClassifier` usa descida do gradiente estocástica. Dependendo do dataset, `LinearSVC` pode ser um pouco mais rápida que `SGDClassifier`, mas nem sempre; além disso, `SGDClassifier` é mais flexível e suporta aprendizado incremental.
</details>

---

### 6 - Digamos que você treinou um classificador SVM com kernel RBF, mas aparentemente ele subajusta o conjunto de treinamento. Você deve aumentar ou diminuir o _γ_ (`gamma`)? E o que fazer com o `C`?

<details>
<summary><strong>Minha Resposta</strong></summary>

No caso de subajuste, a atitude correta seria aumentar o valor de _γ_ (`gamma`) ou aumentar o valor de `C`, ou ambos.

Aumentar `gamma` deixa a curva em sino do kernel RBF mais estreita, fazendo com que cada instância tenha uma influência mais local. Isso permite uma fronteira de decisão mais irregular. Aumentar `C` reduz a regularização, permitindo que o modelo se ajuste melhor ao conjunto de treinamento.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Se um classificador SVM treinado com kernel RBF subajusta o conjunto de treinamento, pode haver regularização demais. Para diminuí-la, você precisa aumentar `gamma` ou `C`, ou ambos.
</details>

---

### 7 - O que significa um modelo ser insensível a _ε_?

<details>
<summary><strong>Minha Resposta</strong></summary>

Significa que, em uma SVM de regressão, erros menores que _ε_ não afetam o modelo. Ou seja, instâncias que ficam dentro da margem, ou dentro da "rua", não alteram a função aprendida.

A largura da rua é controlada por _ε_.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Um modelo de SVM de regressão tenta colocar o maior número possível de instâncias dentro de uma pequena margem ao redor de suas previsões. Se você adicionar instâncias dentro dessa margem, o modelo não será afetado: por isso dizemos que ele é _ε-insensitive_, ou insensível a _ε_.
</details>

---

### 8 - Para que usar o truque do kernel?

<details>
<summary><strong>Minha Resposta</strong></summary>

O truque do kernel serve para treinar modelos SVM não lineares sem precisar criar explicitamente todos os novos atributos.

Na prática, ele permite que o modelo se comporte como se os dados tivessem sido transformados para um espaço de dimensão maior, onde talvez seja possível separá-los com uma fronteira linear. A vantagem é obter esse efeito de forma eficiente, calculando apenas similaridades por meio do kernel.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O truque do kernel é uma técnica matemática que torna possível treinar um modelo SVM não linear. O modelo resultante é equivalente a mapear as entradas para outro espaço usando uma transformação não linear e, em seguida, treinar uma SVM linear nas entradas resultantes em alta dimensão. O truque do kernel fornece o mesmo resultado sem precisar transformar explicitamente as entradas.
</details>

---

### 9 - Treine um `LinearSVC` em um conjunto de dados linearmente separável. Depois, treine um `SVC` e um `SGDClassifier` no mesmo conjunto de dados. Veja se consegue fazer com que eles produzam aproximadamente o mesmo modelo.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício propõe treinar um classificador SVM linear para distinguir classes do Iris, comparar com `SVC(kernel="linear")` e `SGDClassifier`, e observar a importância do escalonamento.
</details>

---

### 10 - Treine um classificador SVM no conjunto de dados Wine, que pode ser carregado com `sklearn.datasets.load_wine()`. Esse conjunto contém a análise química de 178 amostras de vinho produzidas por 3 cultivadores diferentes. O objetivo é treinar um modelo de classificação capaz de prever o cultivador com base na análise química do vinho. Como classificadores SVM são classificadores binários, será necessário usar one-versus-all para classificar as 3 classes. Qual acurácia você consegue alcançar?

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A proposta é treinar SVMs no MNIST, ajustar hiperparâmetros e comparar desempenho e tempo de treinamento, lembrando que SVMs podem ser caras em conjuntos de dados grandes.
</details>

---

### 11 - Treine e ajuste um regressor SVM no conjunto de dados California Housing. Você pode usar o conjunto original, em vez da versão modificada usada no Capítulo 2. O conjunto original pode ser obtido com `sklearn.datasets.fetch_california_housing()`. Os alvos representam centenas de milhares de dólares. Como há mais de 20.000 instâncias, SVMs podem ser lentas; portanto, para o ajuste de hiperparâmetros, use bem menos instâncias, por exemplo 2.000, para testar mais combinações. Qual é o RMSE do seu melhor modelo?
<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício pede aplicar `SVR` ao problema de habitação da Califórnia, usando preparação adequada dos dados e busca de hiperparâmetros para comparar com modelos anteriores.
</details>
