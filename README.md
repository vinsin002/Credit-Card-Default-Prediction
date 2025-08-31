# Credit Card Default Prediction

This repository contains the analysis and machine learning models for predicting credit card default. The project leverages a real-world dataset to build and evaluate various classification models, with the goal of identifying high-risk customers and providing valuable insights for credit risk management.

---

## Project Files
- **Notebook.ipynb**: The main Jupyter Notebook detailing the entire project workflow, from data cleaning and exploratory data analysis (EDA) to model training and evaluation.
- **report.pdf**: The full project report, summarizing the methodology, findings, and business implications.
- **train_dataset_final1.csv**: The training dataset used for model development.
- **validate_dataset_final.csv**: The validation dataset for model tuning and selection.
- **Prediction.csv**: The final dataset used for generating default predictions.

---

## Methodology

The project follows a standard machine learning pipeline:

### 1. Data Exploration & Cleaning
- Performed initial data exploration to understand dataset characteristics.  
- Handled missing values in the `age` feature.  
- Merged invalid categories within the `education` feature.  
- Checked and confirmed the absence of duplicate rows.  

### 2. Exploratory Data Analysis (EDA)
- Conducted visualizations of feature distributions and their relationship with the target variable (`next_month_default`).  
- Analyzed customer demographics and payment behavior.  
- Identified class imbalance in the dataset.  

### 3. Feature Engineering
Engineered new features to enhance model performance:
- **PAY_TO_BILL_RATIO**: Ratio of total payments to total billed amounts, reflecting card usage behavior.  
- **AVG_MONTHLY_PAYMENT**: Mean of past six months’ payments, indicating repayment capacity.  
- **DELINQUENCY_PROBABILITY**: Predicted probability of past delinquency from an auxiliary model.  
- **TOTAL_DUES**: Total outstanding balance, representing credit risk exposure.  

### 4. Handling Class Imbalance
- Applied **SMOTE (Synthetic Minority Over-sampling Technique)** to balance the dataset.  
- Improved the model’s ability to correctly predict the minority (defaulting) class.  

### 5. Model Training & Evaluation
- Models were trained and tuned using **GridSearchCV** with 5-fold cross-validation.  
- **Primary Metric**: F1 Score (balances precision and recall).  

Models evaluated:
- Random Forest  
- AdaBoost  
- Gradient Boosting  
- Logistic Regression  
- XGBoost  
- LightGBM  

---

## Results & Findings

- After hyperparameter tuning, **Random Forest** achieved the best results.  

**Key Metrics (Random Forest – Test Set):**
- Accuracy: **0.81**  
- F1 Score: **0.51**  
- ROC AUC: **0.77**  

---

## Feature Importance

- SHAP (SHapley Additive exPlanations) was used to interpret feature importance.  
- Top influential features:  
  1. `delinquency_probability`  
  2. `marriage`  
  3. `sex`  

---

## Business Implications

The predictive model enables financial institutions to:
- Identify high-risk customers proactively to reduce credit losses.  
- Implement targeted interventions such as tailored payment reminders or credit limit adjustments.  
- Enhance profitability by minimizing defaults while maintaining strong customer relationships.  
- Strengthen regulatory compliance with data-driven credit risk modeling.  

