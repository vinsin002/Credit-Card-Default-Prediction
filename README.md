Credit Card Default Prediction
This repository contains the analysis and machine learning models for predicting credit card default. The project leverages a real-world dataset to build and evaluate various classification models, with the goal of identifying high-risk customers and providing valuable insights for credit risk management.

Project Files
Notebook.ipynb: The main Jupyter Notebook detailing the entire project workflow, from data cleaning and exploratory data analysis (EDA) to model training and evaluation.

report.pdf: The full project report, summarizing the methodology, findings, and business implications.

train_dataset_final1.csv: The training dataset used for model development.

validate_dataset_final.csv: The validation dataset for model tuning and selection.

Prediction.csv: The final dataset used for generating default predictions.

Methodology
The project follows a standard machine learning pipeline:

1. Data Exploration & Cleaning
Initial data exploration was performed to understand the dataset's characteristics. Key preprocessing steps included:

Handling missing values in the age feature.

Merging invalid categories within the education feature.

Checking for and confirming the absence of duplicate rows.

2. Exploratory Data Analysis (EDA)
Comprehensive EDA was conducted to visualize the distribution of key features and their relationships with the target variable (next_month_default). The analysis provided a clear understanding of customer demographics, payment behavior, and the class imbalance issue.

3. Feature Engineering
Several new features were engineered to improve model performance and capture more complex behavioral patterns, including:

PAY_TO_BILL_RATIO: A ratio of total payments to total billed amounts, reflecting overall card usage behavior.

AVG_MONTHLY_PAYMENT: The mean of past six months' payments, indicating repayment capacity.

DELINQUENCY_PROBABILITY: A predicted probability of past delinquency from an auxiliary model, acting as an early warning signal.

TOTAL_DUES: The total outstanding balance, reflecting credit risk exposure.

4. Handling Class Imbalance
The dataset exhibited a significant class imbalance, with a large majority of non-defaulting customers. To address this, the SMOTE (Synthetic Minority Over-sampling Technique) algorithm was applied to the training data. This created a balanced dataset, improving the model's ability to correctly predict the minority (defaulting) class.

5. Model Training & Evaluation
A range of machine learning algorithms were trained and evaluated using GridSearchCV with 5-fold cross-validation. The primary evaluation metric was the F1 Score, which provides a balanced view of both precision and recall, crucial for credit default prediction.

Models Evaluated:

Random Forest

AdaBoost

Gradient Boosting

Logistic Regression

XGBoost

LightGBM

Results & Findings
After hyperparameter tuning, the Random Forest model emerged as the best performer based on the F1 Score. The model demonstrated strong performance in identifying potential defaulters.

Key Metrics (Random Forest - Test Set):

Accuracy: 0.81

F1 Score: 0.51

ROC AUC: 0.77

Feature Importance
A SHAP (SHapley Additive exPlanations) analysis was conducted to understand which features were most influential in the model's predictions. The analysis revealed that delinquency_probability, marriage, and sex were the top three features impacting the model's output.

Business Implications
The predictive model can be a powerful tool for financial institutions, enabling them to:

Proactively identify high-risk customers to mitigate potential credit losses.

Implement targeted interventions, such as tailored payment reminders or credit limit adjustments.

Enhance profitability by minimizing defaults while maintaining customer relationships.

Strengthen regulatory compliance through data-driven credit risk modeling.
