# Breast Cancer Classification Using Artificial Neural Network

## Overview

This project uses a **Deep Learning Artificial Neural Network (ANN)**
built with TensorFlow/Keras to classify breast cancer cases as
**Malignant** or **Benign** using the Breast Cancer Wisconsin diagnostic
dataset.

The notebook demonstrates the end-to-end machine learning workflow:
loading data, preparing features and labels, splitting and scaling the
dataset, building and training an ANN, evaluating its performance,
visualizing accuracy, and predicting a diagnosis for a sample record.

> **Important:** This is an educational machine-learning project, not a
> medical diagnostic tool. Its predictions must not be used to make
> healthcare decisions.

## Objectives

-   Prepare a tabular dataset for binary classification.
-   Standardize numerical features using `StandardScaler`.
-   Build and train a neural network using TensorFlow/Keras.
-   Evaluate the model on held-out test data.
-   Compare actual and predicted labels and plot training/validation
    accuracy.
-   Create a reusable prediction function for new records.

## Dataset

The notebook expects a CSV file named `data.csv` containing the Breast
Cancer Wisconsin diagnostic dataset.

-   **Rows:** 569
-   **Input features:** 30 numeric features
-   **Target column:** `diagnosis`
-   **Labels:** `M` = Malignant, `B` = Benign

The `id`, `diagnosis`, and optional `Unnamed: 32` columns are excluded
from the input features. The target is encoded as `M = 1` and `B = 0`.

### Dataset path

The notebook currently loads the CSV from a machine-specific path:

``` python
df = pd.read_csv("/home/aditya/Downloads/data.csv")
```

Update this path to match your system, or place `data.csv` in the
notebook's working directory and use:

``` python
df = pd.read_csv("data.csv")
```

Make sure you have the right to use and redistribute the dataset before
publishing it in a public repository.

## Technologies Used

-   Python
-   Jupyter Notebook
-   NumPy
-   pandas
-   TensorFlow / Keras
-   Matplotlib
-   scikit-learn

## Model Architecture

The sequential ANN contains:

1.  An input layer for the 30 standardized features.
2.  A dense layer with 32 neurons and ReLU activation.
3.  A Dropout layer with a rate of 0.2.
4.  A dense layer with 16 neurons and ReLU activation.
5.  An output layer with one neuron and sigmoid activation.

**Training configuration**

-   Optimizer: Adam
-   Loss function: Binary cross-entropy
-   Metric: Accuracy
-   Epochs: 30
-   Batch size: 16
-   Test split: 20%
-   Validation split: 20% of the training data
-   Random state: 42
-   Stratified train/test split

The scaler is fitted only on the training features and then applied to
both the training and test features to help avoid data leakage.

## Workflow

1.  Import required libraries.
2.  Load the dataset from CSV.
3.  Separate input features and target labels.
4.  Split the data into training and test sets.
5.  Standardize the features.
6.  Define and compile the ANN.
7.  Train the model and record training/validation metrics.
8.  Evaluate performance on the test set.
9.  Generate predictions using a 0.5 probability threshold.
10. Plot training and validation accuracy.
11. Run the reusable `predict_breast_cancer()` function on a sample
    record.

## Results

In the notebook's recorded run:

  Metric               Result
  ------------------ --------
  Training samples        455
  Test samples            114
  Test loss            0.0789
  Test accuracy        98.25%

These values are from one run and may vary with changes to the dataset,
environment, or training configuration. Accuracy alone does not
establish clinical reliability; additional metrics such as sensitivity,
specificity, precision, recall, F1-score, and a confusion matrix should
be evaluated before drawing broader conclusions.

## Setup and Execution

### 1. Clone or download the repository

``` bash
git clone <your-repository-url>
cd <your-repository-folder>
```

Replace the placeholders with your repository URL and folder name.

### 2. Create and activate a virtual environment (recommended)

``` bash
python -m venv .venv
```

Linux/macOS:

``` bash
source .venv/bin/activate
```

Windows PowerShell:

``` powershell
.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

``` bash
pip install numpy pandas matplotlib scikit-learn tensorflow jupyter
```

### 4. Add the dataset

Place `data.csv` in the notebook's working directory, or update the CSV
path in the notebook.

### 5. Launch Jupyter Notebook

``` bash
jupyter notebook
```

Open `Untitled1(1).ipynb` and run the cells from top to bottom.

## Prediction Function

The notebook defines `predict_breast_cancer(features)`, which accepts a
sequence of 30 feature values in the same order as the training dataset.
It scales the input, obtains the model's sigmoid output, and returns a
predicted class and a model-derived confidence-like percentage.

The returned percentage is **not a clinically validated probability**.
Input values must match the training feature order and units.

## Suggested Repository Structure

``` text
breast-cancer-ann/
├── Untitled1(1).ipynb
├── data.csv                 # Include only if licensing permits
├── README.md
└── requirements.txt         # Optional: record tested dependencies
```

## Future Improvements

-   Add a confusion matrix and classification report.
-   Evaluate precision, recall, F1-score, sensitivity, and specificity.
-   Use cross-validation and compare against baseline models.
-   Add early stopping and model checkpointing.
-   Save and reload the trained model and scaler for repeatable
    inference.
-   Add input validation and tests for the prediction function.
-   Record package versions and make the notebook reproducible.

## Disclaimer

This repository is intended for learning and experimentation with neural
networks. It is not intended for diagnosis, screening, treatment, or
other clinical use. Consult qualified healthcare professionals for
medical decisions.
