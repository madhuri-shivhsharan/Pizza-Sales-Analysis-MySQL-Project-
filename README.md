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
 It counts orders for each size and returns the size with the highest demand.

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
  It finds which pizzas are sold the most in terms of total quantity.

➤ **Insight**:
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/6.png)
➤ **Explanation**:

➤ **Insight**:
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/7.png)
➤ **Explanation**:

➤ **Insight**:
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/8.png)
➤ **Explanation**:

➤ **Insight**:
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/9.png)
➤ **Explanation**:

➤ **Insight**:
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/10.png)
➤ **Explanation**:

➤ **Insight**:
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/11.png)
➤ **Explanation**:


## 🚀 Conclusion
I found that revenue is highly concentrated in a few pizza types. Medium and large pizzas dominate sales, and evening hours are peak order times. Also, top 3 pizzas in each category generate most revenue, which suggests focusing on high-performing items can significantly improve business outcomes.

---

## 🔗 Author
**Your Name**
