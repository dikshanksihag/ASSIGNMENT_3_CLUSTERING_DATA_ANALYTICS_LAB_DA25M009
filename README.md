
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

#### Performance Metric
$$
\begin{array}{|l|l|l|l|}
\hline
\textbf{Metric} & \textbf{Baseline} & \textbf{GMM} & \textbf{GMM+CBU} \\ \hline
\text{Precision} & 0.8211 & 0.7521 & 0.8349 \\ 
\hline
\text{Recall}    & 0.6047 & 0.7054 & 0.7054 \\ 
\hline
\text{F1-score}  & 0.6964 & 0.7280 & 0.7647 \\ 
\hline
\text{ROC-AUC}   & 0.9495 & 0.9556 & 0.9619 \\ 
\hline
\text{PR-AUC}    & 0.6669 & 0.6697 & 0.6735 \\ 
\hline
\end{array}
$$

#### Precision-Recall Curve

<img width="1038" height="481" alt="{448C0736-139B-4391-ACD3-BFA53924B7F2}" src="https://github.com/user-attachments/assets/2f9d3928-7916-453c-ac6d-a0aa13eab598" />


---

## 🔎 Analysis

- **Recall improved** (0.6047 → 0.7054) with both GMM and GMM+CBU, showing better sensitivity to minority samples.  
- **Precision shifted**: it dropped with plain GMM (0.8211 → 0.7521) but was restored and even improved with GMM+CBU (0.8349), meaning CBU helped control noise and sharpen decision boundaries.  
- **F1-score steadily improved** (0.6964 → 0.7280 → 0.7647), confirming a progressively better trade-off between precision and recall.  
- Both **ROC-AUC** (0.9495 → 0.9556 → 0.9619) and **PR-AUC** (0.6669 → 0.6697 → 0.6735) consistently improved, demonstrating stronger robustness and class separability across thresholds.  

---

## ✅ Final Recommendation

The findings demonstrate that **GMM-based oversampling outperforms simpler balancing strategies** in this context. It provides:

- **Theoretical soundness:** Ability to capture multi-modal and non-linear distributions of the minority class.  
- **Empirical gains:** Consistent improvements in recall, precision, F1-score, and AUC metrics.  
- **Robustness:** Generates synthetic points in high-density regions, avoiding unrealistic interpolations.

**Recommendation:**  
Adopt GMM-based synthetic data generation as the preferred oversampling method for imbalanced classification problems. It achieves a superior trade-off between detecting minority samples and maintaining overall model reliability. For further improvements, consider combining GMM with ensemble learning or cost-sensitive approaches.



