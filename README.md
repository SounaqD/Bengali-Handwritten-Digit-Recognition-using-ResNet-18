# 🧠 Bengali Digit Classification Using Deep Learning

### 📘 Course: DS556 — Image Processing   
**Institute:** IIT Ropar & IIM Amritsar  
**Authors:**  
- Aditya Guleria (2024DSS1002)  
- Sounaq Das (2024DSS1021)  
**Date:** October 2025  

---

## 📄 Project Overview

This project focuses on **handwritten Bengali digit recognition** using **deep learning**.  
While English digit recognition (e.g., MNIST) has been extensively studied, Bengali digits remain less explored despite their wide usage.  
The goal of this project was to develop robust models capable of recognizing handwritten Bengali digits (0–9) using the **BanglaLekha-Isolated** dataset.

---

## 🧩 Dataset

**Dataset:** [BanglaLekha-Isolated Dataset (Mendeley)](https://data.mendeley.com/datasets/hf6sf8zrkc/2)

- Contains handwritten samples of Bengali digits (0–9).  
- Split into **training**, **validation**, and **test** sets.  
- Images resized to **128×128 pixels** and normalized.  
- **Data augmentation** applied (rotation, affine transformation, color jitter) to improve generalization.

---

## ⚙️ Methodology

### 1️⃣ SimpleCNN (Baseline)
- Four convolutional blocks: `Conv2D → BatchNorm → ReLU → MaxPooling`
- Fully connected dense layers with **dropout** to prevent overfitting.

### 2️⃣ ResNet18 (Advanced Model)
- Deep **residual network** architecture with skip connections.  
- Final FC layer modified for **10-class output**.

---

## 🧠 Training Configuration

| Parameter | Value |
|------------|--------|
| Optimizer | Adam |
| Learning Rate | 0.001 |
| Loss Function | CrossEntropyLoss |
| Batch Size | 32 |
| Epochs | 4 (extendable) |

---

## 📈 Results & Analysis

| Model | Validation Accuracy |
|--------|----------------------|
| SimpleCNN | 90–93% |
| ResNet18 | **95–98%** |

- **ResNet18 outperformed SimpleCNN** due to residual connections and better feature learning.  
- In some cases, validation accuracy exceeded training accuracy due to the effects of **augmentation** and **dropout**.  
- Misclassifications mostly occurred between **visually similar digits (e.g., ৪ vs ৯)**.

### 🔍 Confusion Matrix Insights
- Most classes achieved **>95% accuracy**.  
- Class **4** had perfect predictions.  
- Minor confusions observed between **0 & 5**, and **8 & 3/4**.

---

## 💬 Discussion

- **ResNet18** demonstrated superior stability and generalization.  
- Data augmentation and dropout enhanced validation performance.  
- Future improvements can focus on deeper and pretrained architectures (EfficientNet, DenseNet).

---

## 🚀 Future Work

- Train for more epochs with **learning rate scheduling**.  
- Apply **transfer learning** with pretrained models.  
- Extend framework to **Optical Character Recognition (OCR)** for full Bengali text.

---

## 🏁 Conclusion

This project successfully demonstrates how deep learning can accurately classify handwritten Bengali digits.  
The **SimpleCNN** serves as a strong baseline, while **ResNet18** achieves superior accuracy, establishing a foundation for future **Indic OCR systems** and **language-specific AI tools**.

---

## 📚 References

1. Y. LeCun et al., *“Gradient-based learning applied to document recognition,”* Proc. IEEE, 1998.  
2. K. He et al., *“Deep Residual Learning for Image Recognition,”* CVPR, 2016.  
3. [BanglaLekha-Isolated Dataset (Mendeley)](https://data.mendeley.com/datasets/hf6sf8zrkc/2)  
4. S. Chowdhury et al., *“Handwritten Bangla Digit Recognition using CNNs,”* IJCA, 2019.
