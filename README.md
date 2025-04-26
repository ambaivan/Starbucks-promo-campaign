# Starbucks Promotion Optimization

This project focuses on building a machine learning model to optimize a promotional campaign for Starbucks, based on a dataset originally provided by Starbucks as a take-home assignment for job candidates.

### Project Objective
Starbucks ran a simulated experiment to test whether sending promotional offers would increase purchases of a specific $10 product. Each promotion sent costs the company $0.15. Therefore, to maximize profitability, it is crucial to target only customers who are most receptive to the promotion.

The primary goal of this project is to use customer features (V1–V7) to decide who should receive the promotion in order to maximize:

    - Incremental Response Rate (IRR) — the increase in purchase probability among those who received the promotion vs. those who did not.

    - Net Incremental Revenue (NIR) — the overall profit after accounting for promotion costs.

### Data
    Train_data.csv: Training dataset (~80,000 observations)
    Test.csv: Test dataset (~40,000 observations)

Each record includes:
    Promotion: Whether the user received a promotion (binary)
    Purchase: Whether the user purchased the product (binary)
    V1 - V7: Abstract customer features

### Methodology
Two machine learning models were built and evaluated:
    Logistic Regression Model
    Random Forest Classifier

Both models were trained using GridSearchCV for hyperparameter tuning. Performance was evaluated against a benchmark model developed by Starbucks.

### Results

Model | NIR ($) | IRR | Compared to Benchmark
Starbucks Benchmark | 189.45 | 0.0188 | Baseline
Logistic Regression | 284.75 | 0.0201 | +55% NIR, +7% IRR
Random Forest | 238.45 | 0.0188 | +26% NIR, same IRR

Logistic Regression significantly outperformed both the benchmark and the Random Forest model in both NIR and IRR
The results from both models are also statistically different from zero, suggesting certainty about any material impact with 95% confidence level.

### Repository Structure
    Starbucks_promo-LogisticReg.ipynb: Logistic Regression model development.
    Starbucks_promo-RandomForest.ipynb: Random Forest model development.
    Train_data.csv and Test.csv: Datasets.
    test_results.py: Utility script to compare model outputs against Starbucks' benchmark.

