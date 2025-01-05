# Hybrid Credit Risk Assessment 💳🔍

Welcome to the **Hybrid Credit Risk Assessment** project! 🚀 This solution combines machine learning, Monte Carlo simulations, and alternative data to assess customer credit risk. 

## Files Included 📂
- **Datasets**: Financial and alternative data (CSV files) 📊
- **Code**: Python scripts for risk assessment and model training ⚙️
- **Notebooks**: Jupyter notebook for analysis 📓
# Real-Time Credit Risk Assessment Using Alternative Data 📊

This repository contains a system designed to assess credit risk in real-time using both traditional financial data and alternative data sources such as social media, utility payments, and spending habits. The system uses machine learning techniques to predict creditworthiness and provides lenders with a transparent and explainable credit risk score.

## Problem Statement 🧑‍💼

Many individuals lack sufficient credit history to access traditional lending products, even if they have steady income or positive financial behavior. This solution aggregates both traditional and alternative data to predict credit risk in real-time, allowing lenders to make more informed decisions. The goal is to:

1. **Aggregate and Process Alternative Data**: Combine traditional financial information with non-traditional data sources.
2. **Predict Creditworthiness**: Use machine learning models to estimate the probability of default (credit risk).
3. **Provide Explainable Credit Risk Scores**: Ensure the model's decisions are transparent and interpretable.

## Approach 📌

The approach used for credit risk assessment follows these key steps:

### 1. **Data Collection & Aggregation**
The system uses two types of data:
- **Traditional Financial Data**: Information like monthly income, credit score, debt-to-income ratio, employment length, and the number of credit lines.
- **Alternative Data**: Information from non-traditional sources like social media sentiment, utility payments (on-time or late), transaction history (monthly spending and spending volatility), and digital footprint score (based on online activity).

### 2. **Data Preprocessing**
Two separate preprocessing methods are used for the traditional and alternative data:

- **Traditional Data Preprocessing**: The following features are extracted:
  - **Income**: Monthly income of the individual.
  - **Credit Score**: A numerical value representing the individual's credit history.
  - **Debt-to-Income Ratio**: The ratio of total debt to monthly income, which is an indicator of financial burden.
  - **Employment Length**: The number of years the individual has been employed.
  - **Number of Credit Lines**: The number of credit lines available to the individual.

- **Alternative Data Preprocessing**:
  - **Social Media Sentiment**: Analyzes social media posts using TextBlob sentiment analysis. The average sentiment score of posts is calculated (a score of -1 being highly negative and 1 being highly positive).
  - **Utility Payments**: Evaluates the utility payment behavior (on-time or late). The utility payment score is calculated by the ratio of on-time payments.
  - **Transaction History**: Analyzes transaction data (spending categories, amounts). Features like average monthly spending and spending volatility (standard deviation of spending) are calculated.
  - **Digital Footprint Score**: A score that indicates the level of an individual's online presence, which is treated as a numerical value between 0 and 1.

### 3. **Model Training**
Once the data is preprocessed, it is used to train machine learning models. The approach uses **Random Forest** and **Gradient Boosting** classifiers, which are evaluated using cross-validation:
- **Random Forest**: An ensemble method that constructs multiple decision trees and combines their results to make predictions.
- **Gradient Boosting**: A technique that builds models sequentially, where each new model corrects the errors of the previous one.

The model is selected based on cross-validation performance. The best model is then trained on the entire dataset, which can be used for real-time credit risk prediction.

### 4. **Risk Prediction**
The trained model predicts the credit risk for an individual by considering both traditional and alternative data. The credit risk score is calculated using the model's output probabilities, where a higher probability of default (class 1) indicates a higher risk. This score is scaled to a percentage (0-100), where a higher score represents lower risk.

Additionally, the system evaluates the importance of each feature in determining the final credit risk score. This allows lenders to understand which factors are contributing the most to the prediction.

### 5. **Monte Carlo Simulation**
To assess the variability in credit risk predictions, **Monte Carlo simulations** are run. This method generates multiple random samples based on the provided data and assesses how different data variations influence the final risk score. This provides a distribution of possible outcomes and helps to understand the uncertainty in the credit risk prediction.

The Monte Carlo results are used to estimate:
- **Mean Risk Score**: The average credit risk score across all simulations.
- **Standard Deviation**: The variability or uncertainty in the credit risk score.

### 6. **Risk Level Classification**
Based on the predicted risk score, the individual is classified into one of the following risk levels:
- **Low Risk**: Risk score >= 80
- **Moderate Risk**: Risk score >= 60 and < 80
- **High Risk**: Risk score >= 40 and < 60
- **Very High Risk**: Risk score < 40

This classification helps lenders make decisions about whether to approve or deny loans based on the risk assessment.

### 7. Visuals 📊
- **Feature Importance**: The importance of each feature (income, credit score, social media sentiment, etc.) is visualized using a bar plot. This shows how each feature contributes to the credit risk score prediction.
- **Monte Carlo Simulation Results**: The risk score distribution from the Monte Carlo simulations is plotted as a histogram, which helps visualize the uncertainty in the credit risk prediction.






