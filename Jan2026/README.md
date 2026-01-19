# 📄 Project Report: Determinants of Student Performance

**Date:** January 19, 2026
**Model Performance:** RMSE 8.87 (Top 10% Tier) | : 0.78

## 1. Executive Summary

We developed a predictive model to identify the key drivers of student exam performance. Using a dataset of 630,000 student records, we determined that student success is primarily driven by linear, additive factors (Time + Environment + Rest). Complex interactions (e.g., "Synergy" between sleep and study) were statistically disproven.

The final Linear Regression model captures **78% of the variance** in exam scores with a prediction error (RMSE) of roughly **8.9 points**.

## 2. Key Insights & Drivers

Our analysis isolated the following independent impacts on student scores (holding all else constant):

* **Study Time is Currency:** The strongest predictor. Every additional hour of study yields **+5.7 points**.
* **The "Coaching" Advantage:** Students enrolled in Coaching centers score **~9.1 points higher** than Self-Study students, indicating a massive gap in resource effectiveness.
* **Environment Matters:** Students in "Low Rated" facilities suffer a **-7.3 point penalty** compared to those in High Rated facilities, regardless of their study hours.
* **The Sleep Symmetry:** Moving from "Average" to "Good" sleep adds **+4.2 points**. Interestingly, sleep does not act as a multiplier for study hours; it is an independent additive boost.

## 3. Methodology & Model Selection

We evaluated three distinct modeling approaches to ensure robustness:

| Model |  Score | Verdict |
| --- | --- | --- |
| **OLS Linear Regression** | **0.779** | **Selected.** Best balance of interpretability and accuracy. |
| **Random Forest** | 0.750 | **Rejected.** The non-linear "step" approach failed to capture the smooth linear trends, resulting in overfitting and lower test accuracy. |
| **XGBoost** | 0.782 | **Rejected.** Provided negligible gain (+0.003) at the cost of explainability and computational resources. |
| **Huber Regression** | **0.779** | **Selected.** Tried considering the heavy tails in the dataset. |

## 4. Recommendations

Based on the coefficients, we recommend the following interventions to maximize scores:

1. **Prioritize Coaching:** The single impactful "switch" a student can make is moving from Self-Study to Coaching (Expected Gain: +9 pts).
2. **Fix the Environment:** Facility quality is a major bottleneck. Improvements in infrastructure (Internet/Facilities) offer a direct point-for-point score increase.
3. **Linear Effort:** Students should be advised that consistency (hours) is key. There is no "hack" where sleeping more allows you to study less; both are required independently.

