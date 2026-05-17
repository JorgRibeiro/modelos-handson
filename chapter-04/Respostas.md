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

Os algoritmos de Gradiente Descendente tendem a ter dificuldades quando o conjunto de treinamento não está escalonado, pois ele irá demorar muito para convergir. Ou seja, ele irá encontrar o mínimo local, mas demorará muito.

A melhor alternativa para contornar esse problema é garantir que os dados tenham uma escala semelhante.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Se as características do conjunto de treinamento tiverem escalas muito diferentes, a função de custo terá o formato de uma tigela alongada, então os algoritmos de descida do gradiente levarão muito tempo para convergir. Para resolver isso, você deve escalonar os dados antes de treinar o modelo. Observe que a Equação Normal ou a abordagem por SVD funcionam sem problemas mesmo sem escalonamento. Além disso, modelos regularizados podem convergir para uma solução subótima se as características não forem escalonadas: como a regularização penaliza pesos grandes, características com valores menores tendem a ser ignoradas em comparação com características com valores maiores.
</details>

---

### 3 - O gradiente descendente pode ficar empacado em um mínimo local quando treinamos um modelo de regressão logística?

<details>
<summary><strong>Minha Resposta</strong></summary>

Não, pois a função de custo é convexa. O gradiente descendente converge para o mínimo global se a taxa de aprendizado não for muito grande e se você esperar o suficiente.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O gradiente descendente não pode ficar preso em um mínimo local ao treinar um modelo de regressão logística, porque a função de custo é convexa. _Convexa_ significa que, se você desenhar uma linha reta entre dois pontos quaisquer da curva, essa linha nunca cruza a curva.
</details>

---

### 4 - Todos os algoritmos do gradiente descendente resultam no mesmo modelo, contanto que você os execute por tempo suficiente?

<details>
<summary><strong>Minha Resposta</strong></summary>

Todos os algoritmos chegam perto do mínimo, mas não necessariamente ao mesmo modelo. O GD em minibatch pode se deslocar para um pouco mais perto do mínimo que o estocástico, mas ambos podem ficar oscilando ao redor do mínimo se a taxa de aprendizado não for reduzida gradualmente. O GD em batch segue um caminho mais direto para o mínimo, enquanto os outros fazem um caminho mais aleatório.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Se o problema de otimização for convexo, como na regressão linear ou na regressão logística, e assumindo que a taxa de aprendizado não seja alta demais, todos os algoritmos de descida do gradiente se aproximarão do ótimo global e acabarão produzindo modelos bastante parecidos. No entanto, a menos que você reduza gradualmente a taxa de aprendizado, a descida do gradiente estocástica e a descida do gradiente em mini-lotes nunca convergirão de verdade; em vez disso, continuarão saltando para frente e para trás ao redor do ótimo global. Isso significa que, mesmo que você os execute por muito tempo, esses algoritmos de descida do gradiente produzirão modelos ligeiramente diferentes.
</details>

---

### 5 - Suponha que você utilize o gradiente descendente em batch e plote o erro de validação em cada época. Caso perceba que o erro de validação aumenta constantemente, o que provavelmente está acontecendo? Como consertar isso?

<details>
<summary><strong>Minha Resposta</strong></summary>

A taxa de aprendizado está desalinhada com o modelo, provavelmente estando muito alta. A melhor forma de consertar isso é encontrar uma boa taxa de aprendizado, usando grid search.

Mas, se o erro de treinamento não estiver aumentando, então o modelo provavelmente está sofrendo overfitting. Nesse caso, o ideal é parar o treinamento.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>
Se o erro de validação aumenta consistentemente após cada época, uma possibilidade é que a taxa de aprendizado esteja alta demais e o algoritmo esteja divergindo. Se o erro de treinamento também estiver aumentando, então esse é claramente o problema, e você deve reduzir a taxa de aprendizado. No entanto, se o erro de treinamento não estiver aumentando, então o modelo está sofrendo overfitting no conjunto de treinamento, e você deve parar o treinamento.
</details>

---

### 6 - É uma boa parar o gradiente descendente em minibatch logo que o erro de validação aumenta?

<details>
<summary><strong>Minha Resposta</strong></summary>

Não, pois ele ainda está explorando a região do mínimo. Por usar mini-lotes aleatórios, ele tende a ter maior aleatoriedade na busca, causando instabilidade no erro de validação.

O melhor é esperar um tempo sem melhora e manter salvo o melhor modelo encontrado.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Devido à sua natureza aleatória, nem a descida do gradiente estocástica nem a descida do gradiente em mini-lotes têm garantia de progresso em cada iteração de treinamento. Portanto, se você parar o treinamento imediatamente quando o erro de validação aumentar, poderá parar cedo demais, antes que o ótimo seja alcançado. Uma opção melhor é salvar o modelo em intervalos regulares; então, quando ele não melhorar por bastante tempo, o que significa que provavelmente não baterá mais o melhor resultado, você pode voltar ao melhor modelo salvo.
</details>

---

### 7 - Qual o algoritmo do gradiente descendente (entre os que discutimos) chegará mais rápido e próximo da solução ideal? Qual deles convergirá? Como você pode fazer os outros convergirem também?

<details>
<summary><strong>Minha Resposta</strong></summary>

O algoritmo que concilia tempo e precisão é o GD em minibatch, pois ele utiliza características dos dois algoritmos vistos. Porém, o GD estocástico costuma chegar mais rápido perto da solução, enquanto o GD em batch vai mais devagar, mas converge de forma mais estável. O GD estocástico e o GD em minibatch podem ficar oscilando ao redor da solução; para fazê-los convergir, é necessário reduzir gradualmente a taxa de aprendizado.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>
A descida do gradiente estocástica tem a iteração de treinamento mais rápida, pois considera apenas uma instância de treinamento por vez. Por isso, geralmente é a primeira a chegar à vizinhança do ótimo global, ou então a descida do gradiente em mini-lotes com um tamanho de mini-lote muito pequeno. No entanto, apenas a descida do gradiente em batch realmente convergirá, dado tempo de treinamento suficiente. Como mencionado, a descida do gradiente estocástica e a descida do gradiente em mini-lotes ficarão saltando ao redor do ótimo, a menos que você reduza gradualmente a taxa de aprendizado.
</details>

---

### 8 - Imagine que esteja usando a regressão polinomial. Você plota as curvas de aprendizado e percebe que existe uma lacuna enorme entre o erro de treinamento e o erro de validação. O que está acontecendo? Quais são as três formas de resolver isso?

<details>
<summary><strong>Minha Resposta</strong></summary>

Provavelmente o modelo está sofrendo de overfitting. Entre as formas de resolver estão:

- reduzir o grau da regressão polinomial;
- aplicar regularização, como Ridge ou Lasso;
- aumentar o tamanho do conjunto de treinamento.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Se o erro de validação é muito maior que o erro de treinamento, isso provavelmente acontece porque o modelo está sofrendo overfitting no conjunto de treinamento. Uma forma de tentar corrigir isso é reduzir o grau polinomial: um modelo com menos graus de liberdade tem menor chance de sofrer overfitting. Outra coisa que você pode tentar é regularizar o modelo, por exemplo, adicionando uma penalidade ℓ₂ (Ridge) ou uma penalidade ℓ₁ (Lasso) à função de custo. Isso também reduz os graus de liberdade do modelo. Por fim, você pode tentar aumentar o tamanho do conjunto de treinamento.
</details>

---

### 9 - Suponha que você esteja usando a Regressão Ridge e note que o erro de treinamento e o erro de validação são quase iguais e bem altos. Você diria que o modelo tem um viés alto ou uma variância alta? Você deve aumentar o hiperparâmetro alpha da regularização ou reduzi-lo?

<details>
<summary><strong>Minha Resposta</strong></summary>
O modelo tem um viés alto. Você deve reduzir o hiperparâmetro alpha da regularização.

</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Se tanto o erro de treinamento quanto o erro de validação são quase iguais e bastante altos, o modelo provavelmente está sofrendo underfitting no conjunto de treinamento, o que significa que ele tem um viés alto. Você deve tentar reduzir o hiperparâmetro de regularização _α_.
</details>

---

### 10 - Por que você usaria:
###    a. A regressão Ridge em vez da regressão linear simples (ou seja, sem qualquer regularização)?
###    b. A regressão Lasso em vez da regressão Ridge?
###    c. A regressão Elastic Net em vez da regressão Lasso?

<details>
<summary><strong>Minha Resposta</strong></summary>

a. Usaria a regressão Ridge em vez da regressão linear simples quando eu quisesse reduzir overfitting. A Ridge adiciona regularização, penalizando pesos muito grandes e ajudando o modelo a generalizar melhor.

b. Usaria a regressão Lasso em vez da Ridge quando eu suspeitasse que poucas características são realmente importantes. A Lasso usa regularização L1, que pode zerar alguns pesos e, assim, fazer seleção automática de atributos.

c. Usaria a regressão Elastic Net em vez da Lasso quando eu quisesse combinar os efeitos da Ridge e da Lasso. Ela é útil quando há características muito correlacionadas ou quando existem muitas características em relação ao número de exemplos, pois tende a ser mais estável que a Lasso pura.
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

Vejamos:

- Um modelo com alguma regularização geralmente tem desempenho melhor do que um modelo sem nenhuma regularização, então normalmente é melhor preferir a regressão Ridge à regressão linear simples.
- A regressão Lasso usa uma penalidade ℓ₁, que tende a empurrar os pesos exatamente para zero. Isso gera modelos esparsos, nos quais todos os pesos são zero, exceto os pesos mais importantes. Essa é uma forma de fazer seleção automática de atributos, o que é bom se você suspeita que apenas poucas características realmente importam. Quando não tiver certeza, prefira a regressão Ridge.
- A Elastic Net geralmente é preferível à Lasso, pois a Lasso pode se comportar de forma instável em alguns casos, por exemplo, quando várias características são fortemente correlacionadas ou quando há mais características do que instâncias de treinamento. No entanto, ela adiciona um hiperparâmetro extra para ajustar. Se você quiser usar Lasso sem esse comportamento instável, pode usar Elastic Net com `l1_ratio` próximo de 1.
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
