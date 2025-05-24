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
