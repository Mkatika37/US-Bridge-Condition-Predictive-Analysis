# US Bridge Condition Predictive Analysis

**Which of America's bridges are deteriorating — and what drives it?** This project builds an end-to-end big-data pipeline on Databricks to predict the condition of U.S. bridges from federal inventory data, turning millions of inspection records into actionable signals for infrastructure maintenance.

The entire workflow — ingestion, cleaning, EDA, and machine learning — runs on PySpark, so it scales to the full national dataset rather than a sampled subset.

---

## Why it matters

The U.S. has hundreds of thousands of bridges, many decades past their design life. Inspecting and maintaining them is expensive, and resources are limited — so knowing which bridges are most likely to be in poor condition, and what factors drive deterioration, has real budgetary and public-safety value.

This project frames bridge condition as a predictive problem: given a bridge's characteristics — daily traffic load, age, structure length, deck area, and more — can we predict its condition and identify the strongest drivers of deterioration?

---

## Data

Source: the Federal Highway Administration (FHWA) InfoBridge portal, which publishes the National Bridge Inventory — a comprehensive record of U.S. bridge inspections and structural attributes.

Key predictive features include:
- Average daily traffic — the load a bridge carries
- Age — years since construction
- Structure length and deck area — size and exposure
- Additional structural and operational attributes from the inventory

---

## Approach

1. **Data ingestion** — raw FHWA InfoBridge CSVs are loaded into the Databricks File System (DBFS).
2. **Cleaning & preprocessing** (`01_Data_Cleaning.ipynb`) — a PySpark pipeline handles missing values, filters invalid records, engineers features, and produces a modeling-ready dataset.
3. **Exploratory data analysis** — SQL and visual analysis surface distributions, relationships, and candidate predictors (see `EDA_Graphs_Report.html`).
4. **Modeling** (`02_Modeling_and_Evaluation.ipynb`) — two tree-based regressors from Spark MLlib are trained and compared:
   - Random Forest Regressor
   - Gradient-Boosted Trees Regressor
5. **Evaluation** — models are scored on held-out data and compared to identify the best predictor of bridge condition, along with the features that matter most.

---

## Pipeline
---

## Tech stack

| Tool | Role |
|------|------|
| Databricks | Cloud environment for ingestion, processing, and model training |
| PySpark | Distributed data processing and machine learning (Spark MLlib) |
| Python | Data manipulation and scripting |
| SQL | Exploratory data analysis |

---

## Results

The Random Forest and Gradient-Boosted Trees models were compared on held-out data to find the strongest predictor of bridge condition.

> [Fill in your actual numbers from 02_Modeling_Report.html] — e.g. "The Gradient-Boosted Trees model achieved the best performance, with an RMSE of __ and an R2 of __. Age and average daily traffic were the most influential predictors of deterioration."

Full results and visualizations are in the exported HTML reports and the project presentation.

---

## Repository structure

| File | What it contains |
|------|-----------------|
| `01_Data_Cleaning.ipynb` | PySpark notebook — cleaning and preprocessing the raw bridge data |
| `02_Modeling_and_Evaluation.ipynb` | PySpark MLlib notebook — Random Forest and Gradient-Boosted Trees models |
| `01_Data_Cleaning_Report.html` | Exported report of the cleaning notebook |
| `02_Modeling_Report.html` | Exported report of the modeling and evaluation notebook |
| `EDA_Graphs_Report.html` | Exploratory data analysis visualizations |
| `US_Bridge_Condition_Prediction_Presentation.pptx` | Project presentation and methodology |
| `Project Working System.txt` | Methodology and workflow notes |

---

## How to run (Databricks)

1. Download the raw bridge condition dataset from the [FHWA InfoBridge portal](https://infobridge.fhwa.dot.gov/).
2. Upload the `.csv` dataset to the Databricks File System (DBFS).
3. Import the notebooks into your Databricks workspace.
4. Run `01_Data_Cleaning.ipynb` to process the raw data.
5. Run `02_Modeling_and_Evaluation.ipynb` to train and evaluate the PySpark ML pipeline.

---

## Data source

Federal Highway Administration — [InfoBridge](https://infobridge.fhwa.dot.gov/) (National Bridge Inventory).
