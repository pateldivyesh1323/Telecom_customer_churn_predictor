# 📉 Telco Customer Churn Prediction

A machine learning project to predict customer attrition using the [Telco Customer Churn dataset](https://www.kaggle.com/blastchar/telco-customer-churn) from Kaggle. This project utilizes both unsupervised learning (K-Means) for customer segmentation and supervised learning (Logistic Regression) for churn prediction.

## 🚀 Key Results
* **Accuracy:** **82.24%** (Tied with top-voted Kaggle kernels using complex ensembles).
* **F1-Score (Non-Churn):** 0.89.
* **Class Imbalance Handling:** Successfully identified 58% of churners (Recall) despite them being the minority class, using weighted logistic regression.

## 📊 Project Overview
Customer churn is a critical metric for telecommunications companies. This project aims to:
1.  **Segment Customers:** Use K-Means clustering to find hidden patterns in customer behavior.
2.  **Predict Churn:** Build a baseline model to identify high-risk customers.
3.  **Explain Drivers:** specific features (like Contract Type and Tenure) that drive users to leave.

## 🛠️ Methodology & Workflow

### 1. Data Preprocessing
* **Cleaning:** Handled missing values in `TotalCharges` and removed duplicates.
* **Feature Engineering:** * Converted categorical variables using `LabelEncoder`.
    * Scaled numerical features (`Tenure`, `MonthlyCharges`) using `MinMaxScaler` to ensure distance-based algorithms (like K-Means) function correctly.
* **Imbalance Handling:** Addressed the 73:27 class imbalance by optimizing decision thresholds and model weights.

### 2. Unsupervised Learning (Customer Segmentation)
* **K-Means Clustering:** Applied the Elbow Method to determine the optimal number of clusters (k=4).
* **Insights:** The clusters revealed distinct groups, such as "New/Low-Spenders" vs. "Loyal/High-Spenders," helping to visualize risk profiles before modeling.

### 3. Supervised Learning (Churn Prediction)
* **Model:** Logistic Regression (Baseline).
* **Optimization:** Tuned regularization strength and class weights to maximize the F1-score rather than just accuracy.
* **Evaluation:**
    * **Confusion Matrix:** Analyzed False Negatives to understand missed churn opportunities.
    * **Feature Importance:** Identified that **Month-to-Month contracts** and **Fiber Optic services** were the strongest predictors of churn.

## 📈 Performance (Test Set)

| Metric | Score | Note |
| :--- | :--- | :--- |
| **Accuracy** | **0.82** | High baseline performance |
| **Precision (Class 0)** | 0.88 | Extremely reliable at identifying happy customers |
| **Recall (Class 1)** | 0.58 | Captures majority of churners despite imbalance |
