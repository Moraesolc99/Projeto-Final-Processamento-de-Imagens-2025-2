# Classificação de Grãos de Café usando GLCM + k-NN e CNN

## Equipe
- Octávio Luís Conejo de Moraes – RA: 2268108

---

## Descrição Geral do Projeto
Este projeto realiza a classificação de imagens do **Coffee Beans Dataset** utilizando duas abordagens de Processamento de Imagens:

### **Abordagem – Clássica**
- Extração de características com **GLCM (Gray Level Co-occurrence Matrix)**  
- Classificação usando **k-NN (k-Nearest Neighbors)**  
- Avaliação com:
  - Matriz de confusão  
  - Acurácia, Precisão, Recall, F1-score  

### **Abordagem – CNN**
- Modelo **pré-treinado EfficientNetB0**, diferente dos modelos apresentados em aula.
- Fine-tuning com:
  - Camadas adicionais  
  - Treinamento sobre as features extraídas  
- Avaliação com:
  - Acurácia  
  - Matriz de confusão  
  - Gráficos de loss/accuracy  

---

## Bibliotecas Utilizadas
- Python 3  
- NumPy  
- OpenCV  
- scikit-image  
- scikit-learn  
- TensorFlow / Keras  
- Matplotlib  
- Seaborn  

---

## Métodos Utilizados

### **1. Extração de características (GLCM)**
- Contrast  
- Dissimilarity  
- Homogeneity  

Essas características alimentam um classificador **k-NN**.

### **2. CNN com EfficientNetB0 (Fine-Tuning)**
- Base pré-treinada no ImageNet  
- Cabeçalho redefinido com camadas densas  
- Treinamento por 10–15 épocas  
- Acompanhamento por curva de loss e accuracy  

---

## Resultados Obtidos

### **Abordagem Clássica (GLCM + k-NN)**
- Acurácia: **0.5750**  
- Precisão: **0.5706**  
- Recall: **0.5750**  
- F1-score: **0.5719**

### **Abordagem CNN (EfficientNetB0 Fine-Tuning)**
- Acurácia de validação: **0.9167**  
- Loss de Validação: **0.2514** 
- Acurácia de Treino: **99,01%**  
- Loss de Treino: **0.0317** 
- Total de parâmetros: **4.113.825**  
- Parâmetros Treinaveis: **4.071.802**  
- Parâmetros não-treináveis: **42.023**
  
---

## Repositório do Projeto
Código completo e vídeo da apresentação:

**[GITHUB](https://github.com/Moraesolc99/Projeto-Final-Processamento-de-Imagens-2025-2)**

---

## Dataset Utilizado
Coffee Bean Dataset (4 classes):  

[coffee-bean-dataset](https://www.kaggle.com/datasets/gpiosenka/coffee-bean-dataset-resized-224-x-224?resource=download)

---

## Área de Execução
Projeto foi inteirameente feito no Colab:  

[Colab](https://colab.research.google.com/drive/1W4OuRWsK1E7G1SDfRYSoSpAB7yUgxdXg?usp=sharing)

---

## Como Usar (Execução no Google Colab)

### 1. Abra o notebook no Colab
- Clique no link do notebook `.ipynb`
- Selecione **"Open in Google Colab"**

### 2. Envie o dataset
- Baixe o dataset no Kaggle  
- Coloque o arquivo `coffee.zip` dentro do Colab:
  - Menu lateral → **Arquivos**  
  - Clique no botão **Upload**  
  - Envie **coffee.zip**

### 3. Execute as células na ordem
O notebook já está dividido em seções:

1. Preparação do ambiente  
2. Extração do GLCM  
3. Treinamento do k-NN  
4. Avaliação (métricas + matriz de confusão)  
5. Preparação da CNN  
6. Treinamento (fit)  
7. Avaliação (curvas e métricas)  

### 4. Gerar resultados
Ao final da execução você verá:

- Gráficos de loss e accuracy  
- Matriz de confusão  
- Métricas completas  
- Acurácia final  

---
