# Nova-Retail-Group-Database-Analysis

The Nova Retail Group project provides a comprehensive overview of the company’s sales performance during the 2023–2024 period. SQL was used to analyze and communicate the findings, while Databricks was utilized to execute and consolidate all queries.

The analysis focused on key areas, including sales, products, customers, and customer feedback, to evaluate the company’s overall performance and identify key business insights.

Nova Retail Group demonstrated strong financial performance, achieving an Average Order Value (AOV) of R6,650.00 and total revenue of R6,650,554 during the 2023–2024 period. The company also achieved a strong net profit margin of 35.34%, generating approximately R2.35 million in profit from 1,000 orders placed by 431 customers.

On average, each customer placed 2.32 orders during the period, indicating a healthy level of customer engagement and repeat purchasing. Overall, these results demonstrate that Nova Retail Group maintained a strong financial position while achieving positive customer and sales performance.

<img width="790" height="475" alt="image" src="https://github.com/user-attachments/assets/17fb0dc1-9e20-46fc-a612-14d58e2bd72b" />

TOP INSIGHTS
#1: Strong Year-over-Year Order Growth

The number of orders increased significantly from 2023 to 2024 reflecting high demand for the products.

SELECT YEAR(OrderDate) AS Year,
       COUNT(DISTINCT OrderID) AS num_orders
FROM sales
WHERE YEAR(OrderDate) IN (2023, 2024)
GROUP BY Year
ORDER BY Year ASC;

#2: High Customer Repeat Rate

A high number of purchases demonstrate positive customer engagement and satisfaction 

SELECT CustomerID,
       COUNT(DISTINCT OrderID) AS num_orders
FROM sales
GROUP BY CustomerID
HAVING COUNT(DISTINCT OrderID) > 1;

#3: Consistent Profitability

The average profit per order demonstrates that Nova Retail Group maintained healthy profitability while processing a growing number of orders.

SELECT AVG(Profit) AS avg_profit_per_order
FROM sales
WHERE YEAR(OrderDate) IN (2023, 2024);

RECOMMENDATIONS:

-Increase Marketing – Build strong growth in order volumes by increasing marketing initiatives and channels that have demonstrated effective customer acquisition.

-Strengthen Customer Loyalty – Introduce loyalty programmes, promotions, and personalized offers to encourage repeat purchases and improve long-term customer retention.

-Monitor and Optimize Profit Margins – Review pricing strategies, operating costs, and profit margins regularly, on a quarterly basis, to ensure continued profitability.

-Expand Upselling and Cross-Selling Opportunities – Leverage the strong Average Order Value (AOV) by offering complementary products, upgrades, and targeted recommendations to existing customers.

-Enhance Data-Driven – Establish regular monthly monitoring of sales performance, customer purchasing behavior, and profitability to identify trends and support informed business decisions.
