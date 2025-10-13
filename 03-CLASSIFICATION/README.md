# 🎯 Course Lead Scoring Dataset

## 📘 Overview

This dataset, **`course_lead_scoring.csv`**, contains information about **potential students (leads)** who interacted with an **online course platform**.

The goal is to **predict whether a lead will actually enroll in a course** (i.e., become a paying student).  
This process is called **lead scoring** in marketing and sales.

## 📊 Dataset Structure

Each **row** represents one potential student, and each **column** describes their behavior or attributes.

### 🧩 Columns Description

| Column Name           | Description |
|------------------------|-------------|
| `source`               | Where the lead came from (ads, Google search, referral, etc.) |
| `country`              | The lead’s country of origin |
| `age`                  | The person’s age |
| `converted`            | Target variable — `1` if the person enrolled, `0` otherwise |
| `total_pages_visited`  | Number of pages visited on the website |
| `time_on_site`         | Time spent on the website (in minutes) |
| `ads_clicked`          | Number of ads the person clicked |
| `email_opened`         | Whether the person opened marketing emails |

## 🧠 Objective

📘 Overview

In this homework, we worked on a lead scoring classification project using the Bank Marketing dataset. The goal was to predict whether a client would sign up for the platform (converted variable) based on several features.

🧩 Steps Performed

Data Loading

Downloaded the dataset from GitHub using wget.

Loaded it into a Pandas DataFrame.

Data Cleaning and Preparation

Checked for missing values.

Replaced textual "NA" values with np.nan.

For categorical variables: replaced missing values with "NA".

For numerical variables: replaced missing values with 0.0.

Exploratory Data Analysis (EDA)

Found the most frequent category (mode) for the column industry.

Created a correlation matrix for the numerical features to identify the strongest relationships.

Feature Engineering

Split the dataset into train (60%), validation (20%), and test (20%) sets using train_test_split with random_state=42.

Verified that the target column converted was excluded from the feature matrix.

Mutual Information (Categorical Features)

Computed mutual information scores between converted and categorical variables to identify the most informative features.

Model Training – Logistic Regression

Applied one-hot encoding to categorical variables.

Trained a Logistic Regression model using the parameters:

model = LogisticRegression(solver='liblinear', C=1.0, max_iter=1000, random_state=42)


Evaluated model accuracy on the validation set (rounded to two decimals).

Feature Elimination (Least Useful Feature)

Iteratively removed each feature and retrained the model to observe how accuracy changed.

Identified the feature with the smallest impact on accuracy.

Regularization Testing

Tested several values of the regularization parameter C = [0.01, 0.1, 1, 10, 100].

Compared validation accuracies and selected the smallest C with the best performance.

 

---

👩‍💻 **Author:** [amira mohammedi]  
📅 **Dataset Source:** [Alexey Grigorev Datasets](https://github.com/alexeygrigorev/datasets)
