# Classification Lecture Notes

## 1. Introduction to Classification
Classification is a supervised learning approach where the goal is to predict categorical labels based on input features. This chapter introduces classification problems and covers how to:

- Split data into training and test sets.
- Train a classification model.
- Make predictions.
- Evaluate model accuracy.
- Understand model complexity and performance.

The example dataset used is a telecom churn dataset, where the task is to classify whether a customer will churn or not.

## 2. Machine Learning Overview

### 2.1 What is Machine Learning?
Machine learning enables computers to learn from data and make predictions or decisions without explicit programming.

### 2.2 Examples of Machine Learning
- **Spam detection**: Classifying emails as spam or not.
- **Book categorization**: Grouping books based on content and assigning labels.

### 2.3 Types of Machine Learning
- **Unsupervised Learning**: Identifying hidden patterns without labeled data (e.g., clustering customers by purchasing behavior).
- **Supervised Learning**: Learning from labeled data to make predictions (e.g., classifying fraudulent bank transactions).

### 2.4 Supervised Learning Types
- **Classification**: Predicting a categorical label (e.g., fraud detection, customer churn prediction).
- **Regression**: Predicting continuous values (e.g., house price prediction).

### 2.5 Naming Conventions
- **Feature** = Predictor variable / Independent variable.
- **Target Variable** = Dependent variable / Response variable.

### 2.6 Prerequisites for Supervised Learning
Before applying supervised learning, data should:
- Have no missing values.
- Be numerical.
- Be stored in Pandas DataFrames, Series, or NumPy arrays.

### 2.7 Scikit-Learn Workflow
Scikit-learn provides a standard workflow for supervised learning:
1. Import the model.
2. Instantiate the model.
3. Fit the model using training data.
4. Predict on new data.
5. Evaluate performance.

Example: Training a k-Nearest Neighbors (KNN) classifier.
```python
from sklearn.neighbors import KNeighborsClassifier

# Prepare data
y = churn_df["churn"].values
X = churn_df[["account_length", "customer_service_calls"]].values

# Instantiate KNN model with 6 neighbors
knn = KNeighborsClassifier(n_neighbors=6)

# Train the model
knn.fit(X, y)
```

## 3. Binary Classification
Binary classification involves predicting a target variable with two possible outcomes (e.g., churn or no churn, fraud or not fraud). Labels are often represented as 0 and 1.

Example dataset:
```
   account_length  total_day_charge  total_eve_charge  total_night_charge  total_intl_charge  customer_service_calls  churn
0             101             45.85             17.65                9.64               1.22                       3      1
1              73             22.30              9.05                9.98               2.75                       2      0
```

## 4. k-Nearest Neighbors (KNN)

### 4.1 KNN Algorithm
KNN classifies data points based on the majority label of their k-nearest neighbors.

- If **k=3**, the label is determined by the three closest points.
- If **k=5**, the label is determined by the five closest points.

### 4.2 Intuition
A scatter plot of total evening charge vs. total day charge can be used to classify customer churn. A decision boundary is formed to separate customers who are likely to churn from those who are not.

### 4.3 Implementing KNN with Scikit-Learn
```python
from sklearn.neighbors import KNeighborsClassifier 

# Prepare data
y = churn_df["churn"].values
X = churn_df[["account_length", "customer_service_calls"]].values

# Create and fit the classifier
knn = KNeighborsClassifier(n_neighbors=6)
knn.fit(X, y)
```

### 4.4 Making Predictions
```python
# New data points
X_new = [[120, 5], [80, 1], [95, 3]]

# Predict using the trained classifier
predictions = knn.predict(X_new)
print(predictions)  # Example output: [1, 0, 0]
```

## 5. Summary
- **Classification** is used for categorical predictions.
- **Binary classification** deals with two possible outcomes (e.g., churn vs. no churn).
- **KNN** is a simple, intuitive classification algorithm based on majority voting among neighbors.
- **Scikit-learn** provides a streamlined workflow for implementing classification models.
- **Model evaluation** is crucial to ensure good generalization to unseen data.

### Next Steps
- Explore different classification models.
- Optimize KNN by tuning hyperparameters.
- Apply classification techniques to real-world datasets.
