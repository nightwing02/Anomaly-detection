# Credit Card Fraud Anomaly Detection

This project demonstrates the application of anomaly detection techniques to identify fraudulent credit card transactions from a dataset containing over 280,000 rows and 31 columns. Anomaly detection is a crucial task in the realm of fraud prevention, where the goal is to identify unusual or unexpected patterns that deviate from the norm.

## Table of Contents
- [Introduction](#introduction)
- [Data](#data)
- [Anomaly Detection Algorithms](#anomaly-detection-algorithms)
- [Results](#results)
- [Observations and Analysis](#observations-and-analysis)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [Acknowledgments](#acknowledgments)

## Introduction

Credit card fraud is a significant concern for financial institutions and customers alike. Traditional methods of fraud detection might not always be effective in identifying sophisticated fraudulent transactions. This project explores the application of anomaly detection algorithms to detect such fraudulent activities.

## Data

The dataset used in this project contains over 280,000 rows and 31 columns, representing various features extracted from credit card transactions. Each row represents a transaction, and the columns contain information such as transaction amount, time, and other relevant features.

## Anomaly Detection Algorithms

### Isolation Forest

Isolation Forest is an ensemble-based anomaly detection algorithm that works by isolating instances into individual trees. Anomalies are expected to have shorter paths in the tree structure, making them easier to isolate. This algorithm excels in identifying isolated anomalies and is relatively computationally efficient.

### Local Outlier Factor (LOF)

Local Outlier Factor is a density-based anomaly detection algorithm that assesses the local density deviation of a data point with respect to its neighbors. Points with significantly lower density than their neighbors are considered outliers. LOF can identify anomalies in more complex data distributions.

### Support Vector Machine (SVM)

Support Vector Machine is a powerful machine learning algorithm that can also be used for anomaly detection. However, due to the size of the dataset, obtaining results using SVM proved to be challenging and computationally intensive. Therefore, SVM results are not included in this analysis.

## Results

After applying Isolation Forest and Local Outlier Factor algorithms to the dataset, the following classification report was obtained:

```
             Isolation Forest : 675
Accuracy Score : 
0.9976299739823811
Classfication Report: 
              precision    recall  f1-score   support

           0       1.00      1.00      1.00    284315
           1       0.31      0.32      0.31       492

    accuracy                           1.00    284807
   macro avg       0.66      0.66      0.66    284807
weighted avg       1.00      1.00      1.00    284807

Local Outlier Factor : 4600
Accuracy Score : 
0.9838487115836339
Classfication Report: 
              precision    recall  f1-score   support

           0       1.00      0.99      0.99    284315
           1       0.02      0.20      0.04       492

    accuracy                           0.98    284807
   macro avg       0.51      0.59      0.52    284807
weighted avg       1.00      0.98      0.99    284807
```

## Observations and Analysis

The performance of Isolation Forest and Local Outlier Factor on the credit card fraud dataset can be summarized as follows:

**Isolation Forest:**
- Identified 675 instances as anomalies.
- Achieved an accuracy of approximately 99.76%.
- Showed better precision, recall, and F1-score for detecting fraudulent transactions compared to LOF.

**Local Outlier Factor (LOF):**
- Identified 4600 instances as anomalies.
- Achieved an accuracy of approximately 98.38%.
- Demonstrated low precision, recall, and F1-score for detecting fraudulent transactions.

Both algorithms struggled with the class imbalance in the dataset, but Isolation Forest outperformed LOF in most evaluation metrics.

## Usage

1. Clone this repository to your local machine.
2. Install the required dependencies (see [Dependencies](#dependencies)).
3. Run the provided Jupyter Notebook to see the implementation of Isolation Forest and Local Outlier Factor on the credit card fraud dataset.
4. (Optional) Attempt the SVM implementation by modifying the code and using a more powerful computing environment.

## Dependencies

- Python 3.x
- Jupyter Notebook
- Pandas
- Scikit-learn

Install the required dependencies using the following command:

```
pip install pandas scikit-learn
```

## Acknowledgments

The dataset used in this project is sourced from [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud). Special thanks to the open-source community for providing valuable resources and algorithms for anomaly detection.

Feel free to customize this README section according to your project's specific details and outcomes.
