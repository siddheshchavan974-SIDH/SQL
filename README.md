# Food Delivery & Restaurant Performance Analytics -- (Swiggy)

### Project Objective

The objective of this project is to analyze food delivery operations using MySQL to evaluate restaurant performance, customer ordering behavior, revenue trends, delivery efficiency, and payment patterns. By using SQL queries, joins, aggregations, subqueries, and window functions, the project aims to identify top-performing restaurants, popular food items, high-value customers, order cancellation trends, and delivery performance. The insights will help businesses make data-driven decisions to improve customer satisfaction, optimize restaurant operations, increase revenue, and enhance overall delivery efficiency.

### Tools & Technologies Used

**MySQL**: For database creation, data storage, data manipulation, and business analysis using SQL queries.<br>
**SQL**: For filtering, joining, aggregating, and analyzing food delivery data.<br>
**MySQL Workbench**: For writing and executing queries, managing database tables, and validating results.

### Database Design

**1. Customers Table**<br>
The Customers table stores information about customers who use the food delivery platform. It contains customer details such as customer ID, customer name, city, contact information, and registration date, depending on the fields defined in the database.

**2. Restaurants Table**<br>
The Restaurants table contains information about restaurants registered on the platform. It includes details such as restaurant ID, restaurant name, city, cuisine type, and other restaurant-related attributes available in the database.

**3. Menu_Items Table**<br>
The Menu_Items table stores information about food items offered by restaurants. It includes menu item ID, restaurant ID, item name, category, and item price.

**4. Delivery_Partners Table**<br>
The Delivery_Partners table stores information about delivery personnel working with the platform. It may include partner ID, partner name, city, and joining date.

**5. Orders Table**<br>
The Orders table records customer orders placed through the platform. It includes order ID, customer ID, restaurant ID, delivery partner ID, order date, order status, and delivery fee, depending on the database schema.

**6. Order_Items Table**<br>
The Order_Items table stores details of the individual food items included in each order. It contains order ID, item ID, quantity, and unit price.

**7. Payments Table**<br>
The Payments table stores payment-related information for customer orders. It may contain payment ID, order ID, payment method, payment amount, and payment status.





### Business problem

A food delivery company is experiencing inconsistent delivery times, customer cancellations, and differences in restaurant performance. Management wants to understand what is happening and identify opportunities to improve customer satisfaction and business revenue.
Our Goal: Use SQL to analyse restaurant sales, delivery efficiency, customer behaviour, order cancellations, and customer ratings.

### What we will analyse

1.Restaurant performance<br>
Top restaurants by revenue, order volume, and average rating.<br>
2.Delivery performance<br>
Average delivery time, late deliveries, and delivery-zone performance.<br>
3.Customer behavior<br>
Repeat customers, high-value customers, and ordering patterns.<br>
4.Revenue and cancellations<br>
Order revenue, cancellation rate, payment methods, and peak ordering hours.<br>

### Understand the business metrics

|            **Metric**            |            **Business meaning**            |            **Formula**            |
|----------------------------------|--------------------------------------------|-----------------------------------|
|        Total Orders              |            Number of orders placed         |        COUNT(Order_ID)            |
|        Delivered Orders          |        Orders successfully delivered       |    COUNT(Order_ID) WHERE Order_Status = 'Delivered'|
|  Total Revenue                   |Value of food sold through delivered orders |SUM(Quantity * Unit_Price) for delivered orders|
|Average Order Value (AOV)         |Food revenue divided by delivered orders    |Total Revenue / Delivered Orders    |
|Cancellation Rate                 |Cancelled orders divided by all orders      |(Cancelled Orders / Total Orders) * 100|
|Average Delivery Time             |Average time from order placement to delivery|AVG(Delivery_Time - Order_Time) for delivered orders|
|Late Delivery Rate                |Delivered orders arriving after the promised time|(Late Delivered Orders / Total Delivered Orders) * 100|
|Repeat Customer Rate              |Customers who placed more than one order    |(Customers with More Than One Order / Total Customers) * 100|

**Insert realistic sample data into your food_delivery_db database**

