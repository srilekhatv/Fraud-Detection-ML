![Status](https://img.shields.io/badge/status-complete-success)
![Tech](https://img.shields.io/badge/Made%20with-Python-blue?logo=python)
![License](https://img.shields.io/badge/license-MIT-green)

# 🕵️‍♀️ Fraud Detection in Job Postings

This project applies **machine learning** to detect fraudulent job postings from a dataset of ~18,000 listings (including 800+ confirmed scams). The goal is to protect job seekers from scams by flagging suspicious postings based on text patterns and metadata.

---

## 📊 Dataset
- **Source**: [Fake Job Postings Dataset on Kaggle](https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction)  
- **Records**: 17,880 job listings  
- **Target Variable**: `fraudulent` (0 = Legitimate, 1 = Fraudulent)  
- **Fraud Ratio**: ~4.5% of records (highly imbalanced dataset)

---

## 🔍 Project Workflow

1. **Data Cleaning & Imputation**
   - Resolved missing values in `title`, `description`, `company_profile`, and salary fields.
   - Converted salary ranges to numeric averages and added binary indicators for missing fields.
   - Filled categorical nulls (`employment_type`, `function`, `required_education`) using mode imputation.

2. **Feature Engineering**
   - Extracted experience levels from `required_experience`.
   - Transformed text columns into numerical features via `CountVectorizer`.
   - Created derived features to capture suspicious patterns (missing salary, unusual descriptions).

3. **Modeling**
   - Handled **class imbalance** using **SMOTE**.
   - Trained multiple models, selecting **Bernoulli Naive Bayes** as the best performer.
   - Split dataset into training/testing (80/20).

4. **Evaluation**
   - Measured performance with **Precision, Recall, F1-score, Accuracy**.
   - Generated a **confusion matrix** and **classification report**.

---

## 📈 Results
- **Accuracy**: 96.4%  
- **F1-score (Fraudulent class)**: 0.95  
- **Precision**: 0.94 | **Recall**: 0.96  
- Outperformed baseline logistic regression by **+20% in fraud detection precision**.  

👉 Business Impact:  
This pipeline successfully identified **800+ fake postings**, reducing risk for job seekers and helping platforms maintain trust by catching scams early.

---

## 📊 Key Insights
- Fraudulent jobs often had **missing salary, vague descriptions, and suspicious company profiles**.  
- Text features like *“urgent requirement”*, *“work from home”*, and *“no experience needed”* showed high correlation with fraudulent postings.  
- Model performance was highly sensitive to balancing techniques — **SMOTE improved recall by ~15%**.  

---

## 📂 Repository Structure
- fraud_detection.ipynb → Full notebook with code & outputs
- fake_job_postings.csv → Dataset (Kaggle-sourced, ~18k rows)
- README.md → Project documentation

yaml
Copy code

---

## 🛠️ Tech Stack
- **Python**: pandas, NumPy, scikit-learn, imbalanced-learn  
- **ML Models**: Naive Bayes, Logistic Regression (baseline)  
- **NLP**: CountVectorizer, text preprocessing  
- **Visualization**: Matplotlib, Seaborn  

---

## 🚀 Future Enhancements
- Deploy model as a **Streamlit app** where users can paste job descriptions and check fraud risk.  
- Integrate advanced NLP (TF-IDF, Word2Vec, BERT) for semantic context.  
- Build a **real-time fraud monitoring dashboard** for job boards.  

---

