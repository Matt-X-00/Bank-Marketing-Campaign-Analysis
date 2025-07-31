# Bank Marketing Campaign Analysis

![Bank Marketing](https://img.shields.io/badge/domain-banking%20marketing-blue)
![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)

## 📌 Project Overview

This project analyzes bank marketing data to predict client subscription to term deposits using machine learning. The analysis includes comprehensive EDA, feature engineering, and evaluation of multiple classification models.

## 📊 Dataset Information

| Feature          | Description                          | Type       |
|------------------|--------------------------------------|------------|
| **age**          | Client's age                         | Numerical  |
| **job**          | Client's occupation                  | Categorical|
| **marital**      | Marital status                       | Categorical|
| **education**    | Education level                      | Categorical|
| **balance**      | Account balance                      | Numerical  |
| **duration**     | Last contact duration (seconds)      | Numerical  |
| **deposit**      | Target: subscribed to term deposit?  | Binary     |

**Dataset Statistics**:
- Records: 11,162
- Features: 17
- Class Distribution:
  - No: 52.62%
  - Yes: 47.38%

## 🔍 Key Insights

### Demographic Factors
| Category        | Subscription Rate |
|----------------|-------------------|
| **Students**    | 74.7%             |
| **Retired**     | 66.3%             |
| **Tertiary Ed** | 54.1%             |
| **Single**      | 54.3%             |

### Campaign Factors
![Duration vs Subscription](duration_boxplot.png)

- Calls > 5 minutes have 3× higher conversion
- Cellular contact outperforms telephone (54.3% vs 50.4%)

## 🛠️ Technical Implementation

### Data Pipeline
```python
# Preprocessing
encoder = LabelEncoder()
for col in categorical_features:
    data[col] = encoder.fit_transform(data[col])
    
# Train-Test Split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.3, random_state=42)


Model Performance

Model	                  Accuracy	 Precision	Recall	 AUC
Logistic Regression	      75%      	0.75	     0.75	   0.81
Decision Tree           	80%	      0.80	     0.80	   0.87
Random Forest	            84%	      0.84	     0.84	   0.92
