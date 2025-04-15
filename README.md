# 📌 Complaint Resolution Timeframe Prediction Using Machine Learning

## 🔍 Overview
In service-driven industries, customer satisfaction is heavily influenced by how efficiently complaints are resolved. A common industry benchmark for resolving customer complaints is 30 days, which includes time for administrative tasks like documentation and evidence gathering.

This project applies machine learning techniques to predict whether a complaint will be resolved within 30 days using a dataset from the communications sector. Unlike traditional manual categorization, we use automation to ensure higher accuracy and proactive complaint management.

---

## 🎯 Objective
- Predict whether a customer complaint will be resolved within 30 days.
- Assist organizations in identifying at-risk complaints that may exceed resolution deadlines.

---
## 🔧 Data Processing

Before applying feature selection, the raw dataset underwent cleaning and transformation using **Tableau** and **Alteryx**. These tools enabled efficient data wrangling, including handling missing values, renaming columns, filtering records, and aggregating relevant attributes. This preprocessing ensured high-quality input for subsequent modeling and analysis steps.

---
## 🧠 Feature Selection

To improve model performance and reduce dimensionality, various feature selection techniques were applied. One key method used was **SelectKBest** with the **Chi-squared (χ²)** statistical test, which selects the features most correlated with the target variable.

Scikit-learn’s `SelectKBest` and `chi2` function were used in combination with the `feature_selection` module. These tools allow for flexible feature selection using different statistical metrics. Additionally, **Recursive Feature Elimination (RFE)** was used to rank and select features by recursively removing the least important ones and re-evaluating the model.

The three most important features selected using **SelectKBest with chi²** were:
- **Complaint Status**
- **Type of Complaint**
- **Sub Complaint**

Below is a summary of feature importance as identified by different selection methods:

### 📋 Table 4.3 – Feature Selection Results

| 🔢 Variable           | ✅ Feature Importance | 🧪 RFE | 🧮 SelectKBest (Chi²) |
|-----------------------|------------------------|-------|------------------------|
| Complaint Status      | ✅                     | ✅    | ✅                     |
| Industry              | ✅                     | ✅    |                        |
| Type of Complaint     | ✅                     | ✅    | ✅                     |
| Sub Complaint         | ✅                     | ✅    | ✅                     |
| Complaint Channel     | ✅                     | ✅    |                        |
| Area                  | ✅                     | ✅    |                        |

These selected features were then used in model training to improve both efficiency and accuracy by focusing on the most predictive variables.

## 🧠 Machine Learning Models Used
The following classification algorithms were tested:
- K-Nearest Neighbors (KNN)
- Naïve Bayes (GaussianNB, MultinomialNB, BernoulliNB)
- Support Vector Machine (SVM)
- Random Forest
- Logistic Regression
- Decision Trees
- Neural Networks

---

## 📊 Evaluation Metrics
Each model was evaluated using the following metrics:
- **Accuracy Score**
- **Precision**
- **Recall**
- **Confusion Matrix**

These metrics helped assess how effectively each model predicted whether a complaint would be resolved on time.

---

## ⭐ Top Performing Models
Based on the evaluations, the top models were:
- **K-Nearest Neighbors (KNN)**
- **Random Forest**
- **Decision Trees**

---

## 📂 Dataset
- Contains records of customer complaints in the communications sector.
- Includes attributes like complaint type, resolution time, and status.
- Sourced from a public domain (not named here for neutrality).
- Preprocessing and exploratory data analysis (EDA) were conducted before training.

---

## 📈 Model Performance Summary

### 🔢 Accuracy Score
| Model                | Accuracy |
|----------------------|----------|
| KNN, RF, DT, SVM     | 71%      |
| Naïve Bayes (all)    | 70%      |
| Logistic Regression  | 69.9%    |
| Neural Networks      | 68%      |

### 🎯 Precision
| Model                | Precision |
|----------------------|-----------|
| BernoulliNB          | 66%       |
| GaussianNB           | 62%       |
| MultinomialNB        | 61%       |
| KNN                  | 58%       |
| RF, DT               | 48%       |
| Neural Networks      | 40%       |
| SVM, LR              | 37%       |

### 🧪 Recall
| Model                | Recall |
|----------------------|--------|
| KNN, LR              | 56%, 53% |
| RF, DT               | 46%     |
| MultinomialNB        | 30%     |
| BernoulliNB          | 23%     |
| GaussianNB           | 13%     |

### ✅ Confusion Matrix Highlights
- **KNN**: Strong for predicting Class 0 (resolved < 15 days)
- **Naïve Bayes (GaussianNB, MultinomialNB)**: Good at predicting Class 2 (resolved > 30 days)
- **SVM & LR**: Showed confusion in class predictions
- **Random Forest & Decision Trees**: Accurately predicted delayed resolutions (Class 2)

---

## 🧾 Evaluation Summary Table

| Model               | Accuracy | Precision | Recall | Key Strength                                 | Rank (Top x/4) |
|---------------------|----------|-----------|--------|----------------------------------------------|----------------|
| KNN                 | 71%      | 58%       | 56%    | Correct for <15 days                         | 3/4            |
| GaussianNB          | 70%      | 62%       | 13%    | Good at predicting >30 days                  | 1/4            |
| MultinomialNB       | 70%      | 61%       | 30%    | Confused predictions                         | 0/4            |
| BernoulliNB         | 70%      | 66%       | 23%    | Mixed predictions                            | 1/4            |
| SVM                 | 71%      | 37%       | 37%    | Mixed predictions                            | 1/4            |
| Logistic Regression | 69.9%    | 37%       | 53%    | Confusion in class prediction                | 0/4            |
| Random Forest       | 71%      | 48%       | 46%    | Accurate on delayed complaints               | 2/4            |
| Decision Trees      | 71%      | 48%       | 46%    | Accurate on delayed complaints               | 2/4            |
| Neural Networks     | 68%      | 40%       | 38%    | High confusion across all classes            | 0/4            |

---

🤝 Contributions
We welcome contributions! Whether it's improving model performance, adding visualizations, or cleaning the data pipeline:

Fork the repo

Create a feature branch

Submit a pull request

### Note 
This project is a snip of a larger accademic project including data processing , description Analysis , features selection and many details . Feel free to contact for the whole project. 

## 📈 Business Impact

The feature selection and analysis performed in this project contribute directly to actionable insights for the business, with key benefits including:

### 🔍 Improved Focus on Critical Issues
By identifying the most influential features such as **Complaint Status**, **Type of Complaint**, and **Sub Complaint**, the organization can prioritize areas that are most closely associated with customer dissatisfaction. This enables more targeted interventions and faster resolution times.

### ⏱️ Operational Efficiency
Using **Tableau** and **Alteryx** for data processing significantly streamlined the data preparation pipeline. Automated workflows reduce the manual effort required for cleaning, transforming, and analyzing data — saving time and resources for the data team.

### 🧠 Smarter Decision-Making
With only the most relevant variables being used for modeling, predictive algorithms become faster and more interpretable. Decision-makers can trust and act on insights without being overwhelmed by noise or irrelevant data points.

### 💬 Enhanced Customer Service
By understanding which types of complaints are most likely to escalate or remain unresolved, customer service teams can proactively design escalation policies, tailor communication strategies, and allocate resources to high-risk cases more effectively.

### 💰 Cost Savings
Reducing unnecessary data dimensions not only optimizes model performance but also lowers the computational costs associated with storage and processing — especially when deployed at scale.

---

These improvements directly support better customer experience, lower churn rates, and improved brand reputation — delivering measurable business value.
📬 Contact
For any queries or collaborations, feel free to reach out via GitHub Issues.


