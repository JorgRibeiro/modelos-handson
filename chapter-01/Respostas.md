# Perguntas — Capítulo 1

<!-- Clique em 'Minha Resposta' ou 'Resposta do Livro' para expandir -->

### 1 - Como você definiria Machine Learning?

<details>
<summary><strong>Minha Resposta</strong></summary>

ML é construir sistemas que aprendem com dados, melhorando seu desempenho em uma tarefa conforme uma medida de desempenho.

Exemplos: Algoritmo de spam (aprende com e-mails rotulados); Recomendação de filmes (aprende com histórico de visualizações).

Palavras-chave: supervised learning, unsupervised learning, reinforcement learning, features, labels, generalization.
Referências: Cap. 1 (Tipos de Aprendizado ML).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

**Machine Learning (Aprendizado de Máquina)** trata da construção de sistemas capazes de aprender a partir de dados. Aprender significa melhorar em alguma tarefa, considerando uma determinada **performance measure (métrica de desempenho)**.
</details>

---

### 2 - Você consegue apontar quatro tipos de aplicações que se destacam?

<details>
<summary><strong>Minha Resposta</strong></summary>

Classificação (gato/cachorro com CNN), Detecção de fraudes (transações suspeitas com Isolation Forest), Regressão (preços de casas com Linear Regression), Classificação de texto (spam/não spam com Naive Bayes), Sistemas de recomendação (filmes com KNN), Clustering (clientes com KMeans), Forecast (demanda com ARIMA), Detecção de objetos (pedestres com YOLO).

Exemplos: Classificação de imagens com CNNs (acurácia/F1); Detecção de anomalias com Random Forest (AUC-ROC).

Palavras-chave: CNNs, Random Forest, Linear Regression, SVM, KMeans, ARIMA, YOLO, acurácia, F1, RMSE, MAE.
Referências: Cap. 3 (classificação), Cap. 4 (regressão), Cap. 8 (clustering), Cap. 9 (aprendizado não supervisionado).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

**Machine Learning** é excelente para problemas complexos para os quais não temos uma solução algorítmica clara, para substituir longas listas de regras ajustadas manualmente, para construir sistemas que se adaptam a ambientes variáveis e, por fim, para ajudar humanos a aprenderem, por exemplo, por meio de **data mining (mineração de dados)**.
</details>

---

### 3 - O que é um conjunto de treinamento rotulado (labeled training set)?

<details>
<summary><strong>Minha Resposta</strong></summary>

Conjunto de dados onde cada instância tem entrada (features) e saída (label) conhecida; essencial para tarefas supervisionadas.

Exemplos: E-mails rotulados (spam/não spam), Casas com preço real de venda, Diagnósticos médicos (doença sim/não).

Palavras-chave: labeled training set, features, labels, targets, supervised learning, qualidade de rótulos, ruído nos dados.
Referências: Cap. 1 (Tipos de Aprendizado), Cap. 2 (Projeto End-to-End).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Um **labeled training set (conjunto de treinamento rotulado)** é um conjunto de treinamento que contém a solução desejada, também chamada de **label (rótulo)**, para cada **instance (instância)**.
</details>

---

### 4 - Quais são as duas tarefas supervisionadas mais comuns?

<details>
<summary><strong>Minha Resposta</strong></summary>

**Classificação** (output discreto: categoria) e **Regressão** (output contínuo: número).

Exemplos: Classificação com Decision Trees (e-mail spam/não spam), Regressão com Linear Regression (preço de casa).

Palavras-chave: categorical output, continuous output, Decision Trees, Random Forest, SVM, Logistic Regression, Linear Regression, Ridge/Lasso, acurácia, F1, RMSE, MAE.
Referências: Cap. 3 (Classificação), Cap. 4 (Regressão Linear).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

As duas tarefas **supervised (supervisionadas)** mais comuns são **regression (regressão)** e **classification (classificação)**.
</details>

---

### 5 - Cite tarefas comuns em aprendizado não supervisionado.

<details>
<summary><strong>Minha Resposta</strong></summary>

Tarefas não supervisionadas comuns: **Clustering** (agrupar dados similares), **Visualização** e **Redução de Dimensionalidade** (simplificar dados), **Detecção de Anomalias** (identificar instâncias atípicas) e **Regras de Associação** (descobrir relações entre atributos).

Exemplos: KMeans para segmentar clientes; PCA para visualização; Isolation Forest para detectar fraudes (anomalias); Apriori para regras de associação ("picanha e carvão").

Palavras-chave: clustering, visualization, dimensionality reduction, anomaly detection, association rules, KMeans, PCA, Isolation Forest, Apriori.
Referências: Cap. 8 (Redução de Dimensionalidade), Cap. 9 (Aprendizado Não Supervisionado e Detecção de Anomalias).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Tarefas **unsupervised (não supervisionadas)** comuns incluem **clustering (agrupamento)**, visualização, redução de dimensionalidade e aprendizado de regras de associação.
</details>

---

### 6 - Para ensinar um robô a caminhar em terrenos desconhecidos, qual abordagem de aprendizado é, em geral, mais adequada? Por quê?

<details>
<summary><strong>Minha Resposta</strong></summary>

**Aprendizado por Reforço** (Reinforcement Learning). Neste contexto, o robô atua como um **agente** (agent) que observa um **ambiente** (environment) desconhecido e toma ações. Através de erro e acerto (recompensas e penalidades), ele aprende a melhor **política** (policy) — a estratégia determinando qual ação tomar em cada situação para otimizar a caminhada.

Exemplos: Robôs aprendendo a caminhar, AlphaGo (DeepMind) jogando Go, carros autônomos otimizando trajetos.

Palavras-chave: reinforcement learning, agent, environment, actions, rewards, penalties, policy.
Referências: Cap. 1 (Tipos de Aprendizado), Cap. 18 (Reinforcement Learning).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

**Reinforcement Learning (Aprendizado por Reforço)** provavelmente terá o melhor desempenho se quisermos que um robô aprenda a andar em vários terrenos desconhecidos, já que esse é tipicamente o tipo de problema tratado por **Reinforcement Learning**. Talvez fosse possível expressar o problema como um problema de **supervised learning (aprendizado supervisionado)** ou **semi-supervised learning (aprendizado semissupervisionado)**, mas isso seria menos natural.
</details>

---

### 7 - Que tipo de algoritmo você utilizaria para segmentar seus clientes em diversos grupos? Por quê?

<details>
<summary><strong>Minha Resposta</strong></summary>

Depende do conhecimento prévio sobre os grupos: 
Se você **não sabe** quais são os grupos, utiliza-se **Agrupamento (Clustering)** (Aprendizado Não Supervisionado). 
Se você **já sabe** quais grupos deseja e tem dados rotulados, utiliza-se **Classificação** (Aprendizado Supervisionado).

Exemplos: KMeans para agrupar clientes por similaridade sem rótulos (Clustering); Regressão Logística para classificar clientes em "premium", "básico" ou "gratuito" com base em dados passados (Classificação).

Palavras-chave: clustering, classification, supervised learning, unsupervised learning, customer segmentation.
Referências: Cap. 1 (Tipos de Aprendizado).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Se você não sabe como definir os grupos, então pode usar um algoritmo de **clustering** para segmentar seus clientes em **clusters (grupos)** de clientes semelhantes. No entanto, se você sabe quais grupos deseja ter, pode fornecer muitos exemplos de cada grupo a um algoritmo de **classification**, e ele classificará todos os seus clientes nesses grupos.
</details>

---

### 8 - O problema de detecção de spam é tipicamente um problema de que tipo de aprendizado? Explique.

<details>
<summary><strong>Minha Resposta</strong></summary>

**Aprendizado Supervisionado** (Supervised Learning). Trata-se de um problema de Classificação, pois o algoritmo é alimentado com dados que já contêm a resposta correta ("spam" ou "não spam"), ou seja, dados rotulados.

Exemplos: Naive Bayes, Support Vector Machines (SVM) ou Regressão Logística treinados em uma base de e-mails já classificados por usuários.

Palavras-chave: supervised learning, classification, labels, spam filtering.
Referências: Cap. 1 (Tipos de Aprendizado), Cap. 3 (Classificação).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Detecção de spam é um problema típico de **supervised learning**: o algoritmo recebe muitos e-mails junto com seus **labels**, indicando se são spam ou não são spam.
</details>

---

### 9 - O que caracteriza um sistema de aprendizado online em comparação com um sistema batch?

<details>
<summary><strong>Minha Resposta</strong></summary>

**Aprendizado Online (Incremental):** Aprende de forma contínua e incremental (a cada amostra ou em minilotes), permitindo adaptar-se rapidamente a novos dados e evoluir em produção. Também é essencial para treinar em quantidades massivas de dados que não cabem na memória (out-of-core). **Batch Learning (Lote):** Treinado com todos os dados de uma vez. Ao entrar em produção ele não aprende mais (mantém o mesmo comportamento), precisando ser retreinado do zero para se atualizar.

Exemplos: Sistema de recomendação ajustando preferências no momento do clique (Online); Modelo de risco de crédito retreinado todo fim de mês (Batch).

Palavras-chave: online learning, batch learning, incremental learning, out-of-core, data decay.
Referências: Cap. 1 (Tipos de Aprendizado).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Um sistema de **online learning (aprendizado online)** pode aprender de forma incremental, ao contrário de um sistema de **batch learning (aprendizado em lote)**. Isso o torna capaz de se adaptar rapidamente tanto a dados em mudança quanto a sistemas autônomos, além de permitir o treinamento com quantidades muito grandes de dados.
</details>

---

### 10 - O que são algoritmos out-of-core e quando são necessários?

<details>
<summary><strong>Minha Resposta</strong></summary>

**Algoritmos Out-of-core:** São utilizados quando o volume de dados é imenso e não cabe na memória principal (RAM) do computador. Eles dividem os dados em **minilotes (mini-batches)** e utilizam técnicas de **Aprendizado Online** para treinar o modelo de forma incremental nesses pedaços.

Exemplos: Treinar um classificador de imagens com uma base de 500GB em um laptop com 16GB de RAM usando o SGDClassifier incrementalmente.

Palavras-chave: out-of-core learning, mini-batches, online learning, memory limitation, RAM.
Referências: Cap. 1 (Tipos de Aprendizado).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Algoritmos **out-of-core (fora da memória principal)** conseguem lidar com quantidades enormes de dados que não cabem na memória principal do computador. Um algoritmo de aprendizado **out-of-core** divide os dados em **mini-batches (minilotes)** e usa técnicas de **online learning** para aprender a partir desses **mini-batches**.
</details>

---

### 11 - Qual tipo de aprendizado depende de uma medida de similaridade para fazer previsões?

<details>
<summary><strong>Minha Resposta</strong></summary>

**Aprendizado Baseado em Instâncias** (Instance-based learning). Esse sistema aprende "decorando" (memorizando) os dados de treinamento e, quando recebe um dado novo, utiliza uma **medida de similaridade** para compará-lo com as instâncias já aprendidas para realizar a previsão.

Exemplos: K-Nearest Neighbors (KNN), onde um novo dado é classificado com base na semelhança (distância) com seus vizinhos mais próximos memorizados do conjunto de treinamento.

Palavras-chave: instance-based learning, similarity measure, memorization, KNN.
Referências: Cap. 1 (Tipos de Aprendizado).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Um sistema de **instance-based learning (aprendizado baseado em instâncias)** aprende os dados de treinamento “de cor”. Depois, quando recebe uma nova **instance**, ele usa uma medida de similaridade para encontrar as instâncias aprendidas mais parecidas e usa essas instâncias para fazer previsões.
</details>

---

### 12 - Qual a diferença entre parâmetro de modelo e o hiperparâmetro do modelo?

<details>
<summary><strong>Minha Resposta</strong></summary>

**Parâmetro de modelo:** Variável interna (ex: pesos) que o modelo ajusta/otimiza durante o treinamento para fazer predições. **Algoritmo de aprendizado:** O mecanismo/metodologia que analisa os dados para encontrar os melhores valores para esses parâmetros. **Hiperparâmetro:** Configuração do próprio *algoritmo de aprendizado* definida *antes* de iniciar o treinamento, que controla como o aprendizado acontece (ex: não é alterado pelo modelo durante o treino).

Exemplos: Na Regressão Linear, o **peso/inclinação da reta** é o parâmetro; o **Gradient Descent** (ou função de custo) é parte do algoritmo de aprendizado; a **taxa de aprendizado (learning rate)** ou o grau de regularização (Ridge/Lasso) é o hiperparâmetro.

Palavras-chave: model parameter, learning algorithm, hyperparameter, weights, regularization.
Referências: Cap. 1 (Tipos de Aprendizado).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Um modelo possui um ou mais **model parameters (parâmetros do modelo)** que determinam o que ele irá prever ao receber uma nova **instance**, por exemplo, a inclinação de um modelo linear. Um algoritmo de aprendizado tenta encontrar valores ideais para esses parâmetros, de modo que o modelo **generalizes well (generalize bem)** para novas instâncias. Um **hyperparameter (hiperparâmetro)** é um parâmetro do próprio algoritmo de aprendizado, não do modelo, por exemplo, a quantidade de **regularization (regularização)** a ser aplicada.
</details>

---

### 13 - Para que servem algoritmos de aprendizado baseados em modelos? Qual é a estratégia mais comum que eles utilizam para serem bem-sucedidos? Como fazem previsões?

<details>
<summary><strong>Minha Resposta</strong></summary>

**Aprendizado Baseado em Modelos** (Model-based learning). Servem para generalizar a partir de exemplos construindo um modelo matemático (uma representação do problema). A estratégia principal para ter sucesso é otimizar os **parâmetros do modelo** minimizando uma **função de custo** (o erro do modelo) ou maximizando uma função de utilidade. Para fazer previsões, as *features* da nova instância são inseridas na função matemática do modelo usando os parâmetros já otimizados.

Exemplos: Regressão Linear otimizando a reta de melhor ajuste para prever preços; Redes Neurais ajustando seus pesos e vieses para classificar imagens.

Palavras-chave: model-based learning, cost function, utility function, optimization, generalization.
Referências: Cap. 1 (Tipos de Aprendizado).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Algoritmos de **model-based learning (aprendizado baseado em modelos)** procuram um valor ideal para os **model parameters**, de modo que o modelo **generalizes well** para novas instâncias. Normalmente treinamos esses sistemas minimizando uma **cost function (função de custo)**, que mede o quão ruim o sistema é ao fazer previsões nos dados de treinamento, além de uma penalidade pela complexidade do modelo caso ele seja regularizado. Para fazer previsões, fornecemos as **features (características/variáveis de entrada)** da nova **instance** à função de predição do modelo, usando os valores dos parâmetros encontrados pelo algoritmo de aprendizado.
</details>

---

### 14 - Quais são alguns dos principais desafios em Machine Learning?

<details>
<summary><strong>Minha Resposta</strong></summary>

Os desafios se dividem em problemas com os **dados** e problemas com os **modelos**. Faltam dados suficientes, dados de baixa qualidade (ruído/erros), dados não representativos do mundo real, ou *features* pouco informativas. Do lado do modelo, o desafio é evitar que ele seja simples demais (**underfitting**) ou complexo/memorizador demais (**overfitting**).

Exemplos: Treinar um sistema de recomendação apenas com dados do Brasil e tentar rodá-lo na Índia (dado não representativo). Usar uma rede neural profunda de bilhões de parâmetros para prever apenas 50 preços de casas (overfitting).

Palavras-chave: data quality, uninformative features, underfitting, overfitting, nonrepresentative training data.
Referências: Cap. 1 (Principais Desafios do ML).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Alguns dos principais desafios em **Machine Learning** são a falta de dados, a má qualidade dos dados, dados não representativos, **features** pouco informativas, modelos excessivamente simples que sofrem **underfitting (subajuste)** nos dados de treinamento e modelos excessivamente complexos que sofrem **overfitting (sobreajuste)** nos dados.
</details>

---

### 15 - Se um modelo tem ótima performance no conjunto de treinamento, mas ruim em dados novos, qual é a provável causa e quais são possíveis soluções?

<details>
<summary><strong>Minha Resposta</strong></summary>

A causa provável é o **Overfitting** (Sobreajuste), indicando que o modelo decorou os dados de treinamento (incluindo os ruídos) e não consegue generalizar para dados novos. Possíveis soluções: simplificar o modelo (usar algoritmos mais simples, reduzir parâmetros/features ou atuar aplicando regularização), obter mais dados de treinamento, ou limpar os dados atuais (reduzir ruídos e consertar erros).

Exemplos: Aplicar regularização (como penalidade L2/Ridge) para restringir os pesos de um modelo, ou reduzir o grau de um polinômio em uma regressão para evitar que a curva oscile violentamente passando por todos os pontos de ruído.

Palavras-chave: overfitting, generalization error, regularization, model simplification, noise reduction.
Referências: Cap. 1 (Principais Desafios do ML).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Se um modelo tem ótimo desempenho nos dados de treinamento, mas generaliza mal para novas instâncias, é provável que o modelo esteja sofrendo **overfitting** nos dados de treinamento, ou então tivemos extrema sorte nos dados de treinamento. Possíveis soluções para **overfitting** incluem obter mais dados, simplificar o modelo — escolhendo um algoritmo mais simples, reduzindo o número de parâmetros ou **features** usadas, ou regularizando o modelo — ou reduzir o ruído nos dados de treinamento.
</details>

---

### 16 - O que é conjunto de teste (test set) e por que utilizar?

<details>
<summary><strong>Minha Resposta</strong></summary>

**Conjunto de Teste** (Test Set). Seu propósito é estimar o **erro de generalização** que um modelo cometerá em novas instâncias, fornecendo uma avaliação final de sua performance real *antes* de ser lançado em produção.

Exemplos: Separar 20% dos seus dados no início do projeto (que o modelo nunca verá durante o treino) para medir o erro final do classificador de spam antes de ativá-lo para os usuários.

Palavras-chave: test set, generalization error, unseen data, out-of-sample evaluation, production.
Referências: Cap. 1 (Testes e Validação).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Um **test set (conjunto de teste)** é usado para estimar o **generalization error (erro de generalização)** que um modelo cometerá em novas instâncias antes de ser lançado em produção.
</details>

---

### 17 - Para que serve um conjunto de validação (validation set)?

<details>
<summary><strong>Minha Resposta</strong></summary>

**Conjunto de Validação** (Validation Set). Serve para **comparar diferentes modelos** e **ajustar hiperparâmetros**. Ele atua como um ambiente seguro de testes intermediários. Se usássemos o Conjunto de Teste para ficar ajustando hiperparâmetros, o modelo acabaria "decorando" também os dados de teste (overfitting no test set) e o erro de generalização pareceria otimista demais antes de ir para produção.

Exemplos: Treinar 5 modelos de Random Forest com profundidades diferentes no Conjunto de Treinamento; usar o Conjunto de Validação para ver qual teve melhor acurácia (seleção do modelo); e só usar o Conjunto de Teste uma única vez no final para medir a precisão definitiva.

Palavras-chave: validation set, hyperparameter tuning, model selection, data leakage, holdout.
Referências: Cap. 1 (Testes e Validação).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Um **validation set (conjunto de validação)** é usado para comparar modelos. Ele permite selecionar o melhor modelo e ajustar os **hyperparameters**.
</details>

---

### 18 - O que é um conjunto `train-dev` e quando ele é usado?

<details>
<summary><strong>Minha Resposta</strong></summary>

**Train-dev set** (Conjunto de Treino-Desenvolvimento). É usado para diagnosticar **incompatibilidade de dados (data mismatch)**. É uma pequena fatia extraída do conjunto de *treinamento*.

O fluxo é: se o modelo vai bem no *treino* mas vai mal no *train-dev*, ele está sofrendo **overfitting**. Se ele vai bem no *treino* E no *train-dev*, mas vai mal na *validação*, o problema não é overfitting, mas sim um **mismatch** (os dados que você usou para treinar são diferentes/piores do que os dados reais de validação/produção), indicando que você precisa conseguir dados de treino mais realistas.

Exemplos: Treinar um App de identificar flores com imagens nítidas da web (treino), mas os usuários vão mandar fotos borradas de celular (validação/teste). O train-dev ajuda a isolar de quem é a culpa do erro.

Palavras-chave: train-dev set, data mismatch, overfitting, training data problem.
Referências: Cap. 1 (Testes e Validação).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

O **train-dev set (conjunto de treino-desenvolvimento)** é usado quando há risco de **mismatch (incompatibilidade/desalinhamento)** entre os dados de treinamento e os dados usados nos conjuntos de validação e teste, que devem sempre ser o mais parecidos possível com os dados que serão usados quando o modelo estiver em produção. O **train-dev set** é uma parte do conjunto de treinamento que é separada, ou seja, o modelo não é treinado nela. O modelo é treinado no restante do conjunto de treinamento e avaliado tanto no **train-dev set** quanto no **validation set**. Se o modelo tem bom desempenho no conjunto de treinamento, mas não no **train-dev set**, então provavelmente está sofrendo **overfitting** no conjunto de treinamento. Se ele tem bom desempenho tanto no conjunto de treinamento quanto no **train-dev set**, mas não no **validation set**, então provavelmente existe um **data mismatch (incompatibilidade dos dados)** significativo entre os dados de treinamento e os dados de validação + teste. Nesse caso, você deve tentar melhorar os dados de treinamento para que eles se pareçam mais com os dados de validação + teste.
</details>

---

### 19 - Por que não devemos ajustar hiperparâmetros usando o conjunto de teste?

<details>
<summary><strong>Minha Resposta</strong></summary>

Você não deve ajustar hiperparâmetros no conjunto de teste porque corre o risco de causar **overfitting no test set** (sobreajuste nos dados de teste). Se você usar o conjunto de teste para escolher os melhores hiperparâmetros, você vai modelá-los de acordo com as peculiaridades exclusivas daquele conjunto de teste. Como resultado, o **erro de generalização** que você medirá será **excessivamente otimista** (uma falsa sensação de acerto geral) e o modelo final terá um desempenho pior no mundo real (em produção) do que o esperado.

Exemplos: Você testa 10 arquiteturas de Rede Neural diferentes direto no conjunto de teste. Aquela que tira a maior nota na verdade não é a melhor no geral, apenas teve "sorte" ou se encaixou exatamente nas minúcias daquelas imagens de teste. Quando o app for lançado aos usuários, vai falhar miseravelmente.

Palavras-chave: overfitting no test set, hyperparameter tuning, optimistic generalization error, data leakage.
Referências: Cap. 1 (Testes e Validação).
</details>

<details>
<summary><strong>Resposta do Livro</strong></summary>

Se você ajustar **hyperparameters** usando o **test set**, corre o risco de causar **overfitting** no próprio **test set**, e o **generalization error** medido será otimista demais. Em outras palavras, você pode acabar lançando um modelo que tem desempenho pior do que o esperado.
</details>
