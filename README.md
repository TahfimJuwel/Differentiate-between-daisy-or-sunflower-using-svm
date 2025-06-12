# 🌼 Daisy vs. 🌻 Sunflower Image Classification using SVM

This project demonstrates a classic machine learning approach to image classification using a **Support Vector Machine (SVM)**. The goal is to build a model that can distinguish between images of **daisies** and **sunflowers**.

Instead of using deep learning architectures like CNNs, this project uses **raw, flattened pixel values** as features, showcasing a fundamental computer vision pipeline using **Scikit-learn** and **OpenCV**.

---

## 📑 Table of Contents

- [Project Overview](#project-overview)
- [Methodology](#methodology)
  - [Data Loading and Preprocessing](#data-loading-and-preprocessing)
  - [Data Normalization](#data-normalization)
  - [SVM Model Training](#svm-model-training)
  - [Evaluation](#evaluation)
- [📊 Results](#results)
- [🚀 How to Use](#how-to-use)
- [🧩 Dependencies](#dependencies)
- [🧠 Code Note](#code-note)

---

## 📘 Project Overview

The core task is to solve a **binary image classification** problem.

- Dataset: Contains labeled images of **daisies** and **sunflowers**
- Task: Classify images based on their **flattened pixel values**
- Frameworks: Scikit-learn, OpenCV
- Model: Linear SVM

The full pipeline includes:

- Reading and preprocessing image data
- Normalizing pixel values
- Training a linear SVM
- Evaluating performance using accuracy and a confusion matrix

---

## 🧪 Methodology

### 🔹 Data Loading and Preprocessing

- Images are loaded from `daisy/` and `sunflower/` class folders
- Each image is:
  - Resized to **64x64**
  - Flattened from 64x64x3 to a vector of length **12,288**
- Labels:
  - `daisy`: `0`
  - `sunflower`: `1`

### 🔹 Data Normalization

- Pixel values scaled from **[0, 255]** to **[0, 1]**
- Done by dividing each value by `255.0`

### 🔹 SVM Model Training

- Model: `sklearn.svm.SVC`
- Kernel: `linear`
- Regularization: `C=0.001` (soft margin)
- Trained on preprocessed and normalized features

### 🔹 Evaluation

- **Accuracy Score**: Percentage of correct predictions
- **Confusion Matrix**: Visual breakdown of TP, TN, FP, FN

---

## 📊 Results

| Metric              | Value     |
|---------------------|-----------|
| Training Accuracy   | 88.56%    |
| Test Accuracy       | 85.64%    |

### 🔍 Confusion Matrix

|                     | Predicted Daisy | Predicted Sunflower |
|---------------------|-----------------|----------------------|
| **Actual Daisy**     | 91 (TN)         | 10 (FP)              |
| **Actual Sunflower** | 19 (FN)         | 82 (TP)              |

- The model generalizes well (small gap between train/test accuracy)
- Acceptable misclassification rate for a basic ML approach

---

## 🚀 How to Use

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/daisy-vs-sunflower-svm.git
   cd daisy-vs-sunflower-svm
