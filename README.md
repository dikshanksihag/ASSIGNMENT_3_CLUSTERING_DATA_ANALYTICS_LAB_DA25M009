
# ASSIGNMENT 4 CLUSTERING DATA ANALYTICS LAB_DA25M009
# GMM-Based Oversampling for Imbalanced Classification

## ⚠️ Important Note
- The repository URL may show a different number due to a minor typing error that was noticed later
- Please **ignore the URL discrepancy** — this repository is strictly and exclusively for **Assignment 4**. 

## 📌 Overview
This project investigates the effectiveness of **Gaussian Mixture Model (GMM)-based oversampling** compared to a baseline balanced model. The goal is to improve the detection of minority class samples in an imbalanced dataset by generating high-quality synthetic data.

Traditional oversampling methods such as **SMOTE** interpolate between existing minority class samples, which can lead to unrealistic points and overlapping distributions. GMM, on the other hand, models the **true underlying probability distribution** of the minority class, enabling more robust and representative synthetic data generation.

---

## ⚙️ Methodology
1. **Baseline Model (Balanced Sampling):**  
   - Trained with standard oversampling/balancing strategy.
   - Metrics recorded as reference.

2. **GMM+CBU Model:**  
   - Minority class distribution modeled using a **Gaussian Mixture Model**.  
   - Synthetic samples generated from high-density regions of the fitted distribution.  
   - Combined with **Class-Balanced Undersampling (CBU)** for majority class reduction.  

3. **Evaluation Metrics:**  
   - Precision, Recall, F1-score  
   - ROC-AUC (Receiver Operating Characteristic)  
   - PR-AUC (Precision-Recall curve)

---

## 📊 Results

### Performance Comparison

$$
\begin{array}{|l|l|l|}
\hline
\textbf{Metric} & \textbf{Baseline Balanced} & \textbf{GMM+CBU} \\ \hline
\text{Precision} & 0.7500 & 0.8182 \\ \hline
\text{Recall} & 0.5714 & 0.6429 \\ \hline
\text{F1-score} & 0.6486 & 0.7200 \\ \hline
\text{ROC-AUC} & 0.9123 & 0.9577 \\ \hline
\text{PR-AUC} & 0.6832 & 0.7458 \\ \hline
\end{array}
$$

---

## 🔎 Analysis

- **Recall improved** significantly (0.5714 → 0.6429), meaning the model became better at detecting true minority samples.  
- **Precision increased** (0.7500 → 0.8182), showing that oversampling with GMM did not introduce noisy or overlapping samples.  
- **F1-score improved**, confirming a better balance between sensitivity and specificity.  
- Both **ROC-AUC** and **PR-AUC** improved, showing stronger generalization and robustness across thresholds.  

---

## ✅ Final Recommendation

The findings demonstrate that **GMM-based oversampling outperforms simpler balancing strategies** in this context. It provides:

- **Theoretical soundness:** Ability to capture multi-modal and non-linear distributions of the minority class.  
- **Empirical gains:** Consistent improvements in recall, precision, F1-score, and AUC metrics.  
- **Robustness:** Generates synthetic points in high-density regions, avoiding unrealistic interpolations.

**Recommendation:**  
Adopt GMM-based synthetic data generation as the preferred oversampling method for imbalanced classification problems. It achieves a superior trade-off between detecting minority samples and maintaining overall model reliability. For further improvements, consider combining GMM with ensemble learning or cost-sensitive approaches.



