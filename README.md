# Rock–Paper–Scissors Image Classifier (PyTorch)

This project implements a convolutional neural network (CNN) that classifies hand‑gesture images into **rock**, **paper**, and **scissors**.  
The model is trained using PyTorch and evaluated using **per‑class precision and recall**, providing a detailed understanding of its strengths and weaknesses.

---

## Project Overview

The goal of this project is to build a simple but effective deep‑learning model capable of recognizing hand gestures from images.  
The dataset contains three classes:

- **rock**
- **paper**
- **scissors**

The model is trained on augmented images and evaluated on a separate test set.

---

##  Model Architecture

The classifier is a lightweight CNN consisting of:

- 3 convolutional blocks  
- ELU activations  
- MaxPooling layers  
- A fully connected classifier head  

Input images are resized to **128×128** and normalized using ImageNet mean/std.

---

## Training Pipeline

The training pipeline includes:

- Random horizontal flips  
- Random rotations  
- Normalization  
- Adam optimizer  
- Cross‑entropy loss  
- 15 training epochs  

A training loss curve is generated to visualize learning progress.

---

## Evaluation Metrics

The model is evaluated using **TorchMetrics**, computing:

- **Macro precision**  
- **Macro recall**  
- **Per‑class precision**  
- **Per‑class recall**  

These metrics reveal how well the model performs on each gesture individually.

---

## Test Results

### **Macro Metrics**
- **Precision:** ~0.87  
- **Recall:** ~0.85  

### **Per‑Class Precision**
| Class     | Precision |
|-----------|-----------|
| paper     | 0.87 |
| rock      | 1.00 |
| scissors  | 0.76 |

### **Per‑Class Recall**
| Class     | Recall |
|-----------|--------|
| paper     | 0.79 |
| rock      | 0.76 |
| scissors  | 1.00 |

---

## Interpretation of Results

### Rock  
High precision and recall - the model identifies rock confidently and consistently.

### Paper  
High precision but lower recall - the model is cautious and misses some real paper samples.

### Scissors  
Perfect recall but lower precision - the model catches all scissors images but overpredicts scissors on some rock/paper images.

This pattern is typical for hand‑gesture datasets where scissors has high shape variability.

---
