# 🕵️‍♀️ Fraud Detection in Job Postings

This project uses machine learning to detect fraudulent job postings from a dataset of 18,000 real-world job listings, including 800+ known fraudulent posts. It aims to help job seekers avoid scams by flagging suspicious listings based on patterns in the data.

---

## 📊 Dataset

- **Source**: [Fake Job Postings Dataset on Kaggle](https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction)
- **Records**: 17,880 job listings
- **Target Variable**: `fraudulent` (0 = Legitimate, 1 = Fraudulent)

---

## 🔍 Project Workflow

1. **Data Loading**
   - Loaded the dataset from a CSV file containing ~18,000 job postings.
   
2. **Data Cleaning & Imputation**
   - Handled missing values in key text fields like `title`, `description`, `company_profile`, etc.
   - Created a binary indicator for missing salary data.
   - Parsed and transformed salary ranges into numeric averages.
   - Imputed missing salary and experience values based on `required_experience`, `required_education`, and overall medians.
   - Filled categorical null values like `employment_type`, `function`, and `required_education` with mode.

3. **Feature Engineering**
   - Processed `required_experience` to extract numeric values.
   - Converted categorical columns and textual fields for use in model input.

4. **Vectorization**
   - Used `CountVectorizer` to transform textual features into numeric format suitable for machine learning models.

5. **Modeling**
   - Split the dataset into training and testing sets.
   - Trained a **Naive Bayes classifier** (BernoulliNB) to classify job posts as real or fraudulent.

6. **Evaluation**
   - Evaluated model performance using classification metrics like **precision**, **recall**, **F1-score**, and **accuracy**.
   - Generated a detailed classification report.

---

## 📁 Files in this Repo

- `fraud_detection.ipynb` – Full notebook with code and outputs
- `README.md` – You're reading it :)

---

## 🚀 How to Run

1. Clone the repo:

```bash
git clone https://github.com/srilekhatv/fraud-detection-ml.git
cd fraud-detection-ml
