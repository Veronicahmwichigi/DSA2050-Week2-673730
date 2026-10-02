# DSA 2050 Week 2 – SQL Practical Lab

## Student Information

**Name:** Veronicah Wanjiku
**Student ID:** 673730

## Project Objective

This project is part of the **DSA 2050 Data Science Methodology Week 2 Practical Lab**. The objective of the practical is to work with relational data using Python, pandas, SQLite, SQL, and JSON. The project focuses on inspecting datasets, identifying data-quality problems, performing SQL queries and JOINs, validating row counts and sales totals, and analyzing customer segments and regional sales.

## Technologies Used

* Python
* Pandas
* SQLite
* SQL
* JSON
* Jupyter Notebook / VS Code

## Project Files

```text
DSA2050-Week2-StudentID/
│
├── DSA2050_Week2_SQL_Lab.ipynb
├── customers.csv
├── orders.csv
├── regions.json
└── README.md
```

### File Description

* **DSA2050_Week2_SQL_Lab.ipynb** – Contains the Python code, SQL queries, analysis, and findings.
* **customers.csv** – Contains customer information such as CustomerID, CustomerName, Segment, and RegionCode.
* **orders.csv** – Contains order information such as OrderID, CustomerID, OrderAmount, and ProductCategory.
* **regions.json** – Contains the region codes and their corresponding region names.
* **README.md** – Provides an overview of the project and its key findings.

## Data Quality Investigation

A duplicate **CustomerID `C004`** was found in the customer dataset. This caused the order belonging to C004 to be duplicated when the customer and order tables were joined.

Before the JOIN, there were **15 orders** with total sales of **KSh 113,500**. After the incorrect JOIN, the number of rows increased to **16** and total sales increased to **KSh 122,600**.

The duplicate customer record was removed to create a cleaned customer table. After the corrected JOIN, the row count returned to **15** and the total sales returned to **KSh 113,500**.

## Key Findings

### 1. Product Category Performance

Electronics recorded the highest total sales of **KSh 51,500** and had the highest number of orders, with **6 orders**.

Home recorded the lowest total sales of **KSh 24,600** and had the lowest number of orders, with **4 orders**.

### 2. Customer Segment Performance

The **Corporate segment** generated the highest total sales, with **KSh 46,800** from four orders.

Retail customers had the highest number of orders, with **6 orders**, while SME customers generated **KSh 27,200** from four orders.

### 3. Regional Sales Performance

**Nairobi** generated the highest recorded regional sales, with **KSh 39,800**.

However, this does not automatically mean that Nairobi is the company's overall best-performing region. The dataset contains only 15 orders and does not include information such as order dates or profit margins.

## Important Data Quality Issues

The analysis identified two important data-quality issues:

* **Duplicate CustomerID:** `C004` appears twice in the customer dataset.
* **Unmatched CustomerID:** `C999` appears in the orders dataset but does not exist in the customer dataset.

The unmatched `C999` order was not deleted. Instead, it was retained during the `LEFT JOIN`, resulting in `NULL` values for the customer's name and segment.

## Conclusion

This practical demonstrated the importance of checking data quality before joining relational datasets. Duplicate keys can cause records and sales totals to be duplicated even when a SQL JOIN executes successfully. Comparing row counts and total sales before and after a JOIN helps identify these problems. The Corporate segment generated the highest sales at KSh 46,800, while Nairobi recorded the highest regional sales at KSh 39,800. A limitation of the analysis is that the dataset is small and may not represent the company's overall sales performance.

## Author

**Veronicah Wanjiku**

**Course:** DSA 2050 – Data Science Methodology
