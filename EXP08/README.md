# Experiment 08: Deep Learning Application for Breast Cancer Classification

## Aim

Implement a deep learning application for breast cancer classification
using the **Breast Cancer Wisconsin Diagnostic Dataset**. This project
is based on the supplied Experiment 08 document and uses an Artificial
Neural Network (ANN) with TensorFlow/Keras.

> **Educational use only:** This model is not clinically validated and
> must not be used for medical diagnosis or treatment decisions.

## Dataset

The notebook expects a CSV file named `data.csv`.

-   Target column: `diagnosis`
-   Labels: `M` = Malignant, `B` = Benign
-   Encoding: `M` → `1`, `B` → `0`
-   Numerical diagnostic features are used as inputs.
-   Identifier and optional unused columns (`id`, `Unnamed: 32`) are
    excluded.

The supplied experiment document shows 569 records and 30 input features
after preprocessing. Place `data.csv` beside the notebook, or update
`DATA_PATH`.

## Model Architecture

1.  Input layer matching the feature count
2.  Dense layer with 32 neurons and ReLU activation
3.  Dropout layer with rate `0.2`
4.  Dense layer with 16 neurons and ReLU activation
5.  Output layer with 1 neuron and sigmoid activation

### Training configuration

-   Optimizer: Adam
-   Loss: Binary cross-entropy
-   Metric: Accuracy
-   Epochs: 30
-   Batch size: 16
-   Test size: 20%
-   Validation split: 20% of training data
-   Random state: 42
-   Stratified train/test split

## Workflow

1.  Import libraries and load the CSV.
2.  Prepare input features and binary target labels.
3.  Split the data into training and testing sets.
4.  Standardize features with `StandardScaler`.
5.  Create, compile, and train the ANN.
6.  Evaluate test loss and accuracy.
7.  Generate predictions and compare actual/predicted labels.
8.  Plot training and validation accuracy.
9.  Test a reusable prediction function with one dataset record.

## Recorded Results

The supplied experiment document reports:

  Metric                    Reported value
  --------------- ------------------------
  Test loss         Approximately `0.0789`
  Test accuracy     Approximately `98.25%`

These are the recorded results from the source document. Your results
may differ because neural-network training can be stochastic.

## Technologies

-   Python, Jupyter Notebook
-   NumPy, pandas
-   TensorFlow / Keras
-   Matplotlib
-   scikit-learn

## Installation and Execution

Create a virtual environment (recommended):

``` bash
python -m venv .venv
source .venv/bin/activate
```

On Windows PowerShell, activate with:

``` powershell
.venv\Scripts\Activate.ps1
```

Install dependencies:

``` bash
pip install numpy pandas tensorflow matplotlib scikit-learn jupyter
```

Place `data.csv` in the same directory as `BEIT_36_AIDS_EXP08.ipynb`,
then launch:

``` bash
jupyter notebook
```

Open `BEIT_36_AIDS_EXP08.ipynb` and run the cells from top to bottom.

## Suggested Repository Structure

``` text
breast-cancer-deep-learning/
├── BEIT_36_AIDS_EXP08.ipynb
├── data.csv                 # Include only if licensing permits
├── README.md
└── requirements.txt         # Optional
```

## Notes

-   The notebook uses a portable relative path (`data.csv`) instead of
    the machine-specific path shown in the source document.
-   Prediction inputs must follow the exact feature order used for
    training.
-   The prediction score is not a clinically validated probability.
-   Confirm dataset licensing before publishing the CSV in a public
    repository.

## Disclaimer

This project is intended for academic learning only. It is not designed
or validated for clinical diagnosis, screening, or treatment decisions.
Consult qualified healthcare professionals for medical advice.
