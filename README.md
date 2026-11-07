# Salifort Motors — Employee Attrition Analysis

Capstone project for the `Google Advanced Data Analytics Professional Certificate(v.2)`

## Project Overview

This project analyzes employee data from Salifort Motors to help the Human Resources (HR) department understand factors associated with employee turnover and identify employees who may be at risk of leaving the company.

The project uses exploratory data analysis, data cleaning, visualizations, feature engineering, and supervised machine learning to investigate employee attrition (`left`). The goal is to provide evidence-based recommendations that may help improve employee satisfaction and retention.

## Business Problem

Finding, interviewing, and hiring replacements can be time-consuming and expensive. Salifort Motors wants to use its employee data to answer the following question:

> What factors are associated with an employee leaving the company, and can employee attrition be predicted from the available data?

The analysis is intended to support HR decision-making. Model predictions should be treated as signals for further investigation, not as definitive judgments about individual employees.

The notebook also references the dataset source:
[HR Analytics and Job Prediction — Kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction)

## Project Workflow

The notebook follows these main stages:

1. **Data loading and inspection** — imports the dataset and reviews its structure and descriptive statistics.
2. **Data cleaning** — standardizes column names, checks missing values, investigates duplicate records, removes duplicates, and examines outliers.
3. **Exploratory data analysis** — explores relationships between employee attributes and the attrition target through summary statistics and visualizations.
4. **Feature engineering and preparation** — prepares the feature matrix and target labels, including engineered workload-related information used in the tree-based modeling stage.
5. **Model development** — builds and evaluates classification models, including logistic regression and tree-based approaches such as decision trees and random forests.
6. **Model evaluation** — compares model performance using classification metrics and visual tools such as confusion matrices and feature-importance plots.
7. **Recommendations** — translates the findings into possible HR actions and identifies opportunities for further analysis.

## Tools and Libraries

The notebook uses Python and the following main libraries:

- **pandas** — data loading, cleaning, and manipulation.
- **NumPy** — numerical operations.
- **Matplotlib** and **Seaborn** — data visualization.
- **scikit-learn** — model training, data splitting, cross-validation, hyperparameter search, and evaluation metrics.
- **XGBoost** — gradient-boosting estimators imported in the notebook.

## Getting Started

### 1. Clone or download the project

Download the notebook and place it in your project directory.

### 2. Add the dataset

Place `HR_capstone_dataset.csv` in the same directory as the notebook, or update the path in the data-loading cell to match your file location.

### 3. Install dependencies

Install the libraries used by the notebook:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost jupyter
```

The notebook reports that the random forest modestly outperformed the decision tree. Refer to the notebook's model evaluation cells for the detailed comparison and plots.

## Key Findings and HR Recommendations

The notebook's analysis identifies workload and employee experience as important areas to investigate. In particular, `last_evaluation`, `number_project`, `tenure`, and the engineered `overworked` feature appear among the most important predictors in the tree-based analysis.

The recommendations proposed in the notebook include:

- Review the number of projects assigned to employees and consider setting reasonable workload limits.
- Investigate why employees with around four years of tenure may report dissatisfaction, and review appropriate career-development or promotion opportunities.
- Review expectations around long working hours, overtime compensation, and time off; communicate relevant policies clearly.
- Hold company-wide and team-level discussions to better understand workplace culture and workload concerns.
- Ensure performance evaluation and reward practices do not disproportionately favor employees who work exceptionally long hours.

These are areas for organizational investigation, not automatic actions to take against individual employees.

## Limitations and Ethical Considerations

- The dataset represents the information available in this analysis and may not capture every factor that influences an employee's decision to leave.
- Predictive performance does not establish that a feature causes attrition.
- `last_evaluation` may introduce data-leakage concerns or may not be available early enough to support a useful intervention. The notebook recommends evaluating model behavior without this feature.
- False positives can lead HR to incorrectly flag employees as likely to leave. Predictions should therefore be reviewed carefully and used to support constructive conversations and organization-wide improvements.
- Employee data should be handled confidentially. Any practical use of predictions should include appropriate privacy safeguards, fairness checks, and human oversight.


## Disclaimer

This project is an analytical and educational exercise. Its findings and predictive models should not be used as the sole basis for employment decisions. The results are intended to help identify patterns and inform fair, supportive, and evidence-based HR practices.
