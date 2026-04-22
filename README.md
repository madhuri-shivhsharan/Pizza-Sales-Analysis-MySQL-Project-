# Pizza-Sales-Analysis(MySQL)
This project analyzes pizza sales data using MySQL to uncover business insights such as revenue trends, customer preferences, and ordering patterns.  The goal is to practice SQL skills like joins, aggregations, subqueries, and window functions while solving real-world business questions.

## 🎯 Objectives of the Project:
- Track total number of orders.
- Calculate total revenue generated.
- Identify top-selling pizzas.
- Analyze customer ordering behavior.
- Understand category and size preferences.
- Study sales trends over time.

## 🗂️ Dataset Includes 4 Tables:
- Orders,Order_Details,Pizzas,Pizza_Types.
- In Orders table contains Order id,Customer id,Order date,amount.
- In Orders_details table conatains Order_details_id,Order_id,Pizza_id,Quantity.
- In Pizzas table contains Pizza_id,Pizza_type_id,Size,Price.
- In Pizzas_types table conatins Pizza_type_id,Name,Category,Ingredients.
## 📊 Key Analysis Performed
### 🔹 Basic Analysis
- Total number of orders placed
- Total revenue generated
- Highest priced pizza
- Most common pizza size
- Top 5 most ordered pizzas
### 🔹 Intermediate Analysis
- Category-wise sales distribution
- Orders distribution by hour
- Average pizzas ordered per day 
## 📈 SQL Queries & Insights:
➤ **Insight**:The total order count highlights customer purchasing activity and can be used to identify business growth patterns when analyzed over time. It also helps in correlating order volume with revenue and operational capacity.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/1.png)
➤ **Explanation**:This query counts the total number of orders recorded in the ORDERS table using ORDER_ID.
- COUNT(ORDER_ID) counts all non-null order IDs.
- Since each ORDER_ID represents one order, the result gives the total orders placed.

  
➤ **Insight**:The total revenue metric reflects the overall financial performance of pizza sales by combining order volume with pricing. It provides a clear view of how much income the business generates from its core product offerings.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/2.png)
➤ **Explanation**:This query calculates the total revenue generated from pizza sales.
- ORDER_DETAILS (OD) → contains quantity of pizzas ordered.
- PIZZAS (P) → contains price of each pizza.
- JOIN → connects both tables using PIZZA_ID to match quantity with price.
- OD.QUANTITY * P.PRICE → calculates revenue per order line.
- SUM(...) → adds all values to get total revenue.


➤ **Insight**:The highest priced pizza represents the premium offering in the menu, highlighting the top-end pricing strategy of the business.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/3.png)
➤ **Explanation**:This analysis is done in two steps:
1. Find the maximum price.
- MAX(PRICE) returns the highest pizza price in the dataset.
2. Retrieve full details.
- Join PIZZAS with PIZZA_TYPES to get the pizza name.
- Sort prices in descending order (ORDER BY P.PRICE DESC).
- LIMIT 1 returns the most expensive pizza with:Name,Size,Price.


➤ **Insight**:The most commonly ordered pizza size reflects customer preference and demand patterns, helping the business understand which portion size is most popular.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/4.png)
➤ **Explanation**:This query identifies the most frequently ordered pizza size.
- JOIN → connects order details with pizza info to get size.
- GROUP BY P.SIZE → groups orders by each pizza size.
- COUNT(*) → counts how many times each size was ordered.
- ORDER BY TOTAL_ORDERS DESC → sorts sizes from most to least ordered.
- LIMIT 1 → returns the top (most ordered) size.
- It counts orders for each size and returns the size with the highest demand.

➤ **Insight**:The top 5 most ordered pizza types highlight the most popular products, reflecting customer preferences and demand trends.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/5.png)
➤ **Explanation**:This query identifies the top 5 most ordered pizza types based on total quantity sold.
- ORDER_DETAILS → contains quantity of each pizza ordered.
- PIZZAS → links pizza ID to pizza type.
- PIZZA_TYPES → contains pizza names.
- JOIN → combines all tables to get full details.
- SUM(OD.QUANTITY) → calculates total quantity sold per pizza type.
- GROUP BY PT.NAME → groups results by pizza type.
- ORDER BY TOTAL_QUANTITY DESC → sorts from highest to lowest demand.
- LIMIT 5 → returns top 5 pizza types.
- It finds which pizzas are sold the most in terms of total quantity.

➤ **Insight**:The category-wise quantity analysis highlights which pizza segments are most popular among customers, providing a clear view of demand distribution across categories.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/6.png)
➤ **Explanation**:This query calculates the total quantity of pizzas ordered for each category.
- ORDER_DETAILS → contains quantity of pizzas ordered.
- PIZZAS → connects each order to a pizza type.
- PIZZA_TYPES → provides category (e.g., Classic, Veggie, Chicken, etc.)
- JOIN → merges all tables to get category-level data.
- SUM(OD.QUANTITY) → calculates total pizzas sold per category.
- GROUP BY PT.CATEGORY → groups results by category
- ORDER BY TOTAL_QUANTITY DESC → ranks categories from highest to lowest demand.
- It shows which category of pizzas is ordered the most.

➤ **Insight**:The hourly distribution of orders reveals peak and off-peak business hours, helping to understand customer ordering patterns throughout the day.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/7.png)
➤ **Explanation**:This query analyzes how orders are distributed across different hours of the day.
- HOUR(TIME) → extracts the hour (0–23) from the order time.
- COUNT(ORDER_ID) → counts number of orders in each hour.
- GROUP BY ORDER_HOUR → groups orders by each hour.
- ORDER BY ORDER_HOUR → displays results in chronological order.
- It shows how many orders are placed in each hour of the day.



➤ **Insight**:The category-wise distribution highlights how the menu is structured across different pizza segments, showing which categories have the highest variety.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/8.png)
➤ **Explanation**:This query calculates the number of pizza variants available in each category.
- PIZZAS → contains individual pizza entries (size variations, etc.)
- PIZZA_TYPES → contains category information (Classic, Veggie, Chicken, etc.)
- JOIN → connects pizzas with their categories.
- COUNT(P.PIZZA_ID) → counts how many pizzas belong to each category.
- GROUP BY PT.CATEGORY → groups results by category.
- ORDER BY TOTAL_PIZZAS DESC → ranks categories by number of pizzas.
- It shows how many different pizzas are offered in each category.

➤ **Insight**:The average number of pizzas ordered per day provides a baseline measure of daily sales volume, helping to understand overall business performance.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/9.png)
➤ **Explanation**:This query calculates the average number of pizzas ordered per day using a subquery.
**Step 1: Inner Query (Subquery)**
- Joins ORDERS and ORDER_DETAILS.
- Groups data by DATE.
- Calculates total pizzas ordered each day using SUM(OD.QUANTITY.
 **Result: Daily total pizzas → DAILY_PIZZAS**
**Step 2: Outer Query**
- Applies AVG() on daily totals.
- Returns the average pizzas ordered per day.
- First calculate pizzas ordered each day, then take the average of those daily totals.
  

➤ **Insight**:The top 3 pizza types by revenue highlight the highest earning products, combining both popularity and pricing impact.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/10.png)
➤ **Explanation**:This query identifies the top 3 pizza types that generate the highest revenue.
- ORDER_DETAILS → contains quantity ordered.
- PIZZAS → contains price of each pizza.
- PIZZA_TYPES → contains pizza names.
- JOIN → combines all tables to link quantity, price, and name.
- OD.QUANTITY * P.PRICE → calculates revenue per order line.
- SUM(...) → total revenue per pizza type.
- ROUND(...,2) → formats revenue to 2 decimal places.
- GROUP BY PT.NAME → groups data by pizza type.
- ORDER BY TOTAL_REVENUE DESC → ranks highest earning pizzas.
- LIMIT 3 → returns top 3.
- It finds which pizzas make the most money, not just the most orders.

➤ **Insight**:This analysis highlights the contribution of each pizza type to total revenue, helping identify top-performing products that drive business income.
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/11.png)
➤ **Explanation**:This query calculates both revenue and its percentage contribution for each pizza type.
- OD.QUANTITY * P.PRICE → revenue generated per order.
- SUM(...) → total revenue for each pizza type.
- Subquery → calculates overall total revenue of all pizzas.
- Division → (pizza revenue / total revenue).
- * 100 → converts into percentage contribution.
- ROUND(...,2) → formats values to 2 decimal places.
- GROUP BY PT.NAME → groups data by pizza type.
- ORDER BY PERCENTAGE_CONTRIBUTION DESC → ranks pizzas from highest to lowest contributors.
- It shows how much money each pizza earns and what share it contributes to total revenue.


## 🚀 Conclusion
I found that revenue is highly concentrated in a few pizza types. Medium and large pizzas dominate sales, and evening hours are peak order times. Also, top 3 pizzas in each category generate most revenue, which suggests focusing on high-performing items can significantly improve business outcomes.


