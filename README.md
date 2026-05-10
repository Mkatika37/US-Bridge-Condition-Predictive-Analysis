# US Bridge Condition Predictive Analysis using Databricks

## Project Overview
This project presents an end-to-end big data pipeline and machine learning analysis aimed at predicting the condition of US bridges. Utilizing data from the Federal Highway Administration (FHWA) InfoBridge, the solution is built entirely on **Databricks**, leveraging **PySpark** for distributed data processing and machine learning.

The goal is to provide actionable insights for infrastructure maintenance by predicting bridge deterioration based on factors such as daily traffic, age, structure length, and deck area.

## Technologies Used
- **Databricks**: Primary environment for data ingestion, processing, and model training.
- **PySpark**: Distributed data processing and machine learning (Spark MLlib).
- **Python**: Data manipulation and scripting.
- **SQL**: Exploratory Data Analysis (EDA).

## Repository Structure
- `data/`: Directory for raw datasets (`.csv` files ignored in version control for space efficiency).
- `notebooks/`: 
  - `01_Data_Cleaning.ipynb`: PySpark notebook for cleaning and preprocessing the raw bridge data.
  - `02_Modeling_and_Evaluation.ipynb`: PySpark MLlib notebook containing the Random Forest and Gradient-Boosted Trees regressor models.
- `html_reports/`: Exported HTML reports of the Databricks notebooks and EDA visual graphs.
- `docs/`: Project presentation and methodology documentation.

## How to Run in Databricks
1. Download the raw bridge condition dataset from the [FHWA InfoBridge portal](https://infobridge.fhwa.dot.gov/).
2. Upload the `.csv` dataset to the Databricks File System (DBFS).
3. Import the notebooks from the `notebooks/` directory into your Databricks workspace.
4. Run `01_Data_Cleaning.ipynb` to process the raw data.
5. Run `02_Modeling_and_Evaluation.ipynb` to execute the PySpark ML pipeline and evaluate the predictive models.
