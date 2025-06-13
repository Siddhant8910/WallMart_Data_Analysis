# Walmart Sales Data Analysis - SQL Project

![Walmart Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d6/Walmart_Spark.svg/1200px-Walmart_Spark.svg.png)  
*(Add actual Walmart logo image if needed)*

## 📌 Project Overview
This project analyzes **Walmart sales data** using SQL to uncover business insights, optimize operations, and improve customer experience. The dataset contains:
- 1,000+ transactions across 3 branches (A, B, C)
- Key metrics: revenue, COGS, product lines, customer demographics, and ratings

## 🛠️ Tools Used
- **MySQL** (Database)
- **SQL Queries** (Data cleaning, transformation, and analysis)
- **Data Visualization** (Through query results)

## 📂 Database Schema
Table: `sales`  
Columns:  
`invoice_id`, `branch`, `city`, `customer_type`, `gender`, `product_line`, `unit_price`, `quantity`, `tax_pct`, `total`, `date`, `time`, `payment`, `cogs`, `gross_margin_pct`, `gross_income`, `rating`

## 🔍 Key Analyses Performed

### 1. **Data Preparation**
- Added time segments (`Morning/Afternoon/Evening`)
- Extracted `day_name` and `month_name` from dates

### 2. **Product Analysis**
- Most sold product line: **Electronic accessories**
- Highest revenue by product: **Food and beverages**
- Product line with highest VAT: **Home and lifestyle**

### 3. **Sales Trends**
- Best revenue month: **January**
- Most sales time: **Evenings**
- Top-rated day: **Monday**

### 4. **Customer Insights**
- Most common customer type: **Member**
- Gender distribution: **Nearly equal (50% Male, 50% Female)**
- Highest spending group: **Female members in Branch A**

## 🚀 Key Findings
- Branch C has the **highest revenue** but **lowest ratings**.
- **Electronic accessories** are the top-selling but have lower margins.
- **Members** generate 16% more revenue than normal customers.

## 📊 Sample Queries
```sql
-- Top product line by sales
SELECT product_line, SUM(quantity) AS qty 
FROM sales 
GROUP BY product_line 
ORDER BY qty DESC;

-- Revenue by month
SELECT month_name, SUM(total) AS revenue 
FROM sales 
GROUP BY month_name;
