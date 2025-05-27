
---
# 🎓 StudentSynapse : Understanding Student Behavior Through Data Science

This project explores student behavior using anonymized educational data collected from a survey conducted at IIT Guwahati. The goal is to uncover hidden patterns in academic performance, stress levels, and personal relationships by applying data cleaning, visualization, and machine learning techniques.

The work was completed as part of a multi-level project under the guidance of the **Student Wellness and Experience Board**, with the final objective of predicting whether a student is likely to be in a romantic relationship based on lifestyle and academic features.

---

## 🧭 Project Structure

This project follows a structured, level-based approach:

1. **Feature Interpretation**: Understand what the anonymized features represent.
2. **Data Integrity Audit**: Handle missing values and clean the dataset.
3. **Exploratory Data Analysis (EDA)**: Visualize trends and relationships between variables.
4. **Predictive Modeling**: Build and evaluate a machine learning model to predict romantic relationships.

Each level builds upon the previous one, forming a complete pipeline from raw data to prediction.

---

## 📌 Key Objectives

- Interpret the meaning of anonymized features (`Feature_1`, `Feature_2`, `Feature_3`)
- Clean the dataset by handling missing values
- Perform exploratory analysis to uncover meaningful trends
- Build a predictive model to estimate the likelihood of a student being in a romantic relationship
- Evaluate model performance using accuracy, F1-score, and ROC-AUC

---

## 📊 Dataset Overview

The dataset contains 649 student records with 33 features covering:

| Category         | Examples |
|------------------|----------|
| **Demographics** | school, sex, age, address, family size |
| **Academic Info** | grades (G1, G2, G3), failures, absences |
| **Behavioral**   | alcohol consumption, free time, going out |
| **Social**       | guardian, reason for choosing school |
| **Psychological** | Stress_Level, Year_of_Study |

---

## 🔍 Feature Interpretation

Three key features were initially labeled as `Feature_1`, `Feature_2`, and `Feature_3`. Based on distribution, correlation, and contextual clues, these were interpreted and renamed:

| Original Name     | Interpreted Meaning | Justification |
|-------------------|---------------------|---------------|
| `Feature_1`       | `Age`              | Values between 15–22, moderate positive correlation with grades |
| `Feature_2`       | `Year_of_Study`    | Integer values (1–4), weak negative correlation with grades |
| `Feature_3`       | `Stress_Level`     | Scale of 1–5, strong positive correlation with Dalc (daily alcohol use) |

These interpretations helped make the dataset more understandable and usable for further analysis.

---

## 🧹 Data Cleaning

Several columns had missing values:
```
higher        76
Fedu          73
traveltime    73
absences      69
famsize       50
Feature_2     46
freetime      45
Feature_3     39
Feature_1     38
G2            35
```

Missing values were handled using appropriate strategies:

- **Categorical Features**: Mode imputation
- **Numerical Features**: Median imputation

All missing values were successfully addressed without deleting any rows or columns.

After cleaning, the dataset was fully ready for modeling and analysis.

---

## 📈 Exploratory Data Analysis (EDA)

We explored five core questions through visualizations:

### 1. **How does stress level vary with age?**
- **Visualization**: Scatterplot with regression line
- **Insight**: Slight upward trend — older students report higher stress levels

### 2. **Is there a relationship between free time and final grades (`G3`)?**
- **Visualization**: Scatterplot with regression line
- **Insight**: Weak negative correlation — more free time may lead to lower grades

### 3. **How do absences affect final grades?**
- **Visualization**: Box plot of `G3` grouped by absence bins
- **Insight**: Students with >15 absences consistently have lower grades

### 4. **Does family size influence academic performance?**
- **Visualization**: Bar chart comparing average `G3` for LE3 vs GT3
- **Insight**: Slightly higher grades in smaller families

### 5. **How do different guardians affect stress levels?**
- **Visualization**: Violin plot
- **Insight**: Parental guardianship correlates with lower stress levels

---

## 🌲 Predictive Modeling

We built a **Random Forest Classifier** to predict whether a student is likely to be in a romantic relationship (`romantic = yes/no`) using features like `Age`, `Stress_Level`, `Year_of_Study`, and others.

### Why Random Forest?

- Handles mixed data types effectively
- Resists overfitting
- Provides feature importance
- No need for scaling

### Evaluation Metrics

| Metric           | Score     |
|------------------|-----------|
| Accuracy         | ~62%      |
| F1-Score         | ~62%      |
| ROC-AUC Score    | ~65%      |

These metrics indicate **moderate performance**, showing that meaningful patterns exist in the data.

A classification report and confusion matrix were used to interpret results in detail, revealing that the model performs slightly better at predicting students **not in** a romantic relationship than those who are.

---

## 🛠️ Tools & Libraries Used

- **Python Libraries**: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
- **Algorithms**: Random Forest Classifier
- **Techniques**: Label Encoding, Imputation, Standardization, EDA

---


## 📈 Future Work (Optional)

- Improve model accuracy using hyperparameter tuning
- Apply synthetic oversampling (e.g., SMOTE) to balance classes
- Deploy findings in a dashboard or API for board use

---


## 📬 Contact

If you're interested in this work or would like help extending it, feel free to reach out!

---

