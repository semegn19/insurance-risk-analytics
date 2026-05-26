# insurance-risk-analytics

## Project Overview

This project analyzes historical automobile insurance data for AlphaCare Insurance Solutions (ACIS), a South African auto-insurance company preparing for an aggressive growth phase.

The primary objective is to support ACIS in transitioning from intuition-based pricing toward a data-driven risk and pricing strategy using exploratory data analysis, statistical hypothesis testing, machine learning, and risk-based premium optimization.

The analysis uses an 18‑month historical claims dataset covering the period from February 2014 to August 2015.

---

# Business Objective

ACIS aims to improve underwriting profitability while remaining competitive in the South African insurance market.

The project focuses on:

* Understanding claim behavior across customer and geographic segments
* Identifying low-risk customer groups
* Supporting data-driven premium adjustments
* Improving pricing transparency and risk segmentation
* Building predictive models for claim severity and claim probability

Two core business metrics are used throughout the project:

## Loss Ratio

Loss Ratio = TotalClaims / TotalPremium

This metric measures underwriting performance.

* Loss Ratio > 100% → underwriting loss
* Lower Loss Ratio → stronger profitability

## Margin

Margin = TotalPremium − TotalClaims

This metric measures direct profitability for policies or customer segments.

---

# Project Structure

```text
project-root/
│
├── data/
│   ├── insurance_raw.csv
│   └── insurance_cleaned.csv
│
├── notebooks/
│   ├── task1_eda.ipynb
│   ├── task3_hypothesis_testing.ipynb
│   └── task4_modeling.ipynb
│
├── reports/
│   └── interim_report.pdf
│
├── .dvc/
├── .gitignore
├── dvc.yaml
├── requirements.txt
└── README.md
```

---

# Tasks Completed

## Task 1 — Exploratory Data Analysis (EDA)

The exploratory analysis included:

* Data summarization and descriptive statistics
* Data quality assessment and missing-value handling
* Univariate analysis of financial variables
* Bivariate and multivariate analysis
* Geographic risk analysis by province and postal code
* Loss ratio analysis by province, vehicle type, and gender
* Temporal trend analysis over the 18‑month period
* Vehicle make/model risk profiling
* Outlier detection on financial variables

Key findings included:

* Overall portfolio loss ratio exceeded 100%
* Gauteng and KwaZulu-Natal exhibited elevated risk
* Heavy Commercial vehicles showed high claim severity
* Significant financial outliers existed in claims data

---

## Task 2 — Data Version Control (DVC)

DVC was integrated to ensure reproducibility and auditability.

Implemented steps:

* Initialized DVC in the project
* Configured local remote storage
* Versioned raw and cleaned datasets
* Tracked dataset evolution across preprocessing stages

Benefits:

* Reproducible analysis
* Traceable data lineage
* Easier collaboration
* Improved regulatory transparency

---

## Task 3 — A/B Hypothesis Testing

1. No risk differences across provinces
2. No risk differences between zip codes
3. No margin differences between zip codes
4. No significant risk differences between women and men

KPIs:

* Claim Frequency
* Claim Severity
* Margin

statistical tests:

* Chi-squared tests
* Independent t-tests
* Z-tests

---

## Task 4 — Statistical Modeling & Risk-Based Pricing

### Modeling Goals

1. Claim Severity Prediction

* Predict TotalClaims for policies with claims

2. Premium Optimization

* Predict claim probability and combine with severity estimates

Pricing formula:

```text
Premium = P(claim) × Predicted Severity + Expense Loading + Profit Margin
```

### Algorithms

* Linear Regression
* Random Forest
* XGBoost

### Model Interpretability

Planned interpretability techniques:

* SHAP
* LIME

These methods will identify the most influential features affecting claim risk and pricing decisions.

---

# Technologies Used

## Programming Language

* Python 3

## Data Analysis

* pandas
* numpy

## Visualization

* matplotlib
* seaborn

## Machine Learning

* scikit-learn
* XGBoost

## Experiment & Data Management

* Git
* DVC

---

# Installation

## 1. Clone the Repository

```bash
git clone https://github.com/semegn19/insurance-risk-analytics.git
cd insurance-risk-analytics
```

## 2. Create Virtual Environment

```bash
python -m venv venv
```

Activate environment:

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Reproducing the Data Pipeline

## Initialize DVC

```bash
dvc init
```

## Pull Versioned Data

```bash
dvc pull
```

## Run Analysis

Open and execute notebooks inside the `notebooks/` directory.

---

# Example DVC Workflow

Track a dataset:

```bash
dvc add data/insurance_cleaned.csv
```

Push data to remote storage:

```bash
dvc push
```

Pull data from remote storage:

```bash
dvc pull
```

---

# Results and Insights

The project aims to provide:

* Data-driven pricing recommendations
* Identification of low-risk customer segments
* Improved underwriting transparency
* Geographic and demographic risk insights
* Predictive risk scoring models
* Risk-based premium optimization

