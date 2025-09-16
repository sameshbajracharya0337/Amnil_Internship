# Logistic Regression on Social Network Dataset

## This repository contains a logistic regression implementation to predict user purchases based on the Social Network Ads dataset from Kaggle. The project includes preprocessing, model training, evaluation, and a LaTeX document explaining the math behind logistic regression and its comparison to linear regression. Results are saved to a CSV file for analysis
# Dataset Description

## Source: I sourced a dataset from Kaggle. Its link is: 

https://www.kaggle.com/datasets/dragonheir/logistic-regression

## Dataset: Social Network Ads (Social_Network_Ads.csv) from Kaggle.
## Features: Gender (categorical), Age (integer), EstimatedSalary (integer).
## Target: Purchased (binary: 0 = not purchased, 1 = purchased).
## Size: 400 samples.

# Repository Structure

```bash
LinearRegression/
├── logistic-regression.ipynb  # Python script
├── requirements.txt              # Dependencies
├── Social_Network.csv               # Dataset (download from Kaggle)
├── test_predictions.csv  # Output predictions
├── roc_curve.png           # Output plot
├── confusion_matrix.png    # Output plot
├── LogisticRegression.pdf          # Pdf
└── README.md                       # This file
```

## Requirements
- Python 3.11+ (tested on 3.11.13)
- Dependencies: See `requirements.txt`.

# Logistic Regression Equations

## Logistic regression is designed for binary classification (e.g., Purchased = 0 or 1). It models the probability of the positive class (class 1) using the sigmoid function: 

## P(y = 1 | x) = σ(z) = 1 / (1 + e^(-z)) 

## where z = β₀ + β₁x₁ + β₂x₂ + … + βₙxₙ. The sigmoid maps 𝑧 to [0, 1], representing the probability of class 1. For predictions, a threshold (typically 0.5) is used: 

## ŷ = { 1   if σ(z) ≥ 0.5 
##     { 0   if σ(z) < 0.5 

## The model optimizes the binary cross-entropy (log loss) function: 

## J(β) = -(1/m) ∑[ yᵢ log(σ(zᵢ)) + (1 - yᵢ) log(1 - σ(zᵢ)) ] 

## Coefficients 𝛽 are updated via gradient descent: 

## J(β) = -(1/m) ∑[ yᵢ log(σ(zᵢ)) + (1 - yᵢ) log(1 - σ(zᵢ)) ] 

## where 𝛼 is the learning rate.

# Evaluation Metrics 
## 1. Accuracy: Proportion of correct predictions. 

## Accuracy = (TP + TN) / (TP + TN + FP + FN) 

## 2. Precision: Proportion of predicted positives that are correct. 

## Precision = TP / (TP + FP) 

## 3. Recall: Proportion of actual positives identified. 

## Recall = TP / (TP + FN)  

## 4. F1-Score: Harmonic mean of precision and recall.  

## F1 = 2 * (Precision * Recall) / (Precision + Recall) 

## 5. ROC-AUC: Area under the ROC curve, measuring class separation.

## ROC-AUC = ∫ TPR(FPR) d(FPR) 

## Where:  
## TP = True Positives   
## TN = True Negatives   
## FP = False Positives 
## FN = False Negatives 
## TPR = True Positive Rate = Recall 
## FPR = False Positive Rate = FP / (FP + TN) 


## Setup Instructions
### 1. Clone the repository:
```bash
git clone https://github.com/sameshbajracharya0337/Customer_Churn_Analysis_and_Prediction.git
cd LogisticRegression
```

### 2. Create and activate a virtual environment (optional but recommended):
```bash
python -m venv venv
source venv\Scripts\activate
```

### 3. Download Dataset
```bash
Visit Kaggle.
Download Social_Network_Ads.csv and place it in the project folder.
```
### 4. Install dependencies:
```bash
pip install -r requirements.txt
```
### 5. Run the Script



# Results
```bash
Accuracy: 0.89 (89% correct).



Precision (class 1): 0.91 (few false positives, good for ad targeting).



Recall (class 1): 0.75 (misses 25% of purchasers, due to class imbalance: 52 non-purchasers vs. 28 purchasers).



F1-Score (class 1): 0.82 (balanced precision and recall).



ROC-AUC: 0.97 (excellent probability calibration).



Confusion Matrix:

[[50  2]  # Class 0: Not Purchased
 [ 7 21]] # Class 1: Purchased
```