# ASSIGNMENT 3 CLUSTERING DATA ANALYTICS LAB_DA25M009


# Fraud Detection with Imbalanced Data

This assignment explores the problem of **imbalanced classification** in fraud detection.  
I use **Logistic Regression** as the baseline model and experiment with different **resampling techniques** and **hyperparameter optimization** methods to improve performance on the minority (fraud) class.

---

## 📌 Project Workflow

### 1. Data Preprocessing
- Loaded and cleaned the dataset.
- Identified the class imbalance problem (majority: non-fraud, minority: fraud).
- Split the data into **training** and **test** sets.

### 2. Resampling Techniques
We applied multiple methods to handle the class imbalance:
- **Undersampling** – reduces the majority class.
- **Oversampling** – duplicates minority class samples.
- **SMOTE** – creates synthetic minority samples.

### 3. Model Training
- Used **Logistic Regression** as the classifier.
- Trained on the **original imbalanced data** and each resampled dataset.

### 4. Model Evaluation
- Evaluated models on the **original test set** to measure generalization.
- Metrics: **Accuracy, Precision, Recall, and F1-score** (focused on the minority/fraud class).

### 5. Extra: Randomized Search
- Applied **RandomizedSearchCV** to tune hyperparameters:
  - Regularization strength `C`
  - Penalty type (`l1`, `l2`)
  - Solver (`liblinear`, `saga`)
  - Maximum iterations

---

## 📊 Performance Comparison
$$
\begin{array}{|c|c|c|c|c|}
\hline
\textbf{Method} & \textbf{Accuracy} & \textbf{Precision (Fraud)} & \textbf{Recall (Fraud)} & \textbf{F1-Score (Fraud)} \\
\hline
\text{Baseline} & 0.99 & 0.83 & 0.60 & 0.7 \\
\hline
\text{Smote} & 0.99 & 0.87 & 0.74 & 0.80 \\
\hline
\text{CBO} & 0.99 & 0.78 & 0.78 & 0.78 \\
\hline
\text{CBU} & 0.99 & 0.64 & 0.78 & 0.70 \\
\hline
\end{array}
$$

> ⚠️ Replace the above placeholder values with your actual model results.

---

## 🔑 Key Insights
- Resampling significantly improved recall for the minority class.
- SMOTE provided the best **balance between precision and recall**.
- Randomized Search improved performance by fine-tuning hyperparameters.
- Undersampling worked but lost too much information.

