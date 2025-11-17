# Projeto Final | Classificação de Imagens com Abordagens Híbridas

## Aluno
Octávio Luís Conejo de Moraes - RA: 2268108

## Descrição da Abordagem Utilizada

O projeto explorou duas metodologias distintas para classificação de imagens, utilizando as restrições de métodos diferentes dos apresentados em aula:

### 1. Abordagem Clássica (Extração de Características + Classificação)
* **Extração de Características:** Utilização do descritor **Local Binary Patterns (LBP)**, focado em extrair padrões de textura, como alternativa ao HOG e SIFT.
* **Classificador:** Utilização do classificador **k-Nearest Neighbors (k-NN)**.
* **Dataset Utilizado:** Simulação de 10 imagens simples (Círculos vs. Quadrados).

### 2. Abordagem com Redes Neurais Convolucionais (CNN)
* **Modelo Utilizado:** **ResNet50** pré-treinado na base ImageNet (diferente do MobileNet).
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

## Links de Entrega

* **Link para o Repositório do Projeto (Código e Vídeo):**
    * [GitHub](https://github.com/Moraesolc99/Projeto-Final-Processamento-de-Imagens-2025-2)

* **Link Direto para o Notebook do Colab (Execução):**
    *  [Colab](https://colab.research.google.com/drive/19xC8svPTGK4XrVKqKeQxhBt0O0DT_q88?usp=sharing)

## Instruções de Uso

1.  **Pré-requisitos:** Instalar o Python e configurar o ambiente de execução para usar **GPU** no Google Colab.
2.  **Execução:** Abrir o notebook `.ipynb` no Google Colab.
3.  **Ordem:** Executar as células sequencialmente, da Célula 1 à Célula 5, após verificar que a **Célula 1 (Instalação e Importações)** foi atualizada com a correção da função `preprocess_input`.
