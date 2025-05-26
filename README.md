# 🚢 Titanic Dataset Preprocessing

A Python-based preprocessing pipeline for the [Titanic dataset](https://www.kaggle.com/c/titanic/data), designed to clean and prepare data for varoius useful purpose.

---

## 📋 task Overview

This task walks through:

- Handling missing values  
- Encoding categorical variables  
- Normalizing numerical features  
- Removing outliers  
- Saving the cleaned dataset for modeling  

The dataset used is `Titanic-Dataset.csv`, sourced from Kaggle or similar platforms.

---

## 🧾 Dataset Description

| Column        | Description                                                  |
|---------------|--------------------------------------------------------------|
| PassengerId   | Unique identifier for each passenger                         |
| Survived      | Survival status (0 = No, 1 = Yes)                             |
| Pclass        | Ticket class (1 = 1st, 2 = 2nd, 3 = 3rd)                      |
| Name          | Full name                                                    |
| Sex           | Gender (male/female)                                         |
| Age           | Age in years                                                 |
| SibSp         | Number of siblings/spouses aboard                            |
| Parch         | Number of parents/children aboard                            |
| Ticket        | Ticket number                                                |
| Fare          | Passenger fare                                               |
| Cabin         | Cabin number                                                 |
| Embarked      | Port of Embarkation (C = Cherbourg, Q = Queenstown, S = Southampton) |

---

## ✅ Prerequisites

Ensure you have Python 3.6+ and install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn


Preprocessing Steps
1. Load and Explore the Dataset
Load the CSV file using pandas

Display dataset info, first 5 rows, and null value counts

2. Handle Missing Values
Impute missing Age values using median

Impute missing Embarked values using mode

Drop the Cabin column (too many missing values, typically >70%)

3. Encode Categorical Features
Convert Sex to numeric (male = 0, female = 1)

Apply one-hot encoding to Embarked (Embarked_Q, Embarked_S), dropping the first category

Drop non-numeric and irrelevant features: PassengerId, Name, Ticket

4. Normalize Numerical Features
Use MinMaxScaler from scikit-learn to scale:

Age

Fare

SibSp

Parch

5. Visualize and Remove Outliers
Generate boxplots for Age and Fare using matplotlib/seaborn

Apply the IQR method to remove outliers:

Remove rows where values are outside Q1 - 1.5*IQR or Q3 + 1.5*IQR

6. Save the Cleaned Dataset
Save the preprocessed dataset as titanic_cleaned.csv if it doesn't already exist
====================================================
📊 Expected Output
✅ Console Output
Dataset info (data types, non-null counts)

First 5 rows before and after processing

Null value counts (before and after handling)

Dataset shape after outlier removal

Summary statistics of the final dataset
==============================================
📁 File Output
A file named titanic_cleaned.csv containing the preprocessed data with the following columns:

text
Copy
Edit
Survived
Pclass
Sex
Age
SibSp
Parch
Fare
Embarked_Q
Embarked_S
