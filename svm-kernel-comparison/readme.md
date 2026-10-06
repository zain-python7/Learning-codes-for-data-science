# SVM Kernel Comparison

A machine learning experiment comparing different Support Vector Machine (SVM) kernels for binary classification.

The goal of this project is to understand how different SVM kernels perform when the relationship between features and the target is not purely linear.

## Dataset

The dataset is a small **synthetic dataset** containing:

* `Age`
* `Income`
* `Churn` — target variable (`0` or `1`)

The dataset was created for learning and experimentation rather than representing a real-world business dataset.

## Models Compared

The following models were evaluated:

* Linear SVM
* Polynomial SVM
* RBF SVM

Logistic Regression was also tested as a baseline model.

## Preprocessing

Before training the SVM models:

1. The data was divided into training and testing sets.
2. The features were standardized using `StandardScaler`.
3. The scaler was fitted only on the training data and then used to transform the test data.

Feature scaling is important for SVM because the algorithm is sensitive to the scale of the input features.

## Results

### Test Accuracy

| Model               | Accuracy |
| ------------------- | -------: |
| Logistic Regression |      70% |
| Linear SVM          |      84% |
| Polynomial SVM      |      80% |
| RBF SVM             |     100% |

### 5-Fold Cross-Validation

| Model          | Mean CV Accuracy |
| -------------- | ---------------: |
| Linear SVM     |            82.0% |
| Polynomial SVM |            89.5% |
| **RBF SVM**    |        **99.0%** |

RBF SVM achieved the highest cross-validation performance, with a mean accuracy of **99%** across the five folds.

## Key Observations

* Linear SVM performed better than Logistic Regression on this dataset.
* Polynomial SVM improved over Linear SVM in cross-validation.
* RBF SVM achieved the strongest performance by a significant margin.
* The results suggest that a **nonlinear decision boundary** is better suited to the pattern present in this dataset.
* Cross-validation provided a more reliable comparison than relying only on a single train/test split.

## Why RBF Performed Better

A linear SVM attempts to separate the classes using a straight decision boundary.

The RBF kernel can model more complex nonlinear relationships between the features and target. In this experiment, that flexibility allowed RBF SVM to capture the structure of the dataset much better.

## Evaluation

The models were evaluated using:

* Accuracy
* Confusion Matrix
* 5-Fold Cross-Validation

## Limitations

This project uses a **small synthetic dataset created for learning purposes**.

Therefore, the 99% cross-validation accuracy should not be interpreted as evidence that RBF SVM would achieve the same performance on a real-world churn dataset.

The main purpose of this project is to demonstrate:

* SVM fundamentals
* Kernel comparison
* Feature scaling
* Model evaluation
* Cross-validation
* Model selection

## Technologies Used

* Python
* Pandas
* Scikit-learn
* Jupyter Notebook

## Conclusion

Among the tested models, **RBF SVM was the best-performing model for this dataset**, achieving a mean 5-fold cross-validation accuracy of **99%**.

This experiment demonstrates why different SVM kernels can produce significantly different results depending on the structure of the data.
s