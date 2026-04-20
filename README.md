# 📊 Sales Trend Analysis Using Aggregations

## 📌 Internship Task 6 – Data Analyst

### 🎯 Objective

The objective of this task is to analyze **monthly revenue** and **order volume** using SQL aggregation techniques.

---

## 🗂️ Dataset

The dataset used is **online_sales**, which contains the following columns:

* `order_id` – Unique ID for each order
* `order_date` – Date of the order
* `amount` – Revenue generated from the order
* `product_id` – Product identifier

---

## 🛠️ Tools Used

* Google Colab
* SQLite (via Python)
* Pandas

---

## 🧠 Concepts Used

* SQL Aggregation Functions:

  * `SUM()` – to calculate total revenue
  * `COUNT(DISTINCT)` – to count unique orders
* Date Functions:

  * `strftime()` – to extract year and month
* `GROUP BY` – to group data by time
* `ORDER BY` – to sort results

---

## 💻 SQL Query

```sql
SELECT 
    strftime('%Y', order_date) AS year,
    strftime('%m', order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_orders
FROM online_sales
GROUP BY year, month
ORDER BY year, month;
```

---

## 📈 Output

The query generates a table showing:

* Monthly total revenue
* Number of unique orders per month

Example:

| Year | Month | Total Revenue | Total Orders |
| ---- | ----- | ------------- | ------------ |
| 2023 | 01    | 300           | 2            |
| 2023 | 02    | 450           | 2            |
| 2023 | 03    | 1000          | 3            |

---

## ⭐ Additional Analysis

### 🔝 Top 3 Months by Revenue

```sql
SELECT 
    strftime('%Y', order_date) AS year,
    strftime('%m', order_date) AS month,
    SUM(amount) AS total_revenue
FROM online_sales
GROUP BY year, month
ORDER BY total_revenue DESC
LIMIT 3;
```

---

## 📚 Key Learnings

* How to group data by month and year
* Difference between `COUNT(*)` and `COUNT(DISTINCT)`
* Use of aggregate functions in real-world datasets
* Performing time-based trend analysis

---

## 📁 Files Included

* Colab Notebook (`.ipynb`)
* SQL Queries
* Output Screenshots
* README.md

---

## ✅ Conclusion

This task helped in understanding how to analyze sales trends using SQL by grouping data and applying aggregation functions. It is a fundamental skill for any Data Analyst role.

---
