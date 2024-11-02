# **Report on Credit Approval Dataset Analysis and Classification**

## Introduction

This report details the analysis and classification of the Credit Approval dataset, sourced from the UCI Machine Learning Repository. 
The goal is to predict whether a credit application will be approved based on various financial and personal features of the applicants. 
The report includes data preprocessing, exploratory data analysis, model training, and evaluation.
The dataset comprises features related to credit applicants, including demographic information and financial indicators. The following steps were taken:

1. **Data Retrieval:** The dataset was fetched using the fetch_ucirepo function from the ucimlrepo library.

2. **Data Preparation:** The dataset was converted into Pandas DataFrames for analysis.
   
3. **Handling Missing Values:** Rows with missing values were dropped from the DataFrame to ensure a complete dataset for analysis.
4. **Encoding Categorical Variables:** Categorical features were transformed into numerical format using one-hot encoding.

## Exploratory Data Analysis (EDA)
**Distribution of Numerical Features**
Numerical features were assessed for their distribution using histograms and box plots. 
This analysis is crucial to identify outliers and understand the underlying distribution of the data.
-Histograms: Plots were created for each numerical feature to visualize the distribution, employing Seaborn's histplot.
-Box Plots: Box plots were generated to identify potential outliers within the numerical features.
-Skewness and Kurtosis
Skewness and kurtosis were computed for each numerical feature to assess their distributions further.

## Model Training
**Data Splitting**
The dataset was split into training and testing sets (80% training and 20% testing) to ensure robust evaluation of the model's performance.
To enhance model performance, feature scaling was performed using the StandardScaler from scikit-learn.

**Model Selection and Hyperparameter Tuning**
An XGBoost classifier was chosen for its efficiency in handling classification tasks. 
A grid search was performed to identify the best hyperparameters, optimizing for the ROC AUC score.

**Model Evaluation**
The best model was evaluated on the test set using confusion matrix and classification report, providing insights into its performance.

# **Overall Assessment:**
## **Confusion Matrix:*

The confusion matrix shows the following counts: **True Negatives (TN): 47** **False Positives (FP): 8** **False Negatives (FN): 13** **True Positives (TP): 63**. This indicates that out of 131 predictions: The model correctly identified 47 instances of the negative class (0) and 63 instances of the positive class (1). However, it misclassified 8 negative instances as positive and 13 positive instances as negative.

## **Classification Report:**
The report reveals: **Precision for class 0: 0.78**, and for **class 1: 0.89** **Recall for class 0: 0.85**, and for **class 1: 0.83**, **F1-Score: 0.82** for class 0 and 0.86 for class 1 The model has a good balance between precision and recall, especially for class 1, where it excels in correctly identifying positive instances while maintaining a low rate of false positives. The overall accuracy of 84% suggests that the model performs well, making it reliable for classification tasks.

## **ROC AUC Score:**
A **ROC AUC score of 0.9194** indicates excellent discrimination ability between classes. This score demonstrates that the model effectively differentiates between the positive and negative classes across various threshold settings. Such a high score strengthens the model's reliability and suggests that it can be effectively used in applications where accurate classification is critical.

## **Conclusion:**
Overall, your model exhibits strong performance, as indicated by the confusion matrix, classification report, and ROC AUC score. The combination of high precision, recall, F1-scores, and a high AUC suggests that it is well-suited for classification tasks, particularly in scenarios where misclassifying instances could have significant implications.
