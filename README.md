# SQL Queries for Superstore Sales Analysis

This file contains SQL queries designed to extract insights from the Superstore dataset, including:

- Total profit by region
- Revenue by segment
- Average profit by category
- Top 5 products by sales
- Monthly sales trends
- Profitability by region and segment
- Top 3 categories by quantity sold

These queries demonstrate the ability to work with SQL for data analysis, generate business insights, and support decision-making processes.

The dataset used is the `Superstore_Orders_Sample.csv` file, which contains information on orders, customers, products, sales, and profit for a fictional Superstore.

## How to Use

1. Import the Superstore dataset into your SQL environment (e.g., SQLite, MySQL, or PostgreSQL).
2. Run the SQL queries to generate insights and perform exploratory data analysis.

Happy analyzing!

# -SQL_Queries_Superstore.sql
-- 1. Total Profit by Region
SELECT Region, SUM(Profit) AS Total_Profit
FROM Superstore_Orders_Sample
GROUP BY Region
ORDER BY Total_Profit DESC;

-- 2. Total Revenue by Segment
SELECT Segment, SUM(Sales) AS Total_Sales
FROM Superstore_Orders_Sample
GROUP BY Segment
ORDER BY Total_Sales DESC;

-- 3. Average Profit by Category
SELECT Category, AVG(Profit) AS Average_Profit
FROM Superstore_Orders_Sample
GROUP BY Category
ORDER BY Average_Profit DESC;

-- 4. Top 5 Products by Sales
SELECT Product_Name, SUM(Sales) AS Total_Sales
FROM Superstore_Orders_Sample
GROUP BY Product_Name
ORDER BY Total_Sales DESC
LIMIT 5;

-- 5. Monthly Sales Trend
SELECT STRFTIME('%Y-%m', Order_Date) AS Month, SUM(Sales) AS Total_Sales
FROM Superstore_Orders_Sample
GROUP BY Month
ORDER BY Month;

-- 6. Profit by Region and Segment
SELECT Region, Segment, SUM(Profit) AS Total_Profit
FROM Superstore_Orders_Sample
GROUP BY Region, Segment
ORDER BY Region, Total_Profit DESC;

-- 7. Top 3 Categories by Quantity Sold
SELECT Category, SUM(Quantity) AS Total_Quantity
FROM Superstore_Orders_Sample
GROUP BY Category
ORDER BY Total_Quantity DESC
LIMIT 3;
