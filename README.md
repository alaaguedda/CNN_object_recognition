# Advanced CNN Models with Keras

Transfer Learning, Data Augmentation, Fine-Tuning, and Model Comparison using TensorFlow/Keras on the CIFAR-10 dataset.

## Project Overview

This project explores multiple Convolutional Neural Network (CNN) approaches for image classification using the CIFAR-10 dataset.

The notebook compares:

- A custom CNN trained from scratch
- Transfer learning with MobileNetV2
- Fine-tuning MobileNetV2
- Transfer learning with ResNet50

The goal is to understand how pre-trained deep learning models behave compared to a baseline CNN on a small image dataset.

---

## Dataset

Dataset used: CIFAR-10

CIFAR-10 contains:

- 60,000 RGB images
- 10 image classes
- Image size: 32×32

### Classes

- airplane
- automobile
- bird
- cat
- deer
- dog
- frog
- horse
- ship
- truck

The dataset is automatically downloaded using TensorFlow/Keras.

---

## Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Pandas

---

## Experiments

### E0 — Baseline CNN

A custom CNN trained entirely from scratch.

#### Architecture

- Conv2D
- BatchNormalization
- MaxPooling
- Dropout
- Dense layers

#### Result

- Test Accuracy: **70.08%**

---

### E1 — Transfer Learning with MobileNetV2

Uses MobileNetV2 pre-trained on ImageNet as a frozen feature extractor.

#### Steps

- Resize images to 96×96
- Apply ImageNet preprocessing
- Freeze backbone layers
- Train only the classifier head

#### Result

- Test Accuracy: **14.98%**

---

### E2 — Fine-Tuning MobileNetV2

Unfreezes the last 20 layers of MobileNetV2 and retrains them using a very small learning rate.

#### Purpose

Adapt ImageNet features to CIFAR-10.

#### Result

- Test Accuracy: **10.00%**

---

### E3 — Transfer Learning with ResNet50

Uses ResNet50 as a frozen backbone for feature extraction.

#### Result

- Test Accuracy: **31.01%**

---

## Final Results

| Experiment | Test Accuracy |
|---|---|
| Baseline CNN | 70.08% |
| ResNet50 (Frozen) | 31.01% |
| MobileNetV2 (Frozen) | 14.98% |
| MobileNetV2 (Fine-Tuned) | 10.00% |

---

## Key Concepts Covered

- Transfer Learning
- Fine-Tuning
- Frozen Backbones
- Data Augmentation
- Early Stopping
- GlobalAveragePooling2D
- Image Preprocessing
- CNN Architecture Design
- Model Comparison

---

## Why the Baseline CNN Performed Better

The baseline CNN achieved the best accuracy because:

- CIFAR-10 images are very small (32×32)
- Pre-trained models were designed for larger ImageNet images
- Resizing small images can reduce feature quality
- Transfer learning models may not adapt well without careful tuning
- The custom CNN was simpler and better suited for CIFAR-10

---

## Data Augmentation Used

The project applies online data augmentation using Keras layers:

- Random horizontal flip
- Random rotation
- Random zoom

This helps reduce overfitting and improves model generalization.

---

## How to Run

### Clone the Repository

```bash
git clone <your-repository-url>
cd <repository-name>
```

### Install Dependencies

```bash
pip install tensorflow numpy matplotlib pandas
```

### Run the Notebook

Open the notebook using:

- Jupyter Notebook
- Google Colab

Recommended runtime:
- GPU (T4 GPU in Google Colab)

---

## Project Structure

```text
project/
│
├── advanced_cnn_lab.ipynb
├── README.md
└── requirements.txt
```

---

## Learning Outcomes

After completing this project, you should understand:

- How CNNs work
- How transfer learning works
- The difference between feature extraction and fine-tuning
- Why preprocessing matters for pre-trained models
- How to compare deep learning architectures experimentally

---

## Author

First Year AI & Data Science — Semester 2 Lab Project

Advanced CNN Models with TensorFlow/Keras and CIFAR-10.
