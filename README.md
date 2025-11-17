# Projeto Final | Classificação de Imagens com Abordagens Híbridas

## Aluno
Octávio Luís Conejo de Moraes - RA: 2268108

## Descrição da Abordagem Utilizada

O projeto explorou duas metodologias distintas para classificação de imagens:

### 1. Abordagem Clássica (Extração de Características + Classificação)
* **Extração de Características:** Utilização do descritor **Local Binary Patterns (LBP)**, focado em extrair padrões de textura, como alternativa ao HOG e SIFT.
* **Classificador:** Utilização do classificador **k-Nearest Neighbors (k-NN)**.
* **Dataset Utilizado:** Simulação de 10 imagens simples (Círculos vs. Quadrados).

### 2. Abordagem com Redes Neurais Convolucionais (CNN)
* **Modelo Utilizado:** **ResNet50** pré-treinado na base ImageNet.
* **Estratégia:** **Transfer Learning** com **Fine-Tuning**.
    * As camadas convolucionais da ResNet50 foram congeladas.
    * O classificador original foi substituído por uma nova camada de Global Average Pooling seguida por uma camada Densa de 128 neurônios e a camada de saída *softmax* para duas classes.
    * Ajuste de hiperparâmetro com baixa Taxa de Aprendizado ($1e-4$) para não corromper os pesos pré-treinados.
* **Dataset Utilizado:** Simulação de 10 imagens com duas classes rotuladas (COVID vs. NORMAL).

## Resultados Obtidos

| Abordagem | Modelo/Método | Acurácia Obtida | Observação |
| :--- | :--- | :--- | :--- |
| **CNN (Fine-Tuning)** | ResNet50 | **0.5000** | Resultado esperado. O modelo não conseguiu aprender a distinção devido ao dataset ser composto por imagens pretas idênticas (simulação de dados nulos), resultando em desempenho aleatório (50%). |
| **Clássica** | LBP + k-NN | **1.0000** | Resultado excelente, obtido pela simplicidade das características visuais (círculos vs. quadrados) no dataset simulado. |

## Arquitetura de Software e Desenvolvimento

Para otimizar a execução e cumprir a entrega sem o *dataset*, foi utilizada uma **abordagem de script único e auto-contido** no Google Colab. Todas as funções de pré-processamento, definição do modelo (ResNet50) e avaliação (cálculo de métricas) estão integradas no arquivo `.ipynb`, garantindo a reprodutibilidade completa e o atendimento aos requisitos.

## Links de Entrega

* **Link para o Repositório do Projeto (Código e Vídeo):**
    * [GitHub](https://github.com/Moraesolc99/Projeto-Final-Processamento-de-Imagens-2025-2)

* **Link Direto para o Notebook do Colab (Execução):**
    *  [Colab](https://colab.research.google.com/drive/19xC8svPTGK4XrVKqKeQxhBt0O0DT_q88?usp=sharing)

## Instruções de Uso

O projeto foi desenvolvido para ser executado no Google Colab.

1.  **Pré-requisitos:**
    * Abrir o arquivo **`Projeto_Final_Processamento_de_Imagens_2025_2_Octavio_Moraes_2268108.ipynb`** no Google Colab.
    * Configurar o ambiente de execução (Runtime) para utilizar **GPU** (por exemplo, T4 ou V100), essencial para o treinamento da ResNet50.

2.  **Execução Sequencial:**
    * O notebook é estruturado em **5 Células** para demonstrar as duas abordagens. As células devem ser executadas em ordem, do topo para o final.
    * **Célula 1 (Instalação e Importações):** Deve ser a primeira a ser executada. A versão final já contém a correção para a função `preprocess_input`.
    * **Célula 2 (Simulação do Dataset):** Cria a estrutura de pastas (`data_cnn`) e as imagens simuladas, garantindo que o código seja auto-contido.
    * **Célula 3 a 5:** Contêm a implementação do modelo **ResNet50 com Fine-Tuning** e a geração do relatório final de métricas.
