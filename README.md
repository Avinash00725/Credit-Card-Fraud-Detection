# Credit Card Fraud Detection

## Overview
This project develops a classification model to detect fraudulent credit card transactions using the [Kaggle Credit Card Fraud Detection dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud). The goal is to minimize false positives while ensuring high accuracy, addressing class imbalance and engineering meaningful features.

## Dataset
- Source: Kaggle (creditcard.csv)
- Features: Anonymized (V1-V28), Time, Amount
- Target: Fraud (0 = Legit, 1 = Fraud)
- Imbalance: ~0.17% fraud cases

## Approach
1. **Preprocessing**:
   - Scaled Amount, Tx_Frequency, Amount_Deviation
   - Dropped Time column
2. **Feature Engineering**:
   - Transaction frequency per hour
   - Amount deviation from hourly average
   - Night transaction flag
3. **Class Imbalance**:
   - SMOTE, RandomUnderSampler, and class weights
4. **Models**:
   - Logistic Regression (baseline)
   - Random Forest
   - XGBoost (tuned with RandomizedSearchCV)
5. **Evaluation**:
   - ROC AUC, precision, recall, F1-score
   - Precision-recall curve and threshold tuning to minimize false positives
   - Cross-validation for robustness

## Results
- Best Model: Tuned XGBoost
- ROC AUC: 0.9335
- Precision for Fraud: 0.82

## How to Run
1. Clone the repository:
   ```bash
   git clone <repo-url>
