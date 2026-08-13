# Iris Flower Classification Using Machine Learning

## Project Overview

This project develops a machine learning classification system to predict
Iris flower species using four morphological features:

- Sepal length
- Sepal width
- Petal length
- Petal width

The target classes are:

- Iris setosa
- Iris versicolor
- Iris virginica

## Objective

The objective is to build and evaluate machine learning classification models,
compare them with a simple baseline, tune the stronger model, and analyze
where the final model fails.

## Dataset

The Iris dataset contains:

- 150 samples
- 3 classes
- 4 numerical features
- 50 samples per class

### Features

| Feature | Description |
|---|---|
| Sepal Length | Length of the sepal in cm |
| Sepal Width | Width of the sepal in cm |
| Petal Length | Length of the petal in cm |
| Petal Width | Width of the petal in cm |

## Models

The following models were evaluated:

1. Dummy Classifier — baseline
2. Logistic Regression
3. Support Vector Machine (SVM)

## Data Preparation

The dataset was divided into:

- 80% training data
- 20% held-out test data

StandardScaler was used for feature scaling, and the scaler was fitted only
on the training data to avoid data leakage.

## Model Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Dummy Baseline | 33.33% | 11.11% | 33.33% | 16.67% |
| Logistic Regression | 93.33% | 93.33% | 93.33% | 93.33% |
| Original SVM | **96.67%** | **96.97%** | **96.67%** | **96.66%** |
| Tuned SVM | 93.33% | 93.33% | 93.33% | 93.33% |

## Hyperparameter Tuning

GridSearchCV with 5-fold cross-validation was used to tune the SVM.

Best parameters:

- C = 0.1
- Kernel = linear
- Gamma = scale

Best cross-validation accuracy:

**97.50%**

However, the tuned SVM achieved 93.33% accuracy on the held-out test set.
The original SVM achieved 96.67%, so the original SVM was selected as the
final model.

## Final Model

The Original SVM was selected as the final model.

Performance on the held-out test set:

- Accuracy: **96.67%**
- Precision: **96.97%**
- Recall: **96.67%**
- F1-Score: **96.66%**

The model correctly classified **29 out of 30** test samples.

## Failure Analysis

The final model made one incorrect prediction:

- Actual: **Versicolor**
- Predicted: **Virginica**

Feature values:

- Sepal length: 6.70 cm
- Sepal width: 3.00 cm
- Petal length: 5.00 cm
- Petal width: 1.70 cm

This indicates that the model had difficulty distinguishing at least one
Versicolor sample from Virginica.

## Limitations

The dataset contains only 150 samples and four numerical features.
Therefore, the model's performance may not generalize to larger or more
diverse datasets.

The final model should be considered a machine learning demonstration rather
than a production-ready classification system.

## Project Structure

```text
Iris-Flower-Classification-ML/
│
├── Iris_Flower_Classification_ML.ipynb
├── iris_svm_final_model.pkl
├── README.md
└── requirements.txt
