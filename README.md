# 🛒 E-commerce Sales Analysis

This project involves cleaning and analyzing an Amazon e-commerce sales dataset using Google Sheets, Python (Pandas), and Tableau. It showcases a full data analytics pipeline from raw exploration to cleaned visualizations and dashboards.

The dataset was downloaded from Kaggle and contains transaction records including revenue, categories, order status, and shipping information.

---

## 🧐 Initial Data Exploration (Google Sheets)

Before jumping into Python, we manually explored the raw dataset in Google Sheets to spot early issues and plan the cleaning process:

- Deleted unnecessary columns: `currency`, `ship-country`, and an unnamed empty column.
- Corrected postal code formatting (was stored as float).
- Removed 33 rows with missing postal and location data.
- Flagged `Courier Status` as redundant with `Status`.
- Noted that some cities had inconsistent formatting (capitalization, extra spaces, non-alphabetical characters).

---

## 🧹 Data Cleaning (Python - Pandas)

We performed a detailed cleaning process in Python using Jupyter Notebook:

- Converted `Date` to datetime format and sorted chronologically.
- Dropped unused or redundant columns: `Courier Status`, `fulfilled-by`.
- Corrected rows where `Qty = 0` but `Status ≠ Cancelled`.
- Handled missing or inconsistent `Amount (IDR)`:
  - Rows with missing `Amount` but non-zero quantity were dropped.
  - If `Qty = 0`, `Amount` was set to 0.
- Cleaned `ship-city`:
  - Standardized capitalization.
  - Trimmed extra spaces.
  - Removed rows with symbols or invalid characters.

The cleaned dataset was saved as:
- `Amazon_Sale_Report_Cleaned.csv`
- `Amazon_Sale_Report_Cleaned_Cities.csv` (with clean city names for dashboarding)

---

## 📊 Exploratory Data Analysis (EDA)

All EDA was performed in Python with Pandas and Matplotlib. Visualizations were saved and documented in the `portfolio_visuals.ipynb` notebook and include:

1. **Monthly Revenue Trend**
2. **Monthly Quantity Sold**
3. **Daily Revenue vs Quantity (Line Chart)**
4. **Smoothed Version of Daily Revenue vs Quantity**
5. **Average Order Value (AOV) Trend with Global AOV Line**
6. **Revenue by Top 10 Shipping Cities**
7. **Top 10 Product Categories by Revenue**
8. **Order Status Distribution**

> Each visualization was exported and saved in the `visualizations/pandas/` folder for use in the portfolio.

---

## 📊 Tableau Dashboards

We created and exported 4 Tableau dashboards based on the cleaned dataset:

1. **KPI Overview**: Total Revenue, Number of Orders, Quantity Sold, AOV
2. **Monthly Trends**: Revenue and Quantity per month with commentary
3. **Daily Breakdown**: Daily revenue and quantity with AOV trend
4. **AOV Dashboard**: AOV over time, per category, and per top cities

> The Tableau workbook file is saved in `docs/`  
> Dashboard images are saved in `visualizations/tableau/`

---

## 📁 Repository Structure

- **data/**
  - `Amazon Sale Report.csv`
  - `Amazon_Sale_Report_Cleaned.csv`
  - `Amazon_Sale_Report_Cleaned_Cities.csv`

- **docs/**
  - `dashboards.twbx` – Tableau workbook file

- **notebooks/**
  - `Amazon_Sales_Data_Cleaning.ipynb`
  - `Amazon_Sales_EDA.ipynb`
  - `portfolio_visuals.ipynb` – Cleaned visuals for portfolio

- **visualizations/**
  - **Pandas visuals/** – Matplotlib visuals (Python-generated)
  - **Tableau dashboards/** – Tableau dashboard exports (images/screenshots)

- `README.md`

---

## 🔍 Final Business Insights

- **Declining Sales Trend**: Both revenue and quantity show a consistent downward trend over the three-month period, indicating potential seasonality, market saturation, or operational issues.
- **AOV Fluctuations**: The Average Order Value (AOV) varies significantly day-to-day. While the overall AOV is ~600K IDR, spikes indicate purchases of high-value items, and drops align with high-quantity, low-cost orders.
- **High Revenue Contributors**: A small number of cities and categories account for the bulk of sales. A targeted strategy focusing on these top performers could drive growth.
- **Cancelled Orders**: There’s a non-negligible number of cancelled orders, especially from specific cities. Understanding reasons for cancellations could improve fulfillment efficiency.
- **Product-Type Performance**: Certain product types show consistent performance across all months — indicating product-market fit — while others fluctuate, possibly due to seasonality or supply issues.

---

## 📚 Skills Practiced

- Data exploration and validation (Google Sheets)
- Data cleaning (Pandas, Python)
- Exploratory data analysis (EDA) and storytelling
- Data visualization (Matplotlib, Tableau)
- Dashboard building and KPI tracking
- Git and version control for portfolio projects

---

## 🧠 Learning Reflection

This project allowed me to deepen my understanding of the complete data analysis workflow:

- Practiced **data cleaning** using both Google Sheets and Python.
- Learned how to **handle logical inconsistencies** between columns (like `Qty` and `Status`) and spot outliers.
- Built my first complete **EDA** in a reproducible Jupyter Notebook and exported visuals for a portfolio.
- Gained hands-on experience with **Tableau**, creating multiple dashboards and refining layout, design, and interactivity.
- Strengthened my ability to **document my process** and organize my work using Git and GitHub.

This experience gave me confidence in my ability to extract actionable insights from messy real-world data and present them clearly.

---

## 📦 Dataset Source

- [E-commerce Sales Dataset on Kaggle](https://www.kaggle.com/datasets/thedevastator/unlock-profits-with-e-commerce-sales-data)
