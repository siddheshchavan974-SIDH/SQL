# SQL

Food Delivery & Restaurant Performance -- ((Swiggy)


Business problem
A food delivery company is experiencing inconsistent delivery times, customer cancellations, and differences in restaurant performance. Management wants to understand what is happening and identify opportunities to improve customer satisfaction and business revenue.
Our objective: Use SQL to analyse restaurant sales, delivery efficiency, customer behaviour, order cancellations, and customer ratings.

What we will analyse

1.Restaurant performance
Top restaurants by revenue, order volume, and average rating.
2.Delivery performance
Average delivery time, late deliveries, and delivery-zone performance.
3.Customer behavior
Repeat customers, high-value customers, and ordering patterns.
4.Revenue and cancellations
Order revenue, cancellation rate, payment methods, and peak ordering hours.

**Understand the business metrics**

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

