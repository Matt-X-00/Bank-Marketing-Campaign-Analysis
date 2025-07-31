# Bank-Marketing-Campaign-Analysis
This project analyzes a bank marketing dataset to predict whether clients will subscribe to a term deposit ("deposit") based on various demographic, financial, and campaign-related features. The analysis includes exploratory data analysis, feature engineering, and machine learning model implementation.
Dataset Information
Source:Kaggle  (Bank marketing campaign data) 






Size: 11,162 records with 17 features

Target Variable: 'deposit' (binary: 'yes'/'no')

Data Types: Numerical: age, balance, day, duration, campaign, pdays, previous

Categorical: job, marital, education, default, housing, loan, contact, month, poutcome



Key Findings from EDA
Target Variable Distribution
No: 52.62%

Yes: 47.38%

Significant Predictors
Demographic Factors:

Job: Students (74.7% yes) and retired (66.3% yes) most likely to subscribe

Marital Status: Singles (54.3% yes) more likely than married (43.4% yes)

Education: Tertiary educated (54.1% yes) more likely than primary (39.4% yes)

Financial Factors:

Higher balance correlates with higher subscription rates

Clients with no housing loan (56.6% yes) more likely than those with loans (36.4% yes)

Campaign Factors:

Longer call duration strongly correlates with subscription

Cellular contact (54.3% yes) outperforms telephone (50.4% yes)

Fewer campaign contacts generally better for subscription



Data Preprocessing
Encoding:

Categorical variables encoded using LabelEncoder

Target variable mapped to binary (yes=1, no=0)

Feature Selection:

All features showed statistical significance (p<0.05) in chi-square/t-tests

Correlation analysis showed no strong multicollinearity



Machine Learning Models
Models Implemented:
Logistic Regression

Accuracy: 75%

Precision/Recall balanced at ~0.75 for both classes

Decision Tree (max_depth=5)

Accuracy: 80%

Improved balance between precision and recall

Random Forest (100 estimators)

Best performance with 84% accuracy

AUC: 0.92 (excellent discrimination)

Balanced precision/recall at ~0.84 for both classes

Evaluation Metrics:
text
Random Forest Results:
[[1415  327]
 [ 209 1398]]

              precision  recall  f1-score  support

           0       0.87     0.81      0.84      1742
           1       0.81     0.87      0.84      1607

    accuracy                           0.84      3349







How to Use This Project
Requirements:

Python 3.x

pandas, numpy

scikit-learn

matplotlib, seaborn

scipy (for statistical tests)

Implementation:

Clone repository

Install requirements: pip install -r requirements.txt

Run Jupyter notebook

Customization:

Adjust model parameters in the respective cells

Add new visualization as needed

Experiment with additional feature engineering

Future Improvements
Feature Engineering:

Create interaction terms between important features

Bin continuous variables where appropriate

Model Enhancement:

Hyperparameter tuning for better performance

Experiment with gradient boosting methods (XGBoost, LightGBM)

Deployment:

Create API endpoint for predictions

Build interactive dashboard for business users

License
This project is open-source and available for educational and research purposes. Commercial use requires permission.
