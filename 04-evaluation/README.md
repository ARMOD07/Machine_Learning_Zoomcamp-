 

# Homework 4: Lead Scoring Analysis

This project documents the solution to the exercises in Homework 4, which focused on analyzing the **"Lead Scoring" (Bank Marketing)** dataset. The main goal was to build and evaluate a Logistic Regression model to predict lead conversion, concentrating on ROC AUC, Precision, Recall, and F1-score metrics, as well as hyperparameter optimization through cross-validation.

### Dataset

* **Source:** `course_lead_scoring.csv` (Dataset derived from Bank Marketing).
* **Target:** `converted` (Did the lead convert? Binary).

### Data Preparation Steps

1.  **Missing Value Handling:**
    * Missing categorical features were replaced with the string `'NA'`.
    * Missing numerical features were replaced with `0.0`.
2.  **Splitting:** The dataset was split into three parts using `random_state=1`:
    * Training (`train`): 60%
    * Validation (`validation`): 20%
    * Test (`test`): 20%

### Analysis and Results

| Question | Task | Key Finding |
| :---: | :--- | :--- |
| **Q1** | **Feature Importance (ROC AUC)** | The **`lead_score`** variable had the highest AUC (after inversion if AUC < 0.5), confirming its strong predictive power. |
| **Q2** | **Model Training** | The AUC for the Logistic Regression model on the validation set was approximately **0.92**. |
| **Q3** | **Precision/Recall Intersection** | The intersection point of the Precision and Recall curves was found around the threshold of **0.34**. |
| **Q4** | **Maximal F1 Score** | The maximal F1 score was achieved at the threshold of **0.34**. |
| **Q5** | **Cross-Validation (CV)** | The standard deviation (std) of the AUC scores across 5 folds was very low ($\approx 0.001$), indicating high model stability. |
| **Q6** | **Hyperparameter Tuning** | Comparing $C \in [0.000001, 0.001, 1]$, the best performance was achieved with **$C=0.001$** (applying the tie-breaking rule of selecting the smallest $C$). |

### Technologies Used

* Python
* `pandas` (Data manipulation)
* `numpy` (Numerical computation)
* `scikit-learn` (Modeling, metrics, cross-validation)