# E-Commerce Sales Dashboard — Excel

![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![Dataset](https://img.shields.io/badge/Dataset-UCI%20E--Commerce-blue)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

## Project Overview

An end-to-end Excel dashboard analyzing a UK-based online retail dataset with 500,000+ transactions. The project explores which markets and product categories drive the most revenue and where the business is losing money to returns.

Business Question: "Which markets and products drive the most revenue — and where are we losing money to returns?"

---

## Download Full Workbook

The Excel workbook exceeds GitHub's 25MB file size limit and is hosted on Google Drive.

[Download Ecommerce_db_analysis.xlsx](https://docs.google.com/spreadsheets/d/1l_97hBvR2X1BscybRanEKRcLTmAePNgW/edit?usp=sharing&ouid=116625825057905562395&rtpof=true&sd=true)

Note: Open in Microsoft Excel 2016 or later for full functionality including slicers and pivot tables.

---

## File Structure
```
Ecommerce_Dataset_analysis/
│
├── Ecommerce_db_csv.xlsx          # Raw dataset (UCI E-Commerce, imported as CSV)
│
├── Ecommerce_db_analysis.xlsx     # Main Excel workbook (hosted on Google Drive)
│   ├── Ecommerce_Raw_Data         # Original untouched dataset
│   ├── Ecommerce_Working_Sheet    # Cleaned and enriched data
│   ├── Pivot Tables               # Analysis pivot tables
│   └── Dashboard                  # Final interactive dashboard
│
└── README.md
```

---

## Tools and Features Used

| Feature | Purpose |
|---|---|
| VLOOKUP and XLOOKUP | Product category lookup from reference table |
| UNIQUE, FILTER, SORT | Dynamic arrays for live data extracts |
| IFS + SEARCH + ISNUMBER | Automated product categorisation formula |
| INT() and TEXT() | Date and time cleaning and formatting |
| Pivot Tables with Slicers | Interactive aggregations connected across all pivots |
| Conditional Formatting | Highlighting nulls, top 10% revenue rows, anomaly prices |
| Data Cleaning | Duplicates, cancelled orders, missing IDs, text formatting |

---

## Data Cleaning Steps

- Removed 516,773 duplicate rows using InvoiceNo and StockCode as composite primary key
- Filtered out negative quantity rows representing cancelled orders
- Flagged missing CustomerIDs as Guest/Unknown rather than deleting rows
- Standardised text formatting using PROPER, TRIM and UPPER functions
- Separated date and time from InvoiceDate using INT() formula
- Created Month-Year column using TEXT() for monthly pivot grouping
- Built Data_Flag column to exclude non-product entries like Postage and Manual from analysis

---

## Dashboard KPIs

| Metric | Value |
|---|---|
| Total Revenue | £10,587,606 |
| Total Orders | 521,246 |
| Avg Order Value | £20.31 |
| Return Rate | 1.96% |

---

## Dashboard Charts

| Chart | Type | Purpose |
|---|---|---|
| Monthly Revenue Trend | Line with Markers | Shows seasonal revenue patterns over 2010-2011 |
| Top 10 Products by Revenue | Horizontal Bar | Identifies highest revenue generating products |
| Revenue by Country | Horizontal Bar | Compares market performance across 39 countries |

---

## Key Business Insights

1. UK accounts for over 85% of total revenue at £8.9M out of £10.6M total — significant market concentration risk for the business
2. Netherlands generates higher revenue than Germany and France despite having 73% fewer orders — indicating significantly higher average order values from Dutch customers
3. Top 10 products contribute disproportionately to total revenue with Regency Cakestand 3 Tier and Paper Craft Little Birdie leading — confirming the Pareto principle
4. Return and cancellation rate of 1.96% across 1M+ raw transactions — while relatively low this still represents thousands of lost orders worth investigating at a fulfilment level
5. Revenue clusters around Q4 confirming seasonal demand patterns — inventory and marketing investment should be planned around this peak period

---

## Data Quality Observations

- 49% of raw records were duplicate entries highlighting the importance of composite key deduplication
- Non-product entries including Postage, Manual, Dotcom Postage and Amazon Fee were present in the dataset and excluded from product-level analysis using a Data_Flag column
- Some orders had missing or unspecified country information — flagged rather than deleted to preserve transaction records
- Product descriptions contained asterisks, question marks and internal adjustment notes indicating inconsistent data entry practices

---

## Dataset

- Source: UCI E-Commerce Dataset on Kaggle — https://www.kaggle.com/datasets/carrie1/ecommerce-data
- Size: approximately 500,000 transactions after cleaning
- Period: December 2010 to December 2011
- Region: UK-based online retailer shipping to 39 countries

---

## How to Use

1. Download Ecommerce_db_analysis.xlsx from the Google Drive link above
2. Open in Microsoft Excel 2016 or later
3. Navigate to the Dashboard sheet
4. Use the Clean_Country and Month-Year slicers to filter all charts simultaneously
5. All pivot tables and KPI cards update dynamically based on slicer selection

---

## About

Built as Project 1 of a 4-project Data Analytics portfolio by a second year engineering student learning SQL, Python, Excel and Power BI.
