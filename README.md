
---

# Cat Breed Image Classification System (Implementation 1)

This repository contains the first implementation of an image-based classification system designed to identify four specific cat breeds using a Convolutional Neural Network (CNN). This project is part of the **ICT 3212: Introduction to Intelligent Systems** course at the Rajarata University of Sri Lanka.

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



---

## 🛠️ Technical Implementation

### Preprocessing Steps

To ensure the model converges effectively, the following mandatory steps were applied:

* **Resizing:** All input images were resized to a fixed **180x180 pixels**.


* **Normalization:** Pixel values were scaled from 0-255 to **0-1**.


* **Splitting:** The data was divided into an **80% Training set** and a **20% Validation set**.



### Model Architecture

The baseline model follows a **CNN-based approach** (Option A) consisting of:

* Three Convolutional blocks (Conv2D + MaxPooling2D) for automatic feature extraction.


* Flatten layer and Dense (Fully Connected) layers for final classification.


* Softmax activation for multi-class probability output.

---

## 📈 Baseline Results (Implementation 1)

The model was trained for **10 epochs** with the following performance metrics:

* **Training Accuracy:** 95.60% 
* **Validation Accuracy:** 55.89% 
* **Observation:** The model currently shows significant **overfitting** due to a lack of regularization and data augmentation in this baseline phase.

---
