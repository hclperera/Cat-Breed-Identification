
---

# Cat Breed Image Classification System 
 **Phase 03 - Implementation 1 & 2 (Final)**

This repository contains the complete evolution of an image-based classification system designed to identify four specific cat breeds using a Convolutional Neural Network (CNN). This project is part of the **ICT 3212: Introduction to Intelligent Systems** course at the Rajarata University of Sri Lanka.

## 🐾 Project Overview

The objective of this project is to design and implement a basic image classification model that accurately categorizes cat images into four predefined classes.

### Selected Breeds

* **Bombay** 


* **Calico** 


* **Persian** 


* **Siamese** 



---

## 📊 Dataset Information

* **Source:** Cat Breeds Dataset from Kaggle.


* **Total Images:** 7,813 images across 4 classes.


* **Distribution:**
  * Bombay: 1,833 
  * Calico: 1,918 
  * Persian: 1,876 
  * Siamese: 2,186 




* **Balance:** The dataset is identified as **Unbalanced**.

### 🧹 Dataset Improvements (Implementation 2)
To resolve severe overfitting caused by noisy data, the dataset was heavily modified in Implementation 2:
* **Data Cleaning:** Mislabeled images (e.g., standard orange tabbies labeled as Calico, mixed street breeds labeled as Siamese) were manually removed.
* **Balancing:** The dataset was strictly undersampled to exactly **1,000 accurate images per breed** (4,000 images total), converting it to a **Perfectly Balanced** dataset.



---

## 🛠️ Technical Implementation

### Preprocessing Steps

To ensure the model converges effectively, the following mandatory steps were applied:

* **Resizing:** All input images were resized to a fixed **180x180 pixels**.


* **Normalization:** Pixel values were scaled from 0-255 to **0-1**.


* **Splitting:** The data was divided into an **80% Training set** and a **20% Validation set**.



### Model Architecture

The baseline model follows a **CNN-based approach** consisting of:

* Three Convolutional blocks (Conv2D + MaxPooling2D) for automatic feature extraction.


* Flatten layer and Dense (Fully Connected) layers for final classification.


* Softmax activation for multi-class probability output.

### 🚀 Optimized Architecture (Implementation 2 - Final Model)
To improve generalization, we upgraded to a **Transfer Learning** approach:
* **Pre-trained Base:** MobileNetV2 architecture with frozen 'imagenet' weights.
* **Data Augmentation:** Added `RandomFlip`, `RandomRotation(0.1)`, and `RandomZoom(0.1)` to artificially expand the dataset.
* **Regularization:** Added a `Dropout(0.5)` layer and `EarlyStopping` (patience=5) to prevent memorization.
* **Custom Head:** GlobalAveragePooling2D followed by a Dense output layer for the 4 specific cat classes.

---

## 📈 Baseline Results (Implementation 1)

The model was trained for **10 epochs** with the following performance metrics:

* **Training Accuracy:** 95.60% 
* **Validation Accuracy:** 55.89% 
* **Observation:** The model currently shows significant **overfitting** due to a lack of regularization and data augmentation in this baseline phase.

---

## 🏆 Final Results (Implementation 2)

By utilizing MobileNetV2 on the cleaned and balanced dataset, the system achieved state of the art performance:

* **Overall Test Accuracy:** **96.00%** on unseen test data.
* **Overfitting:** Completely eradicated. Validation accuracy consistently tracked alongside training accuracy.
* **Class F1-Scores:**
  * Bombay: 0.97
  * Calico: 0.96
  * Persian: 0.94
  * Siamese: 0.97

---
