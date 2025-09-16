# Linear Regression on Salary Dataset

## This project implements simple linear regression to predict salaries based on years of experience using the Salary Dataset from Kaggle. The implementation uses scikit-learn to fit the model and calculates R-squared, Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and Mean Absolute Error (MAE). A visualization of the regression line is included to illustrate the model’s fit.

# Dataset Description

## Source: I sourced a dataset from Kaggle. Its link is: 

https://www.kaggle.com/datasets/abhishek14398/salary-dataset-simple-linear-regression/data

## Columns: (30 rows, 3 columns) 
## • YearsExperience: Years of work experience (numeric, float, e.g., 1.1 to 10.5). 
## • Salary: Annual salary in dollars (numeric, float, e.g., 39343.0 to 122391.0). 

# Repository Structure

```bash
LinearRegression/
├── linear-regression.ipynb  # Python script
├── requirements.txt              # Dependencies
├── Salary_Data.csv               # Dataset (download from Kaggle)
├── Salary_Predictions_sklearn.csv  # Output predictions
├── regression_plot.png           # Output plot
├── LinearRegression.pdf          # Pdf
└── README.md                       # This file
```

## Requirements
- Python 3.11+ (tested on 3.11.13)
- Dependencies: See `requirements.txt`.

# Linear Regression Equations

## Linear regression models the relationship between the independent variable (YearsExperience, denoted ( x )) and the dependent variable (Salary, denoted ( y )) using a linear equation: 

## y = β₀ + β₁x + ε 

## • ( β₀ ): Intercept (predicted salary when years of experience is 0). 
## • ( β₁ ): Slope (change in salary per additional year of experience). 
## • ( ε ): Error term (random variation, assumed normally distributed with mean 0). 

## The goal is to find ( β₀  ) and ( β₁ ) that minimize the Sum of Squared Errors (SSE): 

## SSE = ∑(yᵢ - ŷᵢ)² 

## Where: 

## • ( yᵢ ): Actual salary for the ( i )-th observation. 
## • ( ŷᵢ = β₀ + β₁xᵢ ): Predicted salary. 
## • ( n ): Number of observations (30). 

## scikit-learn’s LinearRegression internally uses Ordinary Least Squares (OLS) to compute: 

## [β₁ = [ ∑(xᵢ - x̄ )(yᵢ - ȳ) ] / [ ∑(xᵢ - x̄ )² ], β₀ = ȳ - β₁x̄ ] 

## • ( x̄ = (1/n) ∑xᵢ ): Mean of YearsExperience. 
## • ( ȳ = (1/n) ∑yᵢ ): Mean of Salary.


# Evaluation Metrics 
## 1. Mean Square Error (MSE): Average of squared differences between actual and predicted values.  
## Mathematically MSE is expressed as: 

## MSE = (1/n) ∑(yᵢ - ŷᵢ)² 

## It is a way to quantify the accuracy of a model's predictions. It is sensitive to outliers as large errors contribute significantly to the overall score.  

## 2. Mean Absolute Error (MAE): Average of absolute differences between actual and predicted values. It calculates the accuracy of a regression model. 
## Mathematically MAE is expressed as:

## MAE = (1/n) ∑|yᵢ - ŷᵢ| 

## Lower MAE value indicates better model performance. It is not sensitive to the outliers as we consider absolute differences. 

## 3. Root Mean Squared Error (RMSE): Square root of MSE, gives error in same unit as dependent variable. 
## Mathematically RMSE is expressed as: 

## RMSE = √[ (1/n) ∑(yᵢ - ŷᵢ)² ] 

## It describes how well the observed data points match the expected values or the model's absolute fit to the data. 

## 4. Coefficient of Determination (R-squared): Proportion of variance in the dependent variable explained by the model. It is always in the range of 0 to 1. In general, the better the model matches the data, the greater the R-squared number. 
## Mathematically R_Squared is expressed as: 

## R² = 1 - [ ∑(yᵢ - ŷᵢ)² / ∑(yᵢ - ȳ)² ] 


## Setup Instructions
### 1. Clone the repository:
```bash
git clone https://github.com/sameshbajracharya0337/Customer_Churn_Analysis_and_Prediction.git
cd LinearRegression
```

### 2. Create and activate a virtual environment (optional but recommended):
```bash
python -m venv venv
source venv\Scripts\activate
```

### 3. Download Dataset
```bash
Visit Kaggle.
Download Salary_Data.csv and place it in the project folder.
```
### 4. Install dependencies:
```bash
pip install -r requirements.txt
```
### 5. Run the Script



# Results
```bash
Linear Regression Results (sklearn):
Intercept (beta_0): 24848.20
Slope (beta_1): 9449.96
R-squared: 0.9570
Mean Squared Error (MSE): 31270951.72
Root Mean Squared Error (RMSE): 5592.04
Mean Absolute Error (MAE): 4644.20

Sample Data with Predictions (First 5 rows):
   Unnamed: 0  YearsExperience   Salary  Predicted_Salary
0           0              1.2  39344.0      36188.158752
1           1              1.4  46206.0      38078.151217
2           2              1.6  37732.0      39968.143681
3           3              2.1  43526.0      44693.124842
4           4              2.3  39892.0      46583.117306
```