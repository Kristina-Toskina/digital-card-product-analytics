# Digital Card Product Analytics: Cashback, Installments and Transaction Behavior

## Project Overview

This project analyzes a large financial transactions dataset to explore product analytics opportunities for a digital card product. The analysis focuses on customer transaction behavior, cashback category selection, installment offer potential, card type differences, and transaction channel risk.

The goal of the project is to demonstrate how transaction-level data can be transformed into actionable product insights that may support business decisions for a digital banking or card product.

## Business Questions

The analysis is focused on the following questions:

1. Which transaction categories are the strongest candidates for cashback campaigns?
2. Which purchase categories show the highest potential for installment offers?
3. Do credit cards show different high-ticket transaction behavior compared with debit cards?
4. Do online transactions have a different fraud risk profile compared with offline transactions?
5. How can product teams use transaction data to design more targeted card features?

## Dataset

The project uses the open Kaggle dataset **Financial Transactions Dataset: Analytics**.

Dataset link:
https://www.kaggle.com/datasets/computingvictor/transactions-fraud-datasets

The dataset includes several related tables:

* transaction data;
* card information;
* user profiles;
* merchant category codes;
* fraud labels.

The raw data files are not stored in this repository due to file size limitations. To reproduce the analysis, download the dataset from Kaggle and run the notebook in Kaggle or a local Jupyter environment.

## Tools and Libraries

The project was completed using:

* Python;
* pandas;
* NumPy;
* Matplotlib / Seaborn;
* SciPy;
* statsmodels;
* Jupyter Notebook / Kaggle Notebook.

## Methodology

The project workflow included the following steps:

1. **Data loading and initial exploration**
   The raw transaction, card, user, MCC, and fraud label datasets were loaded and inspected.

2. **Data cleaning and preparation**
   Financial fields such as transaction amounts and credit limits were converted into numeric format. Date fields were parsed, missing values and duplicates were checked, and tables were prepared for merging.

3. **Data merging**
   Transactions were linked with card information, user profiles, MCC descriptions, and fraud labels to create one analytical dataset.

4. **Feature engineering**
   Additional product analytics features were created:

   * purchase/refund flag;
   * high-ticket transaction flag;
   * amount-to-credit-limit ratio;
   * installment opportunity flag;
   * online/offline transaction channel;
   * fraud indicator.

5. **Product analysis**
   The analysis focused on product overview metrics, cashback category scoring, installment opportunity analysis, and card type comparison.

6. **Hypothesis testing**
   Two statistical tests were conducted:

   * a proportion z-test comparing high-ticket transaction shares between credit and debit cards;
   * a chi-square test comparing fraud distribution between online and offline transactions.

## Key Findings

### 1. Large-scale transaction environment

The final analytical dataset contains over **13 million transactions**, including more than **12.6 million purchases** and approximately **660 thousand refunds**. The total purchase volume is around **$639 million**, with an average purchase amount of approximately **$50.6**.

### 2. High-ticket transaction behavior

High-ticket transactions were defined as purchases above **$78.21**, representing the top 20% of purchase amounts.

Credit cards showed a higher high-ticket transaction share than debit cards:

* Credit cards: approximately **28%** high-ticket transactions;
* Debit cards: approximately **18%** high-ticket transactions.

This suggests that credit cards are more commonly used for larger purchases.

### 3. Cashback category opportunities

Everyday spending categories appeared to be strong cashback candidates. These include:

* grocery stores and supermarkets;
* service stations;
* miscellaneous food stores;
* restaurants;
* drug stores and pharmacies.

These categories combine high transaction frequency, broad customer reach, and relatively low fraud risk. The analysis suggests that cashback category selection should not be based on transaction volume alone. A more balanced approach should include frequency, reach, repeat behavior, volume, and risk.

### 4. Installment opportunity potential

Installment opportunities were defined as credit card purchases where the transaction amount was at least 10% of the card credit limit.

Installment opportunities represented a small but targeted segment of transactions. They were concentrated in categories with larger average transaction amounts and high high-ticket shares, such as:

* airlines;
* hospitals;
* legal services;
* travel agencies;
* automotive repair;
* selected home-related categories.

This suggests that installment offers may be more effective as targeted product features rather than broad campaigns.

### 5. Online transaction risk

The chi-square test showed that fraud distribution differs significantly between online and offline transactions. Online transactions had a noticeably higher fraud rate, which suggests that digital transaction channels require stronger risk monitoring when designing product campaigns or encouraging online card usage.

## Hypothesis Testing

### Hypothesis 1

**Credit cards have a higher share of high-ticket transactions than debit cards.**

A proportion z-test was used to compare the share of high-ticket transactions between credit and debit cards.

Result: the difference was statistically significant. Credit cards had a higher share of high-ticket transactions than debit cards.

Business interpretation: credit cards are more strongly associated with larger purchases and may be more relevant for installment-related product features.

### Hypothesis 2

**Online transactions have a different fraud rate than offline transactions.**

A chi-square test was used to compare fraud distribution between online and offline transactions.

Result: the difference was statistically significant.

Business interpretation: online transactions require stronger risk monitoring, especially when launching digital campaigns or promoting online card usage.

## Business Recommendations

1. **Use cashback campaigns for everyday spending categories**
   Categories such as groceries, gas stations, restaurants, food stores, and pharmacies are strong candidates due to their high frequency and broad customer reach.

2. **Do not select cashback categories based only on total transaction volume**
   A balanced cashback scoring approach should include frequency, reach, repeat behavior, transaction volume, and fraud risk.

3. **Use installment offers as targeted product features**
   Installment offers should focus on high-value credit card purchases rather than all transactions.

4. **Prioritize consumer-facing high-ticket categories**
   Airlines, hospitals, travel agencies, legal services, and automotive repair may be practical categories for targeted installment offers.

5. **Strengthen risk monitoring for online transactions**
   Online transactions show higher fraud risk, so online-focused campaigns should include additional fraud monitoring and risk controls.

## Repository Structure

```text
digital-card-product-analytics/
│
├── README.md
├── digital_card_product_analytics.ipynb
├── requirements.txt
│
├── data/
│   └── README.md
│
├── reports/
│   └── key_findings.md
│
└── images/
    └── dashboard_or_charts_screenshots.png
```

## How to Run the Project

1. Download the dataset from Kaggle:
   https://www.kaggle.com/datasets/computingvictor/transactions-fraud-datasets

2. Open the notebook:

```text
digital_card_product_analytics.ipynb
```

3. Run the notebook in Kaggle or Jupyter Notebook.

4. Install required libraries if running locally:

```bash
pip install -r requirements.txt
```

## Author

Kristina Toskina
