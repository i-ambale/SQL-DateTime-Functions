# SQL DateTime Functions
© ExploreAI Academy
---
📘 Overview
In this exercise, we explore the use of SQL DateTime functions to work with date and time data. You'll learn how to extract, filter, and manipulate date-related fields from a database using SQL.

These techniques are particularly useful when analyzing time-based data such as sales, revenue trends, or customer activity.

---
## 🎯 Learning Objectives
By the end of this exercise, you will be able to:

✅ Measure the period between dates and times.

✅ Extract specific parts of a DateTime column (e.g., year, month).

✅ Filter records using logical and comparison operators on DateTime fields.

---
## 🧰 Tools & Requirements
- SQL Dialect: SQLite (Compatible with other SQL engines, but minor differences may exist)

- Sample Database: `chinook.db` (A small demo database with tables such as `invoices`, `customers`, and `employees`)

- Environment: Local environment (Jupyter Notebook, SQLite browser, or compatible SQL IDE)
---
## 🏗️ Sample Use Cases
- Calculate monthly or yearly revenue

- Find the age of employees when hired

- Analyze customer purchases over time

- Filter records based on date ranges
---
## 🧪 Example Queries
1. Extracting Year from Date:
```
SELECT 
    SUBSTR(InvoiceDate, 1, 4) AS Year, 
    ROUND(SUM(Total), 2) AS Revenue
FROM invoices
GROUP BY Year
ORDER BY Year;
```
2. Filtering by Date:
```
SELECT * 
FROM invoices
WHERE InvoiceDate >= '2010-01-01';
```
3. Calculating Duration Between Two Dates:
SQLite does not support `DATEDIFF()`, but we can use `julianday()`:
```
SELECT 
    CustomerId,
    InvoiceDate,
    julianday('now') - julianday(InvoiceDate) AS Days_Since_Invoice
FROM invoices;
```
---
## 🧼 Tips for Clean DateTime Queries
- Use SUBSTR() or strftime() to extract year/month/day.

- For SQLite: use julianday() to compute date differences.

- Always ensure your dates are in ISO format (YYYY-MM-DD) for best results.
---
## 📎 References
- SQLite Date & Time Functions

- ExploreAI Academy SQL Curriculum
---
## 📂 File Structure
```
📁 sql_datetime_functions/
│
├── chinook.db                # SQLite sample database
├── datetime_exercise.sql     # SQL queries for the exercise
├── README.md                 # This file
```
