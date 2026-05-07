# Modelos Hands-On ML

Implementacoes praticas, anotacoes e exercicios do livro **"Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow"**, de Aurelien Geron.

O projeto esta organizado por capitulos. Cada capitulo contem notebooks executaveis, respostas de exercicios e um README proprio com roteiro de estudo.

## Estrutura do Projeto

```text
modelos-handson/
├── chapter-01/
│   ├── 01_Aprendizado_de_Maquina.ipynb
│   ├── Respostas.md
│   └── README.md
├── chapter-02/
│   ├── 02_Projeto_End_to_End_de_Machine_Learning.ipynb
│   ├── 02_Resposta_exercicio*.ipynb
│   ├── Respostas.md
│   └── README.md
├── chapter-03/
├── ...
├── chapter-19/
├── requirements.txt
└── README.md
```

## Capítulos

| # | Capítulo | Conteudo principal | Status |
|---|----------|--------------------|--------|
| [01](chapter-01/README.md) | The Machine Learning Landscape | Fundamentos de ML, tipos de aprendizado, generalizacao, sobreajuste, subajuste, regressao linear e regularizacao. | ✅ Concluido |
| [02](chapter-02/README.md) | End-to-End Machine Learning Project | Projeto completo com California Housing Prices, EDA, pipelines, validacao cruzada, busca de hiperparametros, avaliacao final e persistencia. | ✅ Concluido |
| [03](chapter-03/README.md) | Classification | Classificacao e metricas com MNIST. | ⏳ Planejado |
| [04](chapter-04/README.md) | Training Linear Models | Regressao linear, gradiente descendente, regressao logistica e softmax. | ⏳ Planejado |
| [05](chapter-05/README.md) | Support Vector Machines | SVM para classificacao, regressao e kernels. | ⏳ Planejado |
| [06](chapter-06/README.md) | Decision Trees | Arvores de decisao para classificacao e regressao. | ⏳ Planejado |
| [07](chapter-07/README.md) | Ensemble Learning and Random Forests | Ensembles, bagging, boosting e florestas aleatorias. | ⏳ Planejado |
| [08](chapter-08/README.md) | Dimensionality Reduction | PCA, reducao de dimensionalidade e visualizacao. | ⏳ Planejado |
| [09](chapter-09/README.md) | Unsupervised Learning | Clustering, mistura gaussiana e deteccao de anomalias. | ⏳ Planejado |
| [10](chapter-10/README.md) | Neural Nets with Keras | Redes neurais com Keras. | ⏳ Planejado |
| [11](chapter-11/README.md) | Training Deep Neural Networks | Treinamento de redes profundas. | ⏳ Planejado |
| [12](chapter-12/README.md) | Custom Models and Training with TensorFlow | Modelos e loops customizados com TensorFlow. | ⏳ Planejado |
| [13](chapter-13/README.md) | Loading and Preprocessing Data | Carregamento e preprocessamento de dados. | ⏳ Planejado |
| [14](chapter-14/README.md) | Deep Computer Vision with CNNs | Visao computacional profunda com CNNs. | ⏳ Planejado |
| [15](chapter-15/README.md) | Processing Sequences using RNNs and CNNs | Sequencias, RNNs e CNNs temporais. | ⏳ Planejado |
| [16](chapter-16/README.md) | NLP with RNNs and Attention | NLP, RNNs, atencao e transformers. | ⏳ Planejado |
| [17](chapter-17/README.md) | Autoencoders, GANs, and Diffusion Models | Autoencoders, GANs e modelos de difusao. | ⏳ Planejado |
| [18](chapter-18/README.md) | Reinforcement Learning | Aprendizado por reforco. | ⏳ Planejado |
| [19](chapter-19/README.md) | Training and Deploying at Scale | Treinamento e implantacao em escala. | ⏳ Planejado |

## Comecando

### Pre-requisitos

- Python 3.12+
- `uv` para gerenciar ambiente e pacotes
- Jupyter Lab

### Configuracao do Ambiente

Entre no diretorio do projeto:

```bash
cd modelos-handson
```

Crie o ambiente virtual:

```bash
uv venv --python 3.12 .venv
```

Ative o ambiente:

```bash
source .venv/bin/activate
```

Se estiver usando Fish:

```fish
source .venv/bin/activate.fish
```

Instale as dependencias:

```bash
uv pip install -r requirements.txt
```

Abra o Jupyter Lab:

```bash
jupyter lab
```

## Organizacao de Cada Capitulo

Cada pasta de capitulo pode conter:

- `README.md`: roteiro e status do capitulo.
- `*.ipynb`: notebooks principais e exercicios praticos.
- `Respostas.md`: respostas, revisoes e comparacoes dos exercicios.
- `datasets/`: dados usados pelo capitulo, quando necessario.
- `images/`: figuras geradas ou usadas nos notebooks.

## Progresso Atual

- Capitulo 1 concluido com notebook principal, figuras e respostas teoricas.
- Capitulo 2 concluido com projeto fim a fim, seis notebooks de exercicios e comparacao numerica dos resultados.
- Capitulos 3 a 19 permanecem planejados para revisao e consolidacao progressiva.

## Agente de Aprendizado

Este repositorio conta com um agente de orientacao personalizado (`.agent.md`) para apoiar o estudo. A proposta e orientar por perguntas, explicar conceitos e trade-offs, e manter o foco em aprendizado ativo nos notebooks e scripts.

## Licenca

Este repositorio segue a licenca do material original e serve a propositos educacionais.

**Ultima atualizacao geral**: 7 de maio de 2026
