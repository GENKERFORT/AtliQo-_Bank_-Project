# AtliQo Bank — Credit Card Launch: Customer Segmentation & Campaign Analysis

A two-phase data analysis project for a bank preparing to launch a new credit card: identifying an underserved customer segment, then validating the campaign's impact with a statistically designed A/B test.

## Phase 1 — Exploratory Data Analysis & Segmentation
- Cleaned and explored credit-profile and transaction datasets pulled from MySQL (500K+ transaction records)
- Handled outliers (age, transaction amount) and engineered age-group buckets
- Analyzed correlations among credit-profile variables and visualized spending patterns by platform, category, and payment type
- **Key finding:** customers aged 18–25 make up ~25% of the customer base, show strong shopping activity (top categories: Electronics, Fashion & Apparel, Beauty & Personal Care), but have low credit-card exposure — an untapped, low-risk market for a new credit card product

## Phase 2 — A/B Test Design & Hypothesis Testing
- Calculated required sample size via statistical power analysis across multiple effect sizes, balancing statistical rigor against the business's budget constraints
- Formed control and test groups (100 customers) from the identified 18–25 segment and ran a 2-month campaign (Sep–Nov 2023)
- Ran a two-sample Z-test on pre/post-campaign average transaction amounts, both via the critical-value (rejection region) method and `statsmodels`' `ztest` API, to confirm the result
- **Result:** rejected the null hypothesis — the campaign produced a statistically significant increase in average transaction amount, supporting a full rollout to this segment

## Tech Stack
Python · pandas · NumPy · Matplotlib · Seaborn · SciPy · statsmodels · MySQL · Jupyter Notebook

## Collaboration
This analysis was worked on jointly with Daksh Sharma ([@GENKERFORT](https://github.com/GENKERFORT)) — developed together in notebook form, with the repo maintained on his GitHub.

**My contribution:** _[fill in — e.g., EDA and outlier handling, the age-segmentation analysis, the A/B test design and sample-size calculation, or the hypothesis testing]_

## Setup
```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels mysql-connector-python jupyter
jupyter notebook Atliqo_bank_project.ipynb
```
Requires a local MySQL instance with the `e_master_card` database populated with credit-profile and transaction tables.

> **Note:** the notebook currently has a MySQL password hardcoded in a connection cell. Worth moving that to an environment variable or `.env` file before this repo gets much visibility — it's a live credential sitting in public history.
