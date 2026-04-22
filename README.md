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
- COUNT(ORDER_ID) counts all non-null order IDs
- Since each ORDER_ID represents one order, the result gives the total orders placed

➤ **Insight**:
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/2.png)
➤ **Explanation**:

➤ **Insight**:
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/3.png)
➤ **Explanation**:

➤ **Insight**:
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/4.png)
➤ **Explanation**:

➤ **Insight**:
![Pizza Sales Analysis](https://raw.githubusercontent.com/madhuri-shivhsharan/Pizza-Sales-Analysis-MySQL-Project-/refs/heads/assets/5.png)
➤ **Explanation**:

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
