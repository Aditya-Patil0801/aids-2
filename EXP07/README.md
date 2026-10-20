# Breast Cancer Classification Using Convolutional Neural Network (CNN)

## Overview

This project uses a **1D Convolutional Neural Network (CNN)** built with
TensorFlow/Keras to classify records from the Breast Cancer Wisconsin
Diagnostic dataset as **Malignant** or **Benign**.

The Jupyter Notebook demonstrates the machine-learning workflow: loading
the dataset, preparing the features and labels, splitting and
standardizing the data, reshaping it for a 1D CNN, training the model,
evaluating its performance, generating predictions, and plotting
training and validation accuracy.

> **Disclaimer:** This project is for educational purposes only. It is
> not a clinically validated diagnostic tool and must not be used to
> make medical decisions.

## Objectives

-   Load and inspect the breast cancer diagnostic dataset.
-   Separate the numerical input features from the diagnosis labels.
-   Split the data into training and test sets.
-   Standardize features using `StandardScaler`.
-   Reshape tabular features for a 1D CNN.
-   Build, compile, and train a CNN using TensorFlow/Keras.
-   Evaluate the model on held-out test data.
-   Compare actual and predicted labels.
-   Visualize training and validation accuracy.

## Dataset

The notebook uses a CSV file named `data.csv`, containing the Breast
Cancer Wisconsin Diagnostic dataset.

-   **Records:** 569
-   **Input features:** 30 numerical features
-   **Target column:** `diagnosis`
-   **Target labels:** `M` = Malignant, `B` = Benign
-   **Excluded columns:** `id`, `diagnosis` from the input features, and
    `Unnamed: 32` if present

The target labels are mapped to numeric values:

-   `M` → `1`
-   `B` → `0`

### Dataset path

The notebook currently loads the CSV from a machine-specific path:

``` python
df = pd.read_csv("/home/aditya/Downloads/data.csv")
```

For easier reuse, place `data.csv` in the same directory as the notebook
and update the code to:

``` python
df = pd.read_csv("data.csv")
```

Make sure you have permission to use and redistribute the dataset before
including it in a public repository.

## Technologies Used

-   Python
-   Jupyter Notebook
-   NumPy
-   pandas
-   TensorFlow / Keras
-   Matplotlib
-   scikit-learn

## CNN Architecture

The notebook creates a sequential 1D CNN with the following layers:

  Layer          Configuration
  -------------- --------------------------------------------
  Input          30 features reshaped to `(30, 1)`
  Conv1D         32 filters, kernel size 3, ReLU activation
  MaxPooling1D   Pool size 2
  Flatten        Converts feature maps to a vector
  Dense          16 neurons, ReLU activation
  Output         1 neuron, sigmoid activation

### Training configuration

-   **Optimizer:** Adam
-   **Loss function:** Binary cross-entropy
-   **Metric:** Accuracy
-   **Epochs:** 30
-   **Batch size:** 16
-   **Test size:** 20%
-   **Validation split:** 20% of the training data
-   **Random state:** 42
-   **Stratification:** Enabled for the train/test split

The `StandardScaler` is fitted on the training features and then applied
to both training and test features. The standardized features are
reshaped to three dimensions to match the CNN input format.

## Workflow

1.  Import the required libraries.
2.  Load the dataset from `data.csv`.
3.  Remove identifier and non-feature columns from the inputs.
4.  Encode diagnosis labels as binary values.
5.  Split the dataset into training and test subsets.
6.  Standardize the features.
7.  Reshape the feature arrays for the 1D CNN.
8.  Create and compile the CNN.
9.  Train the model and record training/validation metrics.
10. Evaluate test loss and accuracy.
11. Generate predictions using a 0.5 threshold.
12. Display actual versus predicted labels.
13. Plot training and validation accuracy.

## Results

The notebook's saved execution produced these test-set results:

  Metric               Result
  ------------------ --------
  Training records        455
  Test records            114
  Test loss            0.0525
  Test accuracy        98.25%

These results represent one recorded run and can vary with changes to
the environment, data, or model configuration. Accuracy alone does not
establish clinical reliability. Consider adding a confusion matrix and
metrics such as precision, recall, F1-score, sensitivity, and
specificity for a more complete evaluation.

## Installation and Execution

### 1. Clone the repository

``` bash
git clone <your-repository-url>
cd <your-repository-folder>
```

Replace the placeholders with your actual repository URL and directory
name.

### 2. Create a virtual environment (recommended)

``` bash
python -m venv .venv
```

Activate it on Linux/macOS:

``` bash
source .venv/bin/activate
```

Activate it on Windows PowerShell:

``` powershell
.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

``` bash
pip install numpy pandas matplotlib scikit-learn tensorflow jupyter
```

### 4. Add the dataset

Place `data.csv` in the notebook directory or update the CSV path in the
notebook.

### 5. Launch Jupyter Notebook

``` bash
jupyter notebook
```

Open `Untitled.ipynb` and run the cells from top to bottom.

## Suggested Repository Structure

``` text
breast-cancer-cnn/
├── Untitled.ipynb
├── data.csv                 # Include only if licensing permits
├── README.md
└── requirements.txt         # Optional: record tested dependencies
```

## Future Improvements

-   Add a confusion matrix and a classification report.
-   Evaluate precision, recall, F1-score, sensitivity, and specificity.
-   Compare the CNN with baseline models such as logistic regression and
    a dense neural network.
-   Use cross-validation and early stopping.
-   Save the trained model and preprocessing scaler for repeatable
    inference.
-   Add tests and input validation.
-   Record dependency versions to improve reproducibility.

## Disclaimer

This repository is intended for educational experimentation with deep
learning. The model is not designed or validated for clinical diagnosis,
screening, or treatment decisions. Consult qualified healthcare
professionals for medical advice.
