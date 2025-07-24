# 🏦 Amex Offer Optimizer - Hackathon Project

This repository contains my solution for the **Amex Decision Track Hackathon**, where the goal was to build a model that recommends the most relevant credit card offers to users, maximizing engagement and conversion rates.

---

## 🚀 Problem Statement

American Express provides numerous card-linked offers to its customers. The task was to optimize which offers to recommend to each customer, using historical data of:

- Customer profiles
- Transactions
- Offer details
- Offer interaction events (like views, redemptions, etc.)

The goal was to **rank offers for each user** in a way that maximizes a MAP@12 (Mean Average Precision at 12) score.

---

## 🧠 Approach

1. **Data Preprocessing**
   - Merged and cleaned multiple datasets (`train`, `offer`, `event`, `transaction`)
   - Handled missing values using median imputation
   - Optimized memory usage by converting data types (e.g., `int64` → `int32`, `float64` → `float32`)

2. **Feature Engineering**
   - Generated user-level and offer-level features
   - Created aggregate transaction features (e.g., total spend, avg amount)
   - Used date-based features (e.g., time between offer and redemption)

3. **Modeling**
   - Used **LightGBM's LambdaRank** objective for learning to rank
   - Grouped data by user ID to structure it as a ranking problem
   - Optimized hyperparameters using **Optuna**
   - Evaluated using custom MAP@12 metric

4. **Post-Processing**
   - Filtered top-12 offers per user for final submission

---

## 📁 Datasets

All the datasets used in this project are available in the shared Google Drive folder below:

📂 **[Access the data here](https://drive.google.com/drive/folders/1eOc7wzb6GdkhjTdrntxtRS8LzItS4Uax)**  
*(Includes: df_train.csv, df_offer.csv, df_transaction.csv, df_event.csv, etc.)*

> ⚠️ Please make a copy of the Drive folder if you want to work on it.

---

## 🛠️ Technologies Used

- Python 3.10
- Pandas, NumPy
- LightGBM (LambdaRank)
- Optuna for hyperparameter tuning
- scikit-learn for preprocessing and evaluation
- Jupyter Notebooks for experimentation

---

## 📊 Evaluation Metric

We used **Mean Average Precision at 12 (MAP@12)**, which reflects how well the model ranks offers for each user.

---

## 🧾 Results

- Achieved a MAP@12 score of **0.440+** after tuning and feature engineering
- Improved performance by:
  - Filling missing values
  - Optimizing groupings
  - Reducing memory usage for faster experimentation

---

## 🤝 Acknowledgments

Thanks to American Express and the organizers of the hackathon for this opportunity.  
Special thanks to the open-source community for tools like LightGBM and Optuna.

---

## 📬 Contact

Feel free to reach out for collaboration or questions!

**Prateek Gupta**  
Email: [pg7729600@gmail.com]  
GitHub: [@prateek-g-bit](https://github.com/prateek-g-bit)

