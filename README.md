# 🏦 Credit Risk Analysis & Loan Default Prediction

This project predicts whether a loan applicant will **default (1)** or **not default (0)** based on their financial, demographic, and loan-related features.  
The goal is to help banks and financial institutions reduce risk by identifying high-risk loan applicants before approval.

---

## 📊 Dataset
- **Source:** [Credit Risk Dataset on Kaggle](https://www.kaggle.com/datasets/laotse/credit-risk-dataset)  
- **Rows:** ~32,000+  
- **Columns:** 12  
- **Target Variable:** `loan_status`  
  - `1` → Default  
  - `0` → Non-default  

**Main Features Used:**
- `person_age`, `person_income`, `person_emp_length`  
- `person_home_ownership`, `loan_intent`, `loan_grade`  
- `loan_amnt`, `loan_int_rate`, `loan_percent_income`  
- `cb_person_default_on_file`  

---

## 🚀 Workflow

### 1. Data Cleaning
- Handled missing values in `person_emp_length` and `loan_int_rate` using median imputation.  
- Removed outliers from `person_age` and `person_income` using IQR/Z-score method.  

### 2. Feature Engineering
- One-Hot Encoding for categorical variables (`home_ownership`, `loan_intent`, `loan_grade`).  
- Label Encoding for binary variables (`cb_person_default_on_file`).  
- Created `loan_to_income_ratio` as a new feature.  

### 3. Data Balancing
- The dataset was **imbalanced** (more non-defaults than defaults).  
- Applied **SMOTE (Synthetic Minority Oversampling Technique)** to balance classes.  

### 4. Scaling
- Applied **StandardScaler** to numerical features (`age`, `income`, `loan_amnt`, `loan_int_rate`).  

### 5. Modeling
Trained and compared multiple models:  
- **Logistic Regression**  
- **Random Forest Classifier**  
- **XGBoost Classifier** (Best performing)  

### 6. Evaluation Metrics
Since **false negatives** (predicting safe loan when it actually defaults) are very costly in finance, more focus was given to **Recall and F1-score**.  

---

## ✅ Results
- Logistic Regression → F1 Score: 0.72  
- Random Forest → F1 Score: 0.81  
- **XGBoost → F1 Score: 0.85 (Best)**  

📈 XGBoost provided the most reliable results with high recall for detecting loan defaults.  

---

## 🛠 Installation & Usage

### Clone this repo
```bash
git clone https://github.com/<your-username>/credit-risk-analysis.git
cd credit-risk-analysis
📌 Tech Stack

Python 3.x

pandas, numpy

scikit-learn

imbalanced-learn (SMOTE)

XGBoost

matplotlib, seaborn

📖 Future Improvements

Deploy model as an API (Flask/FastAPI)

Integrate with a web dashboard (Streamlit) for real-time predictions

Experiment with Deep Learning (Neural Networks) for comparison

---

✅ Ye README **professional + recruiter-friendly** hai:  
- Project ka purpose clear hai  
- Dataset details diye hain  
- Tumhari preprocessing aur ML pipeline explain hai  
- Results highlight kiye hain  
- Future improvements mention hain (companies ko ye pasand aata hai)  

---

👉 Arman, kya chaho ke main tumhare liye **requirements.txt file** bhi bana dun (jo tumhare repo me add ho jaye automatically)?
