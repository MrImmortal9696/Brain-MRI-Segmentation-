Brain MRI Segmentation 🧠

📖 Overview

This project focuses on Brain MRI Segmentation using the BraTS 2020 dataset. The goal is to train a 3D U-Net model to segment different brain regions, including tumors, from MRI scans. The dataset consists of multi-modal MRI images, including T1, T1CE, T2, and FLAIR sequences.

🚀 Features

Multi-modal MRI segmentation

3D U-Net architecture for segmentation

Data preprocessing including multi-channel merging and resizing

Custom data generator for handling large datasets

Model training and evaluation pipeline

📊 Dataset Preparation

The dataset consists of four MRI modalities:

T1: Native MRI sequence

T1CE: Contrast-enhanced T1-weighted MRI

T2: T2-weighted MRI

FLAIR: Fluid-attenuated inversion recovery MRI

We use T1CE, T2, and FLAIR images for training, combined into a single multi-channel volume. The segmentation masks contain four labels: 0 (background), 1, 2, and 4, which are later adjusted to 0, 1, 2, and 3.

Training the Model

Step 1: Data Preprocessing

Normalize and resize MRI scans

Convert images to numpy arrays for efficient processing

Split into training and validation sets

Step 2: Custom Data Generator

Instead of using Keras’ built-in data generators (which do not support numpy arrays), a custom generator is implemented to load images in batches.

Step 3: Model Training

3D U-Net is used for segmentation

Loss function: Dice loss

Optimizer: Adam

Data is fed using the custom generator
