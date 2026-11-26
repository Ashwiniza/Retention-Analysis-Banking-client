# End-to-End Customer Retention Analysis Platform

An end-to-end customer analytics and machine learning platform designed to transform raw customer, billing, usage, support, and churn data into business-ready insights and predictive analytics.

The project integrates **Azure Data Factory, Azure Data Lake Storage Gen2, Azure Databricks, PySpark, Delta Lake, Apache Airflow, Machine Learning, and Power BI** to build a structured data engineering and customer retention analytics solution.

---

## Project Overview

Customer retention is an important business objective for subscription-based organisations. Understanding customer behaviour, revenue patterns, service usage, and support interactions can help organisations identify potential churn risks and improve customer engagement.

This project implements an end-to-end analytics pipeline that processes multiple customer-related datasets, applies data transformation and quality validation, develops customer-level analytical features, trains machine learning classification models, and presents insights through Power BI reports.

## Technology Stack

| Category | Technologies |
|---|---|
| Cloud Platform | Microsoft Azure |
| Data Ingestion | Azure Data Factory |
| Data Storage | Azure Data Lake Storage Gen2 |
| Data Processing | Azure Databricks, Apache Spark, PySpark |
| Data Architecture | Medallion Architecture |
| Storage Format | Delta Lake |
| Data Orchestration | Apache Airflow, Docker Compose |
| Machine Learning | PySpark MLlib |
| Machine Learning Models | Decision Tree, Random Forest, Logistic Regression |
| Business Intelligence | Microsoft Power BI |
| Programming Language | Python |
| Data Analysis | Pandas, NumPy, Matplotlib |

## Solution Architecture

The platform follows a Medallion Architecture to organise data processing into Bronze, Silver, and Gold layers.

**Data Sources → Bronze Layer → Silver Layer → Customer 360 → Gold Layer → Feature Engineering → Machine Learning → Power BI**

### Architecture Layers

**1. Bronze Layer – Raw Data Ingestion**

The Bronze layer loads the source datasets into the data platform.

Source datasets include:
- CRM customer records
- Billing transactions
- Customer usage events
- Customer support tickets
- Churn labels

**2. Silver Layer – Data Transformation**

The Silver layer processes and prepares individual datasets.

Transformations include:
- Customer data cleaning
- Billing data transformation
- Usage data aggregation
- Support ticket transformation
- Churn label validation

**3. Customer 360 – Master Customer Table**

The Customer 360 notebook integrates the Silver datasets into a consolidated customer-level analytical table.

**4. Gold Layer – Retention Features**

The Gold layer creates business-ready customer retention features for downstream analytics, reporting, and machine learning.

**5. Feature Engineering and Machine Learning**

The feature engineering process includes:
- Exploratory Data Analysis (EDA)
- Missing-value analysis
- Outlier detection and IQR-based capping
- Business feature creation
- Categorical encoding
- Feature assembly and scaling
- Correlation analysis
- Feature importance analysis

The resulting machine-learning dataset is used to train and compare classification models.

## Machine Learning Model Comparison

Three classification algorithms are implemented using PySpark MLlib:

- Decision Tree
- Random Forest
- Logistic Regression

Models are evaluated using an 80:20 training and testing split and the following metrics:

- Accuracy
- Precision
- Recall
- F1-Score

The prepared machine-learning dataset contains **286,893 records**.

The model comparison results are saved to the `model_comparison_results` table for reporting and analysis.

## Data Quality and Incremental Processing

The platform also includes dedicated notebooks for:

- Row-count validation
- Null-value validation
- Duplicate validation
- Schema and data-type validation
- Invalid-date validation
- Incremental data processing
- Delta Lake MERGE operations
- Pipeline execution validation

These components support data consistency and controlled data processing.

## Power BI Analytics

The project includes seven Power BI report files (`.pbix`) for customer retention and business analytics.

The Power BI layer is designed to consume the prepared analytical dataset and communicate customer, revenue, engagement, and churn-related insights.

Dashboard screenshots and report descriptions can be added in the `power_bi` directory.

## Workflow Orchestration

Apache Airflow is configured using Docker Compose with a CeleryExecutor-based environment.

The project also includes a Master Pipeline notebook that validates output tables, checks pipeline execution, and generates an execution summary.

## Project Repository Structure

```text
customer-retention-analytics-platform/
│
├── README.md
│
├── databricks_notebooks/
│   ├── Notebook 1 - Bronze Layer.ipynb
│   ├── Notebook 2 - Silver Customers.ipynb
│   ├── Notebook 3 - Silver Billing.ipynb
│   ├── Notebook 4 - Silver Usage.ipynb
│   ├── Notebook 5 - Silver Support.ipynb
│   ├── Notebook 6 - Silver Churn.ipynb
│   ├── Notebook 7 - Customer 360.ipynb
│   ├── Notebook 8 - Gold Layer.ipynb
│   ├── Notebook 9 - Power BI Dataset.ipynb
│   ├── Notebook 10 - Data Quality Framework.ipynb
│   ├── Notebook 11 - Incremental Load.ipynb
│   ├── Notebook 13 - Feature Engineering.ipynb
│   ├── Notebook 14 - ML Model Comparison.ipynb
│   └── Notebook 15 - Master Pipeline.ipynb
│
├── airflow/
│   ├── docker-compose.yaml
│   ├── dags/
│   ├── logs/
│   └── plugins/
│
├── power_bi/
│   ├── reports/
│   └── screenshots/
│
├── architecture/
│   └── architecture_diagram.png
│
└── results/
    ├── model_comparison/
    └── execution_reports/
```

*The structure above is the recommended repository organisation. Update the filenames and folders to match the files actually committed.*

## Project Objectives

- Develop an end-to-end cloud-based customer analytics pipeline.
- Implement Medallion Architecture for structured data processing.
- Integrate multiple customer-related datasets.
- Build a consolidated Customer 360 analytical dataset.
- Engineer meaningful customer retention features.
- Compare machine learning models for churn prediction.
- Develop interactive Power BI analytics.
- Support data quality validation and incremental processing.

## Future Improvements

- Hyperparameter optimisation and advanced model evaluation.
- Model explainability using SHAP.
- Automated model retraining and monitoring.
- Real-time customer churn prediction.
- Advanced customer segmentation.
- Production deployment and performance optimisation.

## Author

**Ashwini Zade**

Data Science | Data Engineering | Machine Learning | Banking Client

---

*This repository is intended for educational, research, and professional portfolio purposes.*
