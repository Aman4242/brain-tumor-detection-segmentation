# Brain Tumor Detection and Segmentation using Deep Learning

This project presents a deep learning pipeline for brain tumor analysis from MRI scans. It includes two core components:

- **Tumor Detection:** Binary image classification using a Convolutional Neural Network (CNN).
- **Tumor Segmentation:** Multi-class pixel-wise segmentation using a 2D U-Net architecture.

---

## 📁 Project Structure


---
## 🧠 Datasets Used

- **Tumor Detection:**  
  [Brain Tumor MRI Dataset (Kaggle)](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)  
  Contains 2D grayscale MRI slices labeled as `tumor` or `no tumor`.

- **Tumor Segmentation:**  
  [BraTS 2020 (Preprocessed)](https://www.kaggle.com/datasets/awsaf49/brats2020-training-data/data)  
  Provides 2D slices with 4 MRI modalities and corresponding segmentation masks for:
  - Enhancing Tumor (ET)
  - Tumor Core (TC)
  - Whole Tumor (WT)

---

## 🚀 Models Overview

### 1. Tumor Detection with CNN

- Input: 2D grayscale MRI slice (128×128)
- Layers:
  - 3 convolutional blocks with BatchNorm + MaxPooling
  - Dense layers with Dropout
- Output: Sigmoid-activated binary classification
- Loss: Binary Cross-Entropy
- Optimizer: Adam

### 2. Tumor Segmentation with 2D U-Net

- Input: 2D MRI slice with 4 modalities (T1, T1ce, T2, FLAIR)
- Architecture:
  - Standard U-Net with encoder-decoder structure and skip connections
- Output: Multi-class segmentation map (3 tumor subregions)
- Loss: Cross-Entropy Loss
- Optimizer: Adam

---

## 📊 Metrics Summary

### 🔹 CNN Tumor Classification

| Metric       | Value   |
|--------------|---------|
| Accuracy     | 99.6%   |
| AUC (ROC)    | 0.96    |
| Precision    | High (see report) |
| Recall       | High (see report) |
| F1-Score     | High (see report) |

### 🔹 U-Net Tumor Segmentation

| Tumor Region       | Dice Score | IoU Score |
|--------------------|------------|-----------|
| Tumor Core (TC)    | 0.99       | —         |
| Whole Tumor (WT)   | 0.91       | —         |
| Enhancing Tumor (ET)| 0.86      | —         |
| **Mean IoU**       | —          | 0.86      |

*Note: Dice and IoU indicate excellent segmentation overlap with ground truth.*

---

## 🛠️ Future Improvements

- Upgrade to 3D U-Net for full volumetric segmentation
- Apply attention-based architectures (e.g., Attention U-Net)
- Explore ensemble and transfer learning approaches
- Integrate model interpretability tools (e.g., Grad-CAM)

---
