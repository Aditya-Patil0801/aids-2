# AIDS-2 Practical Experiments

## 📌 About the Project

This repository contains practical implementations for **Artificial Intelligence and Data Science (AIDS-2)** using Python. It covers Bayesian Networks, cognitive applications, fuzzy logic, neural networks, deep learning, and machine learning classification algorithms.

## 🎯 Objectives

- Understand fundamental AI and machine learning concepts.
- Implement Bayesian Networks and probabilistic inference.
- Build a simple insurance question-answering application.
- Implement fuzzy membership functions, fuzzy set operations, and fuzzy control systems.
- Apply Artificial Neural Networks (ANN) and Convolutional Neural Networks (CNN).
- Classify breast cancer data using machine learning and deep learning algorithms.
- Evaluate and compare classification models.

## 🧪 Experiments Covered

| Experiment | Title |
|---|---|
| 01 | Bayesian Network and Probabilistic Inference |
| 02 | Cognitive Application for Insurance |
| 03 | Fuzzy Membership Functions |
| 04 | Fuzzy Set Properties |
| 05 | Fuzzy Control System |
| 06 | Artificial Neural Network (ANN) |
| 07 | Convolutional Neural Network (CNN) |
| 08 | Deep Learning for Breast Cancer Classification |
| 09 | AdaBoost Classification |
| 10 | Random Forest Classification |
| 11 | Comparison of Classification Models |

## 🛠️ Technologies Used

- **Language:** Python
- **Environment:** Jupyter Notebook
- **Data Processing:** NumPy, Pandas
- **Visualization:** Matplotlib
- **Machine Learning:** Scikit-learn
- **Deep Learning:** TensorFlow / Keras
- **Bayesian Networks:** pgmpy
- **Fuzzy Logic:** pyit2fls, scikit-fuzzy
- **Network Visualization:** NetworkX

## 📊 Dataset

The machine learning and deep learning experiments use the **Breast Cancer Wisconsin Diagnostic dataset**.

The dataset contains numerical features extracted from breast cancer cell nuclei.

- **Input:** Numerical measurements of cell nuclei.
- **Target:** Diagnosis.
- **Benign (B):** Encoded as `0`.
- **Malignant (M):** Encoded as `1`.

The insurance cognitive application uses predefined insurance questions and answers.

## ⚙️ Installation and Execution

### 1. Clone the repository

```bash
git clone https://github.com/Aditya-Patil0801/aids-2.git
cd aids-2
```

### 2. Install the required libraries

```bash
pip install numpy pandas matplotlib scikit-learn tensorflow pgmpy networkx pyit2fls scikit-fuzzy jupyter
```

### 3. Prepare the dataset

Place the required dataset in an accessible location and update the CSV file path in the notebook.

For example:

```python
df = pd.read_csv("data.csv")
```

### 4. Run the notebook

```bash
jupyter notebook AIDS_EXP12.ipynb
```

Run the cells in sequence and review the generated outputs, graphs, predictions, and evaluation metrics.

## 🎓 External Viva Questions and Answers

### Q1. What is Artificial Intelligence?

Artificial Intelligence (AI) is a branch of computer science that enables machines to perform tasks that normally require human intelligence.

### Q2. What is a Bayesian Network?

A Bayesian Network is a probabilistic graphical model that represents variables and their conditional dependencies using a directed acyclic graph (DAG).

### Q3. What is fuzzy logic?

Fuzzy logic handles uncertainty using degrees of membership between 0 and 1 rather than only true or false values.

### Q4. What is a membership function?

A membership function assigns a degree of membership between 0 and 1 to an element in a fuzzy set.

### Q5. What is an ANN?

An Artificial Neural Network is a machine learning model inspired by the structure of biological neural networks.

### Q6. What is a CNN?

A Convolutional Neural Network is a deep learning model that uses convolutional layers to learn patterns from data.

### Q7. What is the difference between ANN and CNN?

ANN generally uses fully connected layers, whereas CNN uses convolutional layers to learn local patterns and features.

### Q8. What is AdaBoost?

AdaBoost is an ensemble learning algorithm that combines multiple weak learners to create a stronger classifier.

### Q9. What is Random Forest?

Random Forest is an ensemble algorithm that combines multiple decision trees to improve prediction performance.

### Q10. What is overfitting?

Overfitting occurs when a model learns the training data too closely and performs poorly on unseen data.

### Q11. Why do we split a dataset into training and testing sets?

The training set is used to train the model, while the testing set evaluates its performance on unseen data.

### Q12. What is feature scaling?

Feature scaling brings numerical features to a comparable scale, helping certain algorithms train more effectively.

### Q13. What is accuracy?

Accuracy is the proportion of all predictions that are correct.

`Accuracy = Correct Predictions / Total Predictions`

### Q14. What are precision and recall?

- **Precision:** Of all positive predictions, how many were actually positive?
- **Recall:** Of all actual positive cases, how many were correctly identified?

### Q15. What is a confusion matrix?

A confusion matrix summarizes classification results using true positives, true negatives, false positives, and false negatives.

### Q16. What is the difference between classification and regression?

Classification predicts categories, while regression predicts continuous numerical values.

### Q17. Why is Python used in AI and machine learning?

Python has simple syntax and provides libraries for data processing, visualization, machine learning, and deep learning.

### Q18. What is TensorFlow?

TensorFlow is a machine learning framework used to develop and train machine learning and deep learning models.

### Q19. What is Scikit-learn?

Scikit-learn is a Python library that provides machine learning algorithms, preprocessing tools, and evaluation metrics.

### Q20. What is the purpose of comparing classification models?

Model comparison helps identify which algorithm performs better according to metrics such as accuracy, precision, recall, and F1-score.

## ✅ Conclusion

These practicals demonstrate the application of AI, fuzzy logic, probabilistic reasoning, machine learning, and deep learning using Python. They provide practical experience in data preprocessing, model training, prediction, visualization, and model evaluation.
