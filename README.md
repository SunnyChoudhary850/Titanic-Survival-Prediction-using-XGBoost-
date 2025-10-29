![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Model-orange)
![Status](https://img.shields.io/badge/Status-Active-success)


# Titanic-Survival-Prediction-using-XGBoost-
This project uses Machine Learning to predict passenger survival on the Titanic dataset. The workflow includes data preprocessing, feature engineering, visualization, and model training using XGBoost, a powerful gradient boosting algorithm.


A machine learning project that predicts whether a passenger survived the Titanic disaster using **XGBoost**.  
This project involves **data cleaning**, **feature engineering**, **data visualization**, and **model training** to achieve accurate survival predictions.

---

## 📁 Project Overview

The **Titanic dataset** is one of the most popular datasets for beginners in data science and machine learning.  
The goal of this project is to predict survival based on passenger information such as age, sex, class, and fare.

---

## ⚙️ Tech Stack

- **Language:** Python  
- **Libraries Used:**
  - pandas  
  - numpy  
  - matplotlib  
  - scikit-learn  
  - xgboost  

---

## 📊 Dataset

- **Dataset File:** `train.csv`  
- **Source:** [Kaggle - Titanic: Machine Learning from Disaster](https://www.kaggle.com/c/titanic/data)

**Key Columns Used:**
- `PassengerId`  
- `Sex`  
- `Age`  
- `Fare`  
- `Ticket`  
- `Survived`

---

## 🧹 Data Preprocessing

1. **Removed unnecessary columns:**
   - `Name`
   - `Embarked`
   - `Cabin`

2. **Created a new feature:**
   - Extracted **ticket prefixes** from the `Ticket` column.

3. **Label Encoding:**
   - Converted `Sex` into numerical form using `LabelEncoder`.

4. **Reordered Columns:**
   - Moved `Survived` to the last column for better readability.

5. **Scaling:**
   - Applied `StandardScaler` to normalize numerical values.

---

## 🧠 Feature Engineering

Extracted **Ticket Prefix** using a custom function:

```python
def get_ticket_prefix(Ticket):
    parts = Ticket.split()
    if len(parts) > 1:
        return parts[0].replace('.', '')
    elif parts[0].isalpha():
        return parts[0]
    else:
        return 0
