# Unsupervised Learning with Autoencoders for Brain MRI Classification

## Overview

This project uses Convolutional Autoencoders (CAE) for unsupervised feature extraction from brain MRI images to improve classification of images with/without tumors, especially when labeled training data is limited.

## Problem & Motivation

MRI classification faces challenges like high dimensionality, non-linearity, and data scarcity. Traditional methods struggle. This project explores unsupervised deep learning to learn robust features automatically.

## Methodology

1.  **Data:** Brain MRI images (tumor/no tumor). Preprocessed to 100x100 grayscale, normalized.
2.  **Model:** 2-layer Convolutional Autoencoder (PyTorch) trained to reconstruct input images (minimizing MSE).
3.  **Feature Extraction:** Trained encoder extracts latent features.
4.  **Evaluation:** Random Forest classifier performance compared:
    *   Trained on raw image data.
    *   Trained on CAE-extracted features.
    *   Tested across varying train/test splits (80/20 to 50/50).

## Key Results

*   CAE learns effective representations, enabling good image reconstruction.
*   CAE features significantly improve classifier robustness when training data is limited (maintaining ~81% accuracy vs. 74% on raw data with 50% training split).

| Test Data Size | Accuracy (No Autoencoder) | Accuracy (With Autoencoder) |
| :------------- | :------------------------ | :-------------------------- |
| 20%            | 82%                       | 85%                         |
| 30%            | 82%                       | 82%                         |
| 40%            | 79%                       | 81%                         |
| 50%            | 74%                       | 81%                         |


## Technologies

Python, PyTorch, TensorFlow (preprocessing), Scikit-learn, NumPy, Matplotlib.

---
