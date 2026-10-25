# Food Delivery & Restaurant Performance Analytics -- (Swiggy)

### Project Objective

The objective of this project is to analyze food delivery operations using MySQL to evaluate restaurant performance, customer ordering behavior, revenue trends, delivery efficiency, and payment patterns. By using SQL queries, joins, aggregations, subqueries, and window functions, the project aims to identify top-performing restaurants, popular food items, high-value customers, order cancellation trends, and delivery performance. The insights will help businesses make data-driven decisions to improve customer satisfaction, optimize restaurant operations, increase revenue, and enhance overall delivery efficiency.

### Tools & Technologies Used

**MySQL**: For database creation, data storage, data manipulation, and business analysis using SQL queries.<br>
**SQL**: For filtering, joining, aggregating, and analyzing food delivery data.<br>
**MySQL Workbench**: For writing and executing queries, managing database tables, and validating results.

### Database Design [![Database Design](https://img.shields.io/badge/Database-Design-blue?style=for-the-badge)](YOUR_GITHUB_FILE_URL)<br>
The project uses a relational database named food_delivery_db, consisting of seven tables to manage and analyze food delivery operations. Each table stores specific information about customers, restaurants, menu items, delivery partners, orders, order items, and payments. Primary keys and foreign keys establish relationships between tables and maintain data integrity.

**1. Customers Table**<br>
The Customers table stores information about customers who use the food delivery platform. It contains customer details such as customer ID, customer name, city, and registration/signup_date depending on the fields defined in the database.

**2. Restaurants Table**<br>
The Restaurants table contains information about restaurants registered on the platform. It includes details such as restaurant ID, restaurant name, city, cuisine, opening_date DATE and other restaurant-related attributes available in the database.

**3. Menu_Items Table**<br>
The Menu_Items table stores information about food items offered by restaurants. It includes menu item ID, restaurant ID, item name, category, item price and Availability.

**4. Delivery_Partners Table**<br>
The Delivery_Partners table stores information about delivery personnel working with the platform. It includes partner ID, partner name, city, and joining date.

**5. Orders Table**<br>
The Orders table records customer orders placed through the platform. It includes order ID, customer ID, restaurant ID, delivery partner ID, order date, order status, delivery fee, and cancellation_reason depending on the database schema.

**6. Order_Items Table**<br>
The Order_Items table stores details of the individual food items included in each order. It contains order item ID, order ID, item ID, quantity, and unit price.

**7. Payments Table**<br>
The Payments table stores payment-related information for customer orders. It contains payment ID, order ID, payment method, payment amount, and payment status.

### Database Relationships

One customer can place multiple orders.<br>
One restaurant can receive multiple orders and offer multiple menu items.<br>
One order can contain multiple order items.<br>
One delivery partner can deliver multiple orders.<br>
Each payment record is linked to an order.<br>

### Business Questions to Be Answered

The project aims to answer important business questions related to customer behavior, restaurant performance, sales revenue, order management, and delivery operations. SQL queries will be used to extract meaningful insights from the database and support data-driven decision-making.

**A. Customer Analysis** <br>
Who are the top 10 customers based on total spending?<br>
Which cities have the highest number of customers?<br>
How many orders does each customer place?<br>
Who are the customers with the highest number of orders?<br>
What is the average spending per customer?<br>

**B. Restaurant Performance Analysis**<br>
Which are the top 10 restaurants based on total sales revenue?<br>
Which restaurants receive the highest number of orders?<br>
Which restaurants have the highest order cancellation rates?<br>
Which cities have the highest restaurant sales?<br>
Which restaurants generate the highest average order value?<br>

C. Sales and Revenue Analysis<br>
What is the total revenue generated from food orders?<br>
What are the monthly and quarterly sales trends?<br>
Which month generates the highest sales revenue?<br>
What is the average order value (AOV)?<br>
What percentage of orders are successfully delivered versus cancelled?<br>

D. Food Item Analysis<br>
Which are the top 10 best-selling food items by quantity?<br>
Which food categories generate the highest revenue?<br>
Which menu items contribute the most to total sales?<br>
What is the average price of menu items across restaurants?<br>
Which restaurants offer the highest number of menu items?<br>

E. Order and Delivery Analysis<br>
What is the total number of orders placed?<br>
How many orders are delivered, cancelled, or still in progress?<br>
Which delivery partners are associated with the highest number of orders?<br>
Which cities have the highest order volumes?<br>
What is the distribution of orders by status?<br>

F. Payment Analysis<br>
Which payment methods are used most frequently?<br>
What is the total value of successful payments?<br>
How many payments have failed?<br>
What is the average payment amount for each payment method?<br>
Which payment methods account for the highest transaction value?<br>

### Key Insights and Business Recommendations

**Key Insights**<br>
1. Customer Behavior: Identify high-value customers, repeat customers, and customers who have registered but never placed an order.<br>
2. Restaurant Performance: Evaluate restaurants based on order volume, delivered food sales, and cancellation rates to identify strong performers and areas requiring improvement.<br>
3. Revenue Trends: Analyze monthly and city-wise food sales to identify growth patterns, seasonal changes, and high-performing markets.<br>
4. Food Item Preferences: Identify best-selling food items and popular food categories to understand customer preferences and support menu optimization.<br>
5. Order Management: Examine order status distribution and cancellation rates to identify potential issues affecting order fulfillment.<br>
6. Delivery Operations: Analyze delivery partner workloads and order distribution to understand operational demand and resource allocation.<br>
7. Payment Trends: Evaluate payment methods, successful transaction amounts, and failed payments to understand payment preferences and potential transaction issues.<br>

**Business Recommendations**<br>
1. Improve Customer Retention: Introduce loyalty rewards, personalized promotions, and targeted offers for repeat and high-value customers.<br>
2. Support Restaurant Growth: Work with restaurants that demonstrate strong performance and investigate the causes of low sales or high cancellation rates.<br>
3. Optimize Revenue Generation: Use monthly and city-wise revenue trends to plan marketing campaigns and identify opportunities for expansion.<br>
4. Optimize Menu Strategy: Promote popular food items, review underperforming menu categories, and help restaurant partners make informed menu decisions.<br>
5. Reduce Order Cancellations: Investigate cancellation reasons, food availability, preparation delays, and order-handling processes before implementing corrective measures.<br>
6. Improve Delivery Operations: Review delivery partner workloads and, when delivery-time data is available, identify delays and opportunities to improve delivery efficiency.<br>
7. Strengthen Payment Monitoring: Monitor failed transactions, investigate payment discrepancies, and use successful transaction data to understand customer payment preferences.<br>

### Understand the business Metrics/KPI used

|            **Metric**            |            **Business meaning**            |            **Formula**            |
|----------------------------------|--------------------------------------------|-----------------------------------|
|Total Orders                      |Number of orders placed                     |COUNT(Order_ID)            |
|Delivered Orders                  |Orders successfully delivered               |COUNT(Order_ID) WHERE Order_Status = 'Delivered'|
|Total Revenue                     |Value of food sold through delivered orders |SUM(Quantity * Unit_Price) for delivered orders|
|Average Order Value (AOV)         |Food revenue divided by delivered orders    |Total Revenue / Delivered Orders    |
|Cancellation Rate                 |Cancelled orders divided by all orders      |(Cancelled Orders / Total Orders) * 100|
|Average Delivery Time             |Average time from order placement to delivery|AVG(Delivery_Time - Order_Time) for delivered orders|
|Late Delivery Rate                |Delivered orders arriving after the promised time|(Late Delivered Orders / Total Delivered Orders) * 100|
|Repeat Customer Rate              |Customers who placed more than one order    |(Customers with More Than One Order / Total Customers) * 100|

### Project Conclusion

The Food Delivery & Restaurant Performance Analytics project uses MySQL to analyze customer behavior, restaurant performance, revenue trends, food preferences, order cancellations, delivery operations, and payment transactions. By applying SQL techniques such as joins, aggregate functions, subqueries, CTEs, views, and window functions, the project transforms raw operational data into meaningful business insights and performance indicators.<br>
From a business perspective, the analysis helps identify high-value customers, evaluate restaurant performance, track revenue trends, understand popular food items, and investigate operational challenges. These insights can support better customer retention strategies, improved restaurant partnerships, more efficient operations, and informed business decisions. Overall, the project demonstrates how SQL-based data analysis can help a food delivery business monitor performance, identify improvement opportunities, and support sustainable growth.

# SQL

# 🍔 Food Delivery & Restaurant Performance Analytics Project

````text
FOOD DELIVERY & RESTAURANT ANALYTICS PROJECT
                    │
                    ▼
               SQL DATABASE
                    │
                    ├── Customers
                    ├── Restaurants
                    ├── Menu Items
                    ├── Delivery Partners
                    ├── Orders
                    ├── Order Items
                    └── Payments
                    │
                    ▼
                SQL ANALYSIS
                    │
                    ├── SELECT & WHERE
                    ├── GROUP BY & HAVING
                    ├── JOINS
                    ├── AGGREGATE FUNCTIONS
                    ├── SUBQUERIES
                    ├── CTEs
                    ├── WINDOW FUNCTIONS
                    └── VIEWS
                    │
                    ▼
              BUSINESS ANALYSIS
                    │
                    ├── Customer Behavior
                    ├── Restaurant Performance
                    ├── Revenue Analysis
                    ├── Popular Food Items
                    ├── Order Cancellation Analysis
                    ├── Delivery Operations
                    ├── Payment Analysis
                    └── Business KPIs & Insights
                    │
                    ▼
              BUSINESS VALUE
                    │
                    ├── Improve Customer Retention
                    ├── Monitor Restaurant Performance
                    ├── Identify Revenue Opportunities
                    ├── Reduce Order Cancellations
                    ├── Optimize Delivery Operations
                    └── Support Data-Driven Decisions
                    │
                    ▼
                  POWER BI
                    │
                    ├── MySQL Data Connection
                    ├── Data Cleaning
                    ├── Data Modeling
                    ├── Table Relationships
                    ├── DAX Measures
                    ├── KPI Cards
                    ├── Charts & Visualizations
                    └── Interactive Dashboard
