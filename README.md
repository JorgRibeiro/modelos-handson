# Modelos Hands-On ML

Implementações práticas e exercícios do livro **"Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow"** de Aurélien Géron.

## Estrutura do Projeto

Este repositório está organizado por capítulos, cada um com seus próprios notebooks e guias de estudo.

### Capítulos

| # | Capítulo | Status |
|---|----------|--------|
| [01](chapter-01/README.md) | The Machine Learning Landscape | ✅ Em andamento |
| [02](chapter-02/README.md) | End-to-End Machine Learning Project | ⏳ Planejado |
| [03](chapter-03/README.md) | Classification | ⏳ Planejado |
| [04](chapter-04/README.md) | Training Linear Models | ⏳ Planejado |
| [05](chapter-05/README.md) | Support Vector Machines | ⏳ Planejado |
| [06](chapter-06/README.md) | Decision Trees | ⏳ Planejado |
| [07](chapter-07/README.md) | Ensemble Learning and Random Forests | ⏳ Planejado |
| [08](chapter-08/README.md) | Dimensionality Reduction | ⏳ Planejado |
| [09](chapter-09/README.md) | Unsupervised Learning | ⏳ Planejado |
| [10](chapter-10/README.md) | Neural Nets with Keras | ⏳ Planejado |
| [11](chapter-11/README.md) | Training Deep Neural Networks | ⏳ Planejado |
| [12](chapter-12/README.md) | Custom Models and Training with TensorFlow | ⏳ Planejado |
| [13](chapter-13/README.md) | Loading and Preprocessing Data | ⏳ Planejado |
| [14](chapter-14/README.md) | Deep Computer Vision with CNNs | ⏳ Planejado |
| [15](chapter-15/README.md) | Processing Sequences using RNNs and CNNs | ⏳ Planejado |
| [16](chapter-16/README.md) | NLP with RNNs and Attention | ⏳ Planejado |
| [17](chapter-17/README.md) | Autoencoders, GANs, and Diffusion Models | ⏳ Planejado |
| [18](chapter-18/README.md) | Reinforcement Learning | ⏳ Planejado |
| [19](chapter-19/README.md) | Training and Deploying at Scale | ⏳ Planejado |

## Começando

### Pré-requisitos

- Python 3.12+
- uv (gerenciador de ambientes e pacotes)
- Jupyter Lab

### Configuração do Ambiente

1. Clone este repositório:
   ```bash
   cd modelos-handson
   ```

2. Crie um ambiente virtual isolado:
   ```bash
   uv venv --python 3.12 .venv
   source .venv/bin/activate.fish  # Para Fish shell
   # ou
   source .venv/bin/activate      # Para Bash/Zsh
   ```

3. Instale as dependências:
   ```bash
   uv pip install -r requirements.txt
   ```

4. Inicie o Jupyter Lab:
   ```bash
   jupyter lab
   ```

## Estrutura de Cada Capítulo

Cada pasta de capítulo contém:
- **Notebooks** (exp-XX-*.ipynb): Experimentos e exercícios práticos
- **README.md**: Guia de estudo específico do capítulo

Consulte o README de cada capítulo para instruções detalhadas.

## Agente de Aprendizado

Este repositório conta com um **agente de orientação personalizado** (`.agent.md`) que:
- Orienta por perguntas em vez de fornecer respostas prontas
- Explica conceitos e trade-offs
- Suporta tanto notebooks quanto scripts Python

## Licença

Este repositório segue a licença do livro original e serve propósitos educacionais.