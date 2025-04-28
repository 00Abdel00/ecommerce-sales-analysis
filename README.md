# 🛒 E-commerce Sales Analysis

This project involves cleaning and preparing an e-commerce sales dataset from Amazon for further analysis and dashboard building.

The raw data was downloaded from Kaggle and contains transaction information.

---

## 🧐 Initial Data Exploration (Google Sheets)

Before diving into Python, the dataset was first explored manually using Google Sheets:
- Deleted unnecessary columns: `currency`, `ship-country`, and an unnamed empty column.
- Identified formatting issues (e.g., postal codes stored incorrectly as floats).
- Detected missing postal codes and flagged about 30 rows for deletion.
- Observed that `Courier Status` was redundant with the `Status` column.

This manual review helped plan an efficient cleaning strategy before moving to code.

---

## 🛠️ Data Cleaning (Python)

The following cleaning steps were performed using Python and Pandas:

- Converted the `Date` column to a proper datetime format.
- Sorted the dataset chronologically by `Date`.
- Dropped the redundant `Courier Status` column (already captured by `Status`).
- Fixed logical inconsistencies between `Qty` and `Status`:
  - Ensured that cancelled orders have a quantity of zero.
  - Corrected any wrong quantity values.
- Cleaned missing or incorrect `Amount (IDR)` values:
  - Dropped rows with missing `Amount` when `Qty ≠ 0`.
  - Set `Amount = 0` for all orders where `Qty = 0`.
- Dropped the `fulfilled-by` column, which was not useful for analysis.

The final cleaned dataset was saved separately as `Amazon_Sale_Report_Cleaned.csv`.

---

## 📂 Repository Structure

```
/ecommerce-sales-analysis  
│
├── data/                   # Raw and cleaned datasets
│   ├── Amazon Sale Report.csv
│   └── Amazon_Sale_Report_Cleaned.csv
│
├── notebooks/               # Python cleaning scripts
│   └── Amazon_Sales_Data_Cleaning.ipynb
│
└── README.md                # Project documentation
```


---

## 📈 Next Steps (Planned)

- Perform exploratory data analysis (EDA) on the cleaned dataset.
- Build visualizations (Google Sheets and Tableau).
- Create an interactive dashboard to showcase KPIs such as revenue trends, top categories, monthly sales volumes, etc.

---

## 📚 Skills Practiced

- Data cleaning and preprocessing (Excel, Google Sheets, Python Pandas)
- Data validation and consistency checking
- Preparing datasets for business intelligence dashboards
- Documentation and project structuring for data portfolios

---

### 📦 Dataset Source
- [E-commerce Sales Dataset on Kaggle](https://www.kaggle.com/datasets/thedevastator/unlock-profits-with-e-commerce-sales-data)
