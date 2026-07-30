# Customer Analytics Portfolio

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-Machine%20Learning-F7931E?logo=scikitlearn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-Churn%20Prediction-006600)
![lifetimes](https://img.shields.io/badge/lifetimes-CLTV-6F42C1)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

**BSc Artificial Intelligence — AI for Communication and Marketing**

A portfolio of three applied customer analytics projects covering customer segmentation, churn prediction and customer lifetime value estimation.

The projects combine exploratory data analysis, statistical modeling and machine learning to transform customer data into actionable marketing and communication strategies.

The complete portfolio received full marks in the AI for Communication and Marketing course.

---

## Portfolio Overview

Understanding customer behavior is essential for designing effective marketing strategies, improving retention and allocating resources efficiently.

This portfolio addresses three complementary business questions:

1. How can customers be divided into meaningful behavioral segments?
2. Which customers are most likely to leave a service?
3. Which customers are expected to generate the greatest future value?

The repository contains three projects:

| Project | Main Objective | Main Methods |
|---|---|---|
| Customer Segmentation | Identify meaningful customer profiles | RFM analysis and K-Means clustering |
| Churn Prediction | Estimate customer churn risk | Classification models, lift and decile analysis |
| Customer Lifetime Value | Estimate future customer value | BG/NBD, Gamma-Gamma and machine learning regression |

---

## Repository Structure

```text
customer-analytics-portfolio/
│
├── 01-customer-segmentation/
│   ├── analysis code
│   └── project presentation
│
├── 02-churn-prediction/
│   ├── analysis code
│   └── project presentation
│
├── 03-customer-lifetime-value/
│   ├── analysis code
│   └── project presentation
│
├── LICENSE
└── README.md
```

Each project folder contains the corresponding analysis code and final presentation.

---

# 1. Customer Segmentation

## Project Objective

The first project focuses on identifying groups of customers with similar characteristics and purchasing behavior.

Customer segmentation allows companies to move beyond generic communication strategies and design more targeted campaigns for different customer profiles.

The project combines customer behavior analysis, RFM variables and clustering techniques.

## Dataset

The analysis uses customer-level marketing data containing information about:

- customer demographics
- income and household characteristics
- product purchases
- campaign responses
- purchasing channels
- recency and frequency of transactions

## Methodology

### Data Cleaning and Preparation

The dataset is inspected for missing values, inconsistent observations and variables requiring transformation.

Customer characteristics and purchasing behavior are prepared before the segmentation analysis.

### RFM Analysis

Customers are evaluated according to three main behavioral dimensions:

- **Recency:** how recently the customer made a purchase
- **Frequency:** how frequently the customer purchases
- **Monetary value:** how much the customer spends

RFM variables provide a compact representation of customer value and engagement.

### Customer Clustering

K-Means clustering is applied to identify groups of customers with similar characteristics.

The clustering workflow includes:

- feature selection
- numerical preprocessing
- feature scaling
- comparison of alternative cluster solutions
- interpretation of the resulting customer groups

The final segmentation identifies three main customer profiles.

## Business Interpretation

The resulting clusters are translated into customer personas and communication strategies.

One relevant opportunity identified by the analysis is a group of approximately 260 customers whose current spending is relatively low compared with their income potential.

This segment may represent an opportunity for:

- personalized offers
- targeted communication
- cross-selling initiatives
- product recommendations
- engagement campaigns

## Main Techniques

- exploratory data analysis
- customer behavior analysis
- RFM analysis
- feature scaling
- K-Means clustering
- customer persona development
- marketing strategy formulation

---

# 2. Churn Prediction

## Project Objective

The second project focuses on predicting whether a customer is likely to stop using a service.

Customer churn prediction can help organizations identify at-risk customers before they leave and prioritize retention interventions.

## Dataset

The dataset contains 5,630 customer records and 20 variables.

The target variable indicates whether the customer churned. Approximately 16.8% of customers belong to the churn class, making the problem moderately imbalanced.

The available variables describe:

- customer characteristics
- service usage
- satisfaction
- complaints
- relationship history
- demographic information

## Machine Learning Task

The problem is formulated as a binary classification task:

- `Churn = 0`: the customer remains with the company
- `Churn = 1`: the customer leaves the company

The objective is not only to maximize predictive performance, but also to identify the customers who should receive retention actions.

## Methodology

### Exploratory Data Analysis

The analysis examines the relationship between churn and variables such as:

- customer tenure
- recency of interaction
- satisfaction
- complaints
- service usage
- demographic characteristics

### Feature Engineering

Additional customer indicators are created to represent behavioral and relationship patterns.

The engineered information includes variables related to:

- tenure
- recency
- satisfaction
- complaint behavior
- customer engagement

### Model Development

Classification models are trained to estimate customer churn probability.

The workflow includes:

- data preprocessing
- feature engineering
- model training
- model comparison
- probability estimation
- classification evaluation

### Customer Prioritization

The predicted churn probabilities are interpreted as customer risk scores.

Customers are ordered from highest to lowest estimated churn risk and divided into groups for lift and decile analysis.

This makes it possible to evaluate how effectively the model concentrates actual churners among the highest-risk customers.

## Business Interpretation

The model is designed to support targeted retention campaigns.

Rather than contacting every customer, the company can focus its resources on customers with the highest predicted churn probability.

The analysis connects model outputs with possible interventions such as:

- personalized retention offers
- proactive customer support
- complaint resolution
- satisfaction recovery actions
- targeted communication campaigns

## Main Techniques

- exploratory data analysis
- feature engineering
- binary classification
- churn probability estimation
- model evaluation
- lift analysis
- decile analysis
- customer risk segmentation

---

# 3. Customer Lifetime Value

## Project Objective

The third project focuses on estimating Customer Lifetime Value, or CLTV.

CLTV represents the expected economic value generated by a customer over a future period.

Estimating customer value can support decisions related to:

- customer acquisition
- retention budgets
- loyalty programs
- personalized communication
- marketing resource allocation

## Dataset

The project uses the Brazilian E-Commerce Public Dataset by Olist.

The original data are distributed across nine related tables containing information about:

- customers
- orders
- order items
- payments
- products
- sellers
- reviews
- product categories
- geographic information

The tables are combined to reconstruct customer purchase histories.

## Methodology

### Data Integration

The relational tables are merged and prepared to create customer-level transaction data.

The preprocessing stage includes:

- table integration
- date conversion
- transaction aggregation
- customer identification
- monetary value calculation
- inspection of invalid or incomplete transactions

### Calibration and Holdout Periods

The transaction history is divided into:

- a calibration period used to estimate customer behavior
- a 90-day holdout period used to evaluate future purchasing activity

This temporal design makes it possible to assess whether the models generalize to future customer behavior.

### Probabilistic CLTV Modeling

The project applies two established probabilistic models.

#### BG/NBD Model

The BG/NBD model estimates:

- expected future purchase frequency
- the probability that a customer remains active
- the expected number of transactions during a future period

#### Gamma-Gamma Model

The Gamma-Gamma model estimates the expected monetary value of future transactions.

The frequency and monetary components are then combined to calculate customer lifetime value.

### Machine Learning Approach

A machine learning regression approach is also developed to estimate future customer value from engineered customer features.

The project compares probabilistic CLTV modeling with a more flexible predictive approach based on customer-level characteristics.

### Macro and Micro Strategies

The CLTV estimates are used to develop two levels of business strategy:

- **Macro strategy:** broad allocation of marketing resources across customer-value segments
- **Micro strategy:** personalized actions for individual customers or narrowly defined customer groups

## Business Interpretation

Customers are grouped according to their predicted future value.

High-value customers may justify:

- loyalty benefits
- priority support
- personalized recommendations
- exclusive offers
- retention investments

Customers with growth potential may instead receive actions designed to increase purchase frequency or average order value.

## Main Techniques

- relational data integration
- transaction aggregation
- customer-level feature engineering
- temporal calibration and holdout split
- BG/NBD modeling
- Gamma-Gamma modeling
- customer lifetime value estimation
- regression modeling
- customer value segmentation
- marketing strategy development

---

# Results and Business Value

The three projects provide complementary perspectives on customer behavior.

Customer segmentation identifies groups with similar characteristics and purchasing patterns.

Churn prediction estimates the probability that a customer will leave and supports retention prioritization.

Customer lifetime value estimates future economic value and helps determine how marketing resources should be allocated.

Together, the projects demonstrate how customer analytics can support the complete customer management process:

1. understand the customer base
2. identify customers at risk
3. estimate future customer value
4. define targeted communication strategies
5. allocate marketing resources more efficiently

---

# Tech Stack

## Language

- Python

## Libraries

- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- XGBoost
- lifetimes

## Techniques

- exploratory data analysis
- data cleaning
- feature engineering
- RFM analysis
- K-Means clustering
- binary classification
- churn prediction
- lift and decile analysis
- BG/NBD modeling
- Gamma-Gamma modeling
- regression
- customer lifetime value estimation
- business-oriented model interpretation

---

# Reproducibility

To explore the projects:

1. Clone the repository.
2. Open the folder corresponding to the selected project.
3. Install the required Python libraries.
4. Open the notebook or source file.
5. Run the analysis in the original order.

```bash
git clone https://github.com/sabinagallo/customer-analytics-portfolio.git
cd customer-analytics-portfolio
```

The datasets may not be included directly in the repository because of file size or redistribution restrictions.

When necessary, the corresponding project documentation describes the original data source.

---

# Limitations and Future Improvements

The projects were developed as academic applications of customer analytics and should not be interpreted as production-ready decision systems.

Possible future improvements include:

- evaluating the models on more recent or external datasets
- introducing temporal validation for churn prediction
- assessing model calibration
- comparing additional clustering algorithms
- incorporating customer acquisition costs into CLTV
- evaluating fairness across customer groups
- developing interactive dashboards
- deploying the models through reproducible data pipelines

---

# Author

**Sabina Gallo**

BSc Artificial Intelligence  
University of Pavia, University of Milan and University of Milan-Bicocca

[GitHub](https://github.com/sabinagallo) | [LinkedIn](https://linkedin.com/in/sabina-gallo)
