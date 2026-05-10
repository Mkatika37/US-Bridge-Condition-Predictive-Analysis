# US Bridge Condition Analysis and Prediction

## Project Overview
This project focuses on analyzing and predicting the condition of US bridges using data from the Federal Highway Administration (FHWA) InfoBridge. The analysis and machine learning models are built using PySpark on Databricks.

## Repository Structure
- `data/`: Contains the datasets used for the project (ignored in git if too large).
- `notebooks/`: Jupyter notebooks containing the data cleaning, exploratory data analysis (EDA), and machine learning models.
- `html_reports/`: Exported HTML versions of the notebooks and EDA graphs.
- `docs/`: Project presentations and documentation.

## How to Run
1. Download the dataset from the [FHWA InfoBridge website](https://infobridge.fhwa.dot.gov/).
2. Upload the dataset to Databricks (DBFS).
3. Run the `Data cleaning 614.ipynb` notebook to clean the raw data.
4. (Optional) View the EDA in SQL within Databricks to understand the data distribution.
5. Run the `Project.ipynb` notebook which contains the PySpark Machine Learning models (Random Forest, Gradient-Boosted Trees) to predict bridge conditions based on features like Average Daily Traffic, Age, Structure Length, and Deck Area.

## Team
- AIT614-001 Team 5
