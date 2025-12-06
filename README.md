# 🛳️ Titanic Survival Prediction — Exploratory Data Analysis (EDA) Ankit Yadav 

This project performs **in-depth Exploratory Data Analysis (EDA)** on the famous **Titanic dataset**, aiming to uncover patterns, relationships, and key factors that influenced passenger survival during the tragic sinking of the RMS Titanic in 1912.

The focus of this repository is **only EDA**, not model building.

---
## dataset Link: https://www.kaggle.com/datasets/yasserh/titanic-dataset
## 📌 Project Objective

* Understand the structure and nuances of the Titanic dataset.
* Analyze how demographic, socio-economic, and travel-related factors influenced survival.
* Visualize key patterns using statistical graphics.
* Prepare insights that could help in future feature engineering for predictive modeling.

---

## 📂 Dataset Description

The dataset used is the classic **Kaggle Titanic dataset** containing information such as:

| Feature       | Description                                                          |
| ------------- | -------------------------------------------------------------------- |
| `PassengerId` | Unique ID for each passenger                                         |
| `Survived`    | Survival flag (0 = No, 1 = Yes)                                      |
| `Pclass`      | Travel class (1 = Upper, 2 = Middle, 3 = Lower)                      |
| `Name`        | Passenger name                                                       |
| `Sex`         | Gender                                                               |
| `Age`         | Passenger age                                                        |
| `SibSp`       | Number of siblings/spouses aboard                                    |
| `Parch`       | Number of parents/children aboard                                    |
| `Ticket`      | Ticket number                                                        |
| `Fare`        | Fare paid                                                            |
| `Cabin`       | Cabin number                                                         |
| `Embarked`    | Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton) |

---

## 🧹 Data Preprocessing

Before analysis, the following steps were performed:

### ✔ Handling Missing Values

* `Age`: Imputed using median values grouped by `Sex` & `Pclass`.
* `Cabin`: Majority missing → treated as "Cabin available vs not available".
* `Embarked`: Filled with mode.
* `Fare`: Filled with median for group where missing occurred.

### ✔ Feature Transformations

* Extracted **Title** from `Name` (Mr, Miss, Mrs, Master, etc.).
* Created **FamilySize** = SibSp + Parch + 1.
* Created **IsAlone** flag.
* Converted categorical variables to categories for easier analysis.

---

## 📊 Detailed EDA Summary

### 1. **Univariate Analysis**

#### 🎯 Target Variable — Survival

* Survival rate ~38% overall.
* Highly imbalanced but still informative for analysis.

#### 👨‍👩‍👧 Gender Distribution

* ~65% male, ~35% female.
* Clear imbalance in gender populations.

#### 🎟 Pclass Distribution

* Majority passengers belonged to **3rd class**.

#### 🧒 Age Distribution

* Right-skewed distribution.
* Several infants and children but majority adults in 20–40 age group.

---

### 2. **Bivariate Analysis**

#### 🚹 Gender vs Survival

* **Females survived ~74%**
* **Males survived ~19%**
  Gender is one of the strongest predictors.

#### 🎟 Pclass vs Survival

* 1st Class: ~63% survived
* 2nd Class: ~47% survived
* 3rd Class: ~24% survived
  Clear socio-economic advantage for survival.

#### 🧒 Age vs Survival

* Children (<15) had higher survival likelihood.
* Older passengers had lower chances.

---

### 3. **Multivariate Insights**

#### ⭐ Combined Effect of Gender + Class

* **Female + 1st Class** → highest survival (~96%)
* **Male + 3rd Class** → lowest survival (~14%)

#### ⭐ Family Size Patterns

* Small families (2–4 members) survived more.
* Very large families (7+) had extremely low survival.
* Alone passengers ("IsAlone = 1") had lower survival odds.

#### ⭐ Fare Influence

* Higher fare → higher survival probability.
* Strong correlation between Fare and Pclass.

#### ⭐ Embarked Port Trends

* Passengers from **Cherbourg (C)** had the highest survival rate.
* Possibly due to more 1st-class travelers boarding there.

---

## 📈 Visualizations Included

The analysis contains visualizations such as:

* Distribution plots (Age, Fare, Family Size)
* Survival heatmaps
* Sex vs Survival bar charts
* Pclass vs Survival stacked bars
* Age distributions by survival groups
* Fare boxplots grouped by class and survival
* Correlation matrix (numeric features)

All charts generated using:

* **Matplotlib**
* **Seaborn**
* **Pandas**

---

## 🔍 Key Insights

* **Gender** and **Pclass** are the most influential factors.
* Children benefited from "women and children first" evacuation protocol.
* Family presence improved survival (to a limit).
* High fare-paying passengers had more access to lifeboats.
* Embarkation location indirectly relates to socio-economic status.

---

## 🗂 Project Structure

```
📁 Titanic-EDA/
│
├── notebooks/
│   └── Titanic_EDA.ipynb
│
├── data/
│   └── train.csv
│
├── images/
│   └── charts-and-visuals.png
│
└── README.md
```

---

## 🛠️ Tech Stack

* Python
* Pandas
* NumPy
* Seaborn
* Matplotlib
* Jupyter Notebook

---

## 🚀 How to Run the Project

```bash
# Clone the repo
git clone https://github.com/your-username/titanic-eda.git

# Move to folder
cd titanic-eda

# Install dependencies
pip install -r requirements.txt

# Run Jupyter Notebook
jupyter notebook
```

---

## 📌 Future Work

* Feature engineering for model building
* Applying ML models (Logistic Regression, Random Forest, XGBoost)
* Hyperparameter tuning
* Building a full prediction pipeline

---

## 🤝 Contribution

Pull requests are welcome! For major changes, open an issue first to discuss your ideas.

---

## ⭐ Acknowledgements

Dataset sourced from **Kaggle Titanic: Machine Learning from Disaster**.


