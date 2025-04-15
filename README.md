# Model Training and Evaluation Notebooks

This repository contains two Jupyter Notebook files designed for the training and evaluation of a machine learning model. The notebooks cover two main stages of the modeling pipeline:

1. **cross_validation_train.ipynb** – Training the model using cross-validation.
2. **validate_test_set.ipynb** – Validating the model performance using a held-out test set.

## Table of Contents
- [Overview](#overview)
- [Notebook Details](#notebook-details)
  - [Cross-Validation Training Notebook](#cross-validation-training-notebook)
  - [Test Set Validation Notebook](#test-set-validation-notebook)
- [Setup and Requirements](#setup-and-requirements)

## Overview

This project demonstrates a typical machine learning pipeline:
- **Training Phase:** The first notebook (`cross_validation_train.ipynb`) focuses on model training. It uses cross-validation techniques to assess the robustness of the model. Cross-validation helps in understanding how the model performs across different subsets of data and can assist in tuning hyperparameters.
  
- **Evaluation Phase:** After training, the second notebook (`validate_test_set.ipynb`) is used for final evaluation. It applies the trained model on a separate test set to confirm its performance and generalization capability.

## Notebook Details

### Cross-Validation Training Notebook
- **Filename:** `cross_validation_train.ipynb`
- **Purpose:** 
  - Load and preprocess the training dataset.
  - Implement  5 fold- cross-validation, where it splits the patients to evaluate model performance on different train-val splits.
  - Easily tune different things such as models, preprocessing, hyperparameters.
  - Structurally save every model with proper naming and Save every run to WandB
- **Key Sections:**
  - Cross validation setup
  - Data and functions loading
  - Loading model and create data loaders
  - Training loop: Preprocessing, Training, check metrics on validation set.
  - Once done with with training check final results on test set
- **Expected Outcome:** A trained model along with detailed insights into its performance variations across different validation folds.

### Test Set Validation Notebook
- **Filename:** `validate_test_set.ipynb`
- **Purpose:**
  - Data and functions loading
  - Use the 5 models from the cross validation sepperately or as an esemble to generate samples or calculate metrics on the test set.
  - Generate results for the secret test set.
- **Key Sections:**
  - Load in all the functions and data
  - Loading the Trained Model
  - Data Preprocessing for the Test Set
  - Model Prediction and Metrics Calculation
  - Compare .gz files (used to check compatibility with secret test set, (eg voxel size))
- **Expected Outcome:** Results from model detections as .gz files and/or results from ensemble on test set.
## Setup and Requirements

To run these notebooks, ensure you have the same versions as in requirements.txt

If you just want to install all the libraries run in a terminal:
"pip install -r requirements.txt"


