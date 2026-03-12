## Anomaly Detection in Industrial Images Using Neural Networks

This project develops a deep learning–based anomaly detection system for identifying defects in industrial product images. Using a convolutional autoencoder neural network, the model learns the visual structure of defect-free products and detects anomalies when deviations occur.

The goal is to automate visual quality inspection in manufacturing environments, reducing reliance on manual inspection and enabling scalable, AI-driven quality control.

## Project Overview

Industrial manufacturing often relies on manual inspection to detect defects such as scratches, contamination, or missing components. However, manual inspection can be:

Expensive

Inconsistent

Difficult to scale

This project addresses the problem by building a neural network model capable of detecting anomalies in industrial product images. The model is trained on defect-free images and identifies abnormal regions in new images. 

## Problem Statement

The objective of this project is to:

Train a neural network to learn normal image patterns

Detect defective regions in industrial product images

Generate pixel-level segmentation masks highlighting anomalies

The model uses images from the MVTec Anomaly Detection dataset, a benchmark dataset for industrial visual inspection tasks. 

## Dataset

The dataset used in this project follows a structured format:

Train

Contains only normal (defect-free) images used to train the model.

Test

Contains both:

normal images

defective images (e.g., scratches, contamination, holes)

Ground Truth

Provides pixel-level masks that highlight the exact location of anomalies in defective images. 

## Data Preprocessing

Before training, images were preprocessed to ensure consistent input for the neural network.

Steps include:

Image resizing (RGB images resized to manageable dimensions, Normalization of pixel values, Binary mask conversion for ground truth segmentation, Thresholding to identify anomaly regions

This preprocessing step helps reduce noise and improves model training efficiency.

Model Architecture, The anomaly detection system uses a convolutional autoencoder architecture. 

Extracts important spatial features from images using:

Conv2D layers

MaxPooling layers

Feature compression through a bottleneck representation

Bottleneck Layer

Captures the compressed representation of normal image patterns.

Reconstructs the image using:

Conv2DTranspose layers

Upsampling

Skip connections to preserve spatial details

Activation Function

Sigmoid activation produces pixel-level probability maps for anomaly detection.

Loss Function

Binary Cross Entropy is used for measuring reconstruction error between predicted and ground truth masks.

Optimizer

Adam optimizer is used for efficient gradient updates and faster convergence. 

## Results
Carpet Defect Detection

The model successfully detected anomalies in carpet images by highlighting defective regions using predicted masks.

Training observations:

Rapid convergence within the first few epochs

Stable training and validation loss

Minimal overfitting

Loss values stabilized around 0.06–0.08, indicating effective learning. 

Leather Defect Detection

The model generalized well to leather defect detection.

## Key observations:

Training and validation loss dropped below 0.1 within the first 5 epochs

Stable convergence around 0.04–0.06 loss

Reliable detection of defects such as scratches and contamination

These results demonstrate strong generalization across different material surfaces. 

## Challenges

Several challenges were encountered during model development:

Complex industrial components are difficult to reconstruct

Lighting variations can cause false positives

Autoencoder smoothing may miss very fine defects

These issues highlight the difficulty of anomaly detection in real-world manufacturing environments. 

## Limitations

The model detects anomalies but does not yet classify defect types

High-resolution images increase computational cost

Static thresholding may not adapt well to different defect patterns

Future work can address these limitations through advanced architectures and adaptive detection methods. 

## Future Improvements

Potential improvements include:

Advanced data augmentation (rotation, noise injection, elastic transforms)

Variational Autoencoders (VAE) for unsupervised anomaly detection

Model explainability using SHAP or LIME

Multi-class defect classification

These enhancements would make the system more robust and production-ready. 

## Technologies Used

Python
TensorFlow / Keras
NumPy
OpenCV
Matplotlib
Deep Learning (CNN / Autoencoder)

## Team 14 – BA865

Aparna Kalla

Nilay Jaini

Sai Nruthya Vaka 

## Applications

This anomaly detection system can be applied to:

Manufacturing quality control

Semiconductor defect detection

Textile inspection

Automated product inspection pipelines
