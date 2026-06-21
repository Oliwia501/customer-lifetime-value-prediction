# Customer Lifetime Value Prediction

End-to-end customer analytics project focused on predicting Customer Lifetime Value (CLTV) using e-commerce transaction data.

The project uses the Brazilian E-Commerce Public Dataset by Olist and compares probabilistic BTYD models with machine learning approaches to estimate future customer value and support data-driven marketing decisions.

## Objective

The goal of this project is to estimate the future value of customers and identify segments that should receive different marketing actions.

The analysis focuses on:

* predicting 90-day customer value,
* comparing probabilistic and machine learning models,
* identifying high-value and win-back customer segments,
* translating model outputs into actionable marketing recommendations.

## Workflow

* **Data Audit and Cleaning**
  Loaded and joined multiple Olist tables, checked missing values and duplicates, removed invalid transactions, and prepared a clean transaction-level dataset for CLTV modeling.

* **Exploratory Data Analysis**
  Analyzed purchase frequency, recency, monetary value, and customer retention patterns to understand the structure of the customer base.

* **BTYD Modeling**
  Applied BG/NBD to estimate expected future purchases and customer probability of being alive. Used Gamma-Gamma modeling to estimate expected average transaction value and calculate 90-day CLTV.

* **Machine Learning Modeling**
  Trained XGBoost and Random Forest regressors to predict holdout-period revenue using customer-level behavioral features.

* **Model Evaluation**
  Compared BTYD, XGBoost, and Random Forest using MAE, MSE, RMSE, actual vs predicted revenue plots, and aggregate 90-day revenue forecasts.

* **Customer Segmentation and Marketing Strategy**
  Combined predicted CLTV and probability alive to define actionable segments such as High Value Active, Win-Back Priority, Low Value Active, and Low Priority.

## Key Insight

BTYD models provided the most useful framework for aggregate revenue forecasting and marketing segmentation because they produce interpretable outputs such as expected purchases, predicted CLTV, and probability alive.

Machine learning models were useful for customer-level revenue prediction, but the dataset shows strong one-time purchase behavior, making individual-level return prediction difficult.

The most actionable segment is **Win-Back Priority**: customers with high predicted CLTV but weaker activity signals. These customers are strong candidates for targeted reactivation campaigns.

## Tech Stack

Python · pandas · NumPy · scikit-learn · XGBoost · lifetimes · matplotlib · seaborn · kagglehub

## Repository Structure

```text
customer-lifetime-value-prediction/
│
├── customer_lifetime_value_prediction.ipynb
├── requirements.txt
├── README.md
└── presentation/
    └── Customer Lifetime Value Prediction.pdf
```

## How to Run

Open the notebook in Google Colab or Jupyter Notebook.

The dataset is loaded from Kaggle using `kagglehub`, so no manual dataset upload is required.

Install the required Python libraries with:

```bash
pip install -r requirements.txt
```

## Author

Oliwia Iwańska
