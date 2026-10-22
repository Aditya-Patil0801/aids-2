# Breast Cancer Classification Using AdaBoost

## Overview

This project uses the **AdaBoost (Adaptive Boosting) classifier** from
scikit-learn to classify breast cancer diagnostic records as **Benign**
or **Malignant**. The implementation is provided in a Jupyter Notebook
and uses the Breast Cancer Wisconsin Diagnostic dataset.

The notebook covers loading the dataset, preparing features and labels,
splitting the data into training and testing sets, training the AdaBoost
model, evaluating accuracy, and displaying a confusion matrix and
classification report.

> **Disclaimer:** This is an educational machine-learning project, not a
> medical diagnostic tool. Do not use its predictions to make healthcare
> decisions.

## Objectives

-   Load and inspect the breast cancer diagnostic dataset.
-   Prepare the feature matrix and binary target labels.
-   Split the data into training and test sets.
-   Train an AdaBoost classifier.
-   Evaluate the model using accuracy, a confusion matrix, and a
    classification report.
-   Visualize classification results.

## Dataset

The notebook uses a CSV file named `data.csv` containing the Breast
Cancer Wisconsin Diagnostic dataset.

-   **Records:** 569
-   **Input features:** 30 numerical features
-   **Target column:** `diagnosis`
-   **Labels:** `B` = Benign, `M` = Malignant
-   **Excluded columns:** `id`, `diagnosis` from the feature matrix, and
    `Unnamed: 32` if present

The target labels are encoded as:

-   `B` → `0`
-   `M` → `1`

### Dataset path

The notebook currently loads the dataset using a machine-specific path:

``` python
df = pd.read_csv("/home/aditya/Downloads/data.csv")
```

For portability, place `data.csv` in the same directory as the notebook
and change the code to:

``` python
df = pd.read_csv("data.csv")
```

Before publishing the dataset in a public repository, confirm that its
licensing and redistribution terms permit this.

## Technologies Used

-   Python
-   Jupyter Notebook
-   pandas
-   NumPy
-   scikit-learn
-   Matplotlib

## Model Details

The notebook uses `AdaBoostClassifier` with the following configuration:

  Parameter              Value
  ---------------------- ------------
  Number of estimators   50
  Learning rate          1.0
  Random state           42
  Test set size          20%
  Train/test split       Stratified

The dataset is split into 455 training records and 114 test records. The
notebook uses the default base estimator and other default settings
provided by the installed scikit-learn version.

## Workflow

1.  Import the required libraries.
2.  Load `data.csv` with pandas.
3.  Remove identifier and non-feature columns from the inputs.
4.  Encode diagnosis labels as numeric values.
5.  Split the dataset into training and testing sets using
    `train_test_split`.
6.  Create and train the AdaBoost classifier.
7.  Predict labels for the test set.
8.  Calculate test accuracy.
9.  Generate a confusion matrix and classification report.
10. Plot the confusion matrix.

## Results

The notebook's recorded execution produced the following results on the
114-record test set:

  Metric                        Result
  ----------------------- ------------
  Test accuracy                 98.25%
  Correct predictions       112 of 114
  Incorrect predictions       2 of 114

### Confusion matrix

Rows represent actual classes and columns represent predicted classes,
ordered as **Benign**, then **Malignant**:

  Actual / Predicted     Benign   Malignant
  -------------------- -------- -----------
  Benign                     72           0
  Malignant                   2          40

In this run, 72 benign records and 40 malignant records were classified
correctly. Two malignant records were classified as benign. These
results are from one split and do not establish clinical reliability;
additional validation is needed.

## Installation and Execution

### 1. Clone the repository

``` bash
git clone <your-repository-url>
cd <your-repository-folder>
```

Replace the placeholders with your repository URL and directory name.

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
pip install pandas numpy scikit-learn matplotlib jupyter
```

### 4. Add the dataset

Place `data.csv` in the notebook directory or update the CSV path in the
notebook.

### 5. Launch Jupyter Notebook

``` bash
jupyter notebook
```

Open `Untitled2.ipynb` and run the cells from top to bottom.

## Suggested Repository Structure

``` text
breast-cancer-adaboost/
├── Untitled2.ipynb
├── data.csv                 # Include only if licensing permits
├── README.md
└── requirements.txt         # Optional
```

## Future Improvements

-   Evaluate the model with cross-validation.
-   Compare AdaBoost with logistic regression, random forest, and other
    classifiers.
-   Add ROC and precision-recall curves.
-   Assess sensitivity, specificity, and other metrics relevant to the
    cost of missed malignant cases.
-   Save the fitted model and document a repeatable inference workflow.
-   Record package versions for reproducibility.

## Disclaimer

This project is intended for educational use only. It is not designed or
validated for clinical diagnosis, screening, or treatment decisions.
Consult qualified healthcare professionals for medical advice.
