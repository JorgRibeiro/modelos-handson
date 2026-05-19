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

### 4 - Pergunta.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam margem, vetores de suporte, margem suave, kernels, regularização, escalonamento de atributos e uso de SVMs para classificação e regressão.
</details>

---

### 5 - Pergunta.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam margem, vetores de suporte, margem suave, kernels, regularização, escalonamento de atributos e uso de SVMs para classificação e regressão.
</details>

---

### 6 - Pergunta.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam margem, vetores de suporte, margem suave, kernels, regularização, escalonamento de atributos e uso de SVMs para classificação e regressão.
</details>

---

### 7 - Pergunta.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam margem, vetores de suporte, margem suave, kernels, regularização, escalonamento de atributos e uso de SVMs para classificação e regressão.
</details>

---

### 8 - Perguntas.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

As perguntas revisam margem, vetores de suporte, margem suave, kernels, regularização, escalonamento de atributos e uso de SVMs para classificação e regressão.
</details>

---

### 9 - Treine um `LinearSVC` no conjunto de dados Iris.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício propõe treinar um classificador SVM linear para distinguir classes do Iris, comparar com `SVC(kernel="linear")` e `SGDClassifier`, e observar a importância do escalonamento.
</details>

---

### 10 - Treine uma SVM no MNIST.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

A proposta é treinar SVMs no MNIST, ajustar hiperparâmetros e comparar desempenho e tempo de treinamento, lembrando que SVMs podem ser caras em conjuntos de dados grandes.
</details>

---

### 11 - Treine uma SVM de regressão no California Housing.

<details>
<summary><strong>Minha Resposta</strong></summary>

*(Resposta em construção.)*
</details>

<details>
<summary><strong>Resposta Oficial (Resumo)</strong></summary>

O exercício pede aplicar `SVR` ao problema de habitação da Califórnia, usando preparação adequada dos dados e busca de hiperparâmetros para comparar com modelos anteriores.
</details>
