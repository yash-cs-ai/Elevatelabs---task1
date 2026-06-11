# Data Cleaning and Preprocessing
**Data Analyst Internship | Task 1**


## Project Overview
This project focuses on the initial and critical data preprocessing stage of the data analytics pipeline. Using a raw dataset from Kaggle (Netflix Movies and TV Shows - https://www.kaggle.com/datasets/shivamb/netflix-shows), the objective was to identify, handle, and resolve common data quality issues—such as missing values, duplicate records, and inconsistent data formatting—to produce a structured, clean dataset optimized for analysis or modeling.

---

## Key Objectives Met
* **Data Quality Assessment:** Explored the raw structure, tracked null entry counts, and evaluated column data types.
* **Handling Missingness:** Implemented strategic imputation (using placeholders) and selective row deletion based on data completeness requirements.
* **Data Standardization:** Converted varied string entries into uniform text formats and normalized messy date fields.
* **Pipeline Integrity:** Designed a clean, reproducible Python pipeline using Pandas to handle end-to-end data processing.

---

## Detailed Summary of Changes

| Data Issue Identified | Impacted Columns | Resolution Strategy Applied |
| :--- | :--- | :--- |
| **Missing Values (High)** | `director`, `cast`, `country` | Imputed missing rows with a fallback string placeholder (`'Unknown'`) to prevent substantial data loss. |
| **Missing Values (Low)** | `rating` | Filled missing categorical data points with an `'Unknown'` flag to maintain consistency. |
| **Missing Values (Critical)** | `date_added`, `duration` | Dropped rows containing missing variables since they constituted a negligible fraction of the data and would break chronological/numerical analysis if replaced with text. |
| **Duplicate Records** | All columns | Audited the dataset for complete row duplication and dropped redundant entries using `.drop_duplicates()`. |
| **Data Alignment & Whitespace** | `date_added` | Stripped hidden leading/trailing spaces (`.str.strip()`) that were preventing successful datetime parsing. |
| **Inconsistent Date Formats** | `date_added` | Converted varied textual and string dates into a unified **DD-MM-YYYY** datetime format pattern. |
| **Column Headers** | All Headers | Standardized all header text uniformly to lowercase snake_case (e.g., removing any accidental spaces or capitals). |

---

## Tools & Libraries Used
* **Language:** Python 3.11
* **Libraries:** Pandas 
* **Environment:** Jupyter Notebook  

---

## Project Structure
```text
├── data/
│   ├── netflix_titles.csv       # The original, untouched Kaggle download
│   └── cleaned_dataset.csv   # Target structured output file ready for analysis
├── notebooks/
│   └── data_cleaning.ipynb   # Complete executable data preprocessing pipeline script
└── README.md                 # Project documentation and modification log
