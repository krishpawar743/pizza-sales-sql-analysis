# 🍕 Pizza Sales SQL Analysis Project

This project focuses on analyzing pizza sales data using **SQL** to uncover trends in customer behavior, popular pizzas, and revenue insights. The project is ideal for practicing real-world SQL queries like joins, aggregations, filtering, and date-based analysis.

---

## 📁 Project Structure

- `pizza_sales_analysis.sql` → All SQL queries used in the analysis.
- `pizza_sales_data.csv` → Pizza sales dataset.
- `pizza_sales_report.pdf` → Final report with summarized insights and visuals (optional).
- `README.md` → Project documentation and usage instructions.
- `ERD.png` → (Optional) Entity Relationship Diagram.

---

## 🎯 Objectives

- Identify best-selling pizzas by quantity and revenue
- Analyze sales by day, month, and time of day
- Understand average order value and order frequency
- Use SQL skills for real business case analysis

---

## 📊 Key Insights Explored

- Top 5 pizzas by revenue and quantity
- Peak order hours and days
- Average order value over time
- Sales trend across months and pizza categories
- Most popular pizza sizes

---

## 🛠️ SQL Concepts Used

- SELECT, WHERE, GROUP BY, ORDER BY
- Aggregate functions (SUM, AVG, COUNT)
- Date/time functions (MONTH, DAYNAME, HOUR)
- JOINs (for linking pizza, orders, and order_details tables)
- Subqueries and Aliases

---

## ▶️ How to Run

1. Import `pizza_sales_data.csv` into your SQL database (MySQL / PostgreSQL / SQLite).
2. Use the schema to create relevant tables (e.g., orders, order_details, pizzas, pizza_types).
3. Run `pizza_sales_analysis.sql` in your SQL editor (MySQL Workbench, DBeaver, etc.).
4. Analyze output or visualize insights (optional in Excel or Power BI).

---

## 🧾 Sample Query

```sql
-- Top 5 Pizzas by Revenue
SELECT pt.name AS pizza_name, SUM(od.quantity * p.price) AS total_revenue
FROM order_details od
JOIN pizzas p ON od.pizza_id = p.pizza_id
JOIN pizza_types pt ON p.pizza_type_id = pt.pizza_type_id
GROUP BY pt.name
ORDER BY total_revenue DESC
LIMIT 5;
