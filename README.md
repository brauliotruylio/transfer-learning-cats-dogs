# 🐱🐶 Transfer Learning: Classificação de Gatos e Cachorros (VGG16)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/brauliotruylio/transfer-learning-cats-dogs/blob/main/Treinamento de Redes Neurais com Transfer Learning.ipynb)

## 📌 Descrição

Este projeto aplica **Transfer Learning** com a rede **VGG16** pré-treinada no ImageNet para classificar imagens de **Gatos** e **Cachorros**.  
O desenvolvimento foi feito no **Google Colab (GPU T4)**, com base no dataset **Cats vs Dogs** da Microsoft.

O fluxo implementado:

1. Download e organização do dataset (train/val/test).
2. Limpeza e conversão das imagens para RGB (eliminação de arquivos corrompidos).
3. Criação de datasets robustos (`tf.data`) para evitar erros de canais.
4. Treinamento da cabeça densa sobre VGG16 congelada.
5. Avaliação no conjunto de teste.
6. Fine-tuning leve (bloco 5 da VGG16 liberado).
7. Geração de métricas finais (classification report e matriz de confusão).

---

## 📊 Resultados

- **Test accuracy (base congelada):** 97.99%
- **Test loss (base congelada):** 0.0866
- **Test accuracy (fine-tuning):** 98.10%
- **Test loss (fine-tuning):** 0.0592

### Classification Report (teste)

```
      precision    recall  f1-score   support

 Cat            0.98      0.98      0.98      1865
 Dog            0.98      0.98      0.98      1865
      
 accuracy                           0.98      3730
 macro avg      0.98      0.98      0.98      3730
 weighted avg   0.98      0.98      0.98      3730
```

### Matriz de confusão (teste)

[[1834 31]  
[ 40 1825]]

---

## 🚀 Como executar

1. Abra o notebook no **Google Colab** e ative **GPU (T4)**.
2. Rode as células na ordem (0 → 5).
3. No final, veja as métricas do teste, relatório e matriz de confusão.

---

## 📂 Dataset

- **Descrição:** [Cats vs Dogs – TFDS](https://www.tensorflow.org/datasets/catalog/cats_vs_dogs)
- **Download oficial:** [Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54765)

---

## 🗣️ Experiência pessoal

Este projeto foi **difícil** de implementar, não pela complexidade do Transfer Learning em si, mas porque as **aulas do curso foram muito fracas**:

- O conteúdo foi passado de forma muito superficial, sem práticas completas.
- Faltaram exemplos práticos mais robustos.
- Na verdade, a experiência do curso foi **ruim** em termos de suporte prático.

Para conseguir concluir, contei com **apoio do ChatGPT**, que ajudou a estruturar o notebook do zero, corrigir erros (como imagens corrompidas e canais inválidos) e organizar um fluxo de trabalho completo e funcional.

---

## 🏷️ Tecnologias utilizadas

- Python 3.12
- TensorFlow / Keras
- NumPy / PIL / scikit-learn
- Google Colab (GPU T4)

---

## 📌 Créditos

- Dataset fornecido pela Microsoft.
- Base pré-treinada: VGG16 (ImageNet).
- Orientação e suporte técnico: **ChatGPT**.
