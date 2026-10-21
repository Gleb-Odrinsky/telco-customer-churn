# Telco Customer Churn Prediction

## Project Overview
This project uses Machine Learning to predict customer churn for a telecom company. 
The goal is to help the retention department find customers who are about to leave, so they can offer them a discount and save them.

## Dataset and Metric
* **Dataset:** [Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) (7043 rows, 21 columns).
* **Main metric:** **Recall**. It is much cheaper for the business to give a discount to a loyal client (false alarm) than to lose a real customer. Therefore, we optimize for finding as many churners as possible.

## Tech Stack and Methods
* **Languages and Libraries:** Python, Pandas, Numpy, Scikit-learn.
* **Preprocessing:** I used `Pipeline` and `ColumnTransformer` to prevent data leakage. 
  * Fixed `TotalCharges` (it contained spaces instead of numbers).
  * Filled missing values (median for numbers, most frequent for text).
  * Scaled numeric features (`StandardScaler`).
  * Encoded categorical features (`OneHotEncoder`).
* **Models compared:** Logistic Regression, Random Forest, Gradient Boosting, SVM, KNN.
* **Optimization:** `GridSearchCV` for hyperparameter tuning.

## Results
* **Best Model:** Logistic Regression (`C=1`, `solver='liblinear'`).
* **Final Recall (Class 1):** **0.78** (The model successfully finds 78% of customers who want to leave).
* **Final Precision (Class 1):** **0.50**.
* **Business value:** The model makes some false alarms, but it is highly effective at catching the real churners, which saves the company money.