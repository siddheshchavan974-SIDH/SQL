**1. Customers**
CREATE TABLE customers (<br>
    customer_id INT PRIMARY KEY AUTO_INCREMENT,<br>
    customer_name VARCHAR(100) NOT NULL,<br>
    city VARCHAR(50),<br>
    signup_date DATE<br>
);<br>

**-- 2. Restaurants**
CREATE TABLE restaurants (
    restaurant_id INT PRIMARY KEY AUTO_INCREMENT,
    restaurant_name VARCHAR(100) NOT NULL,
    cuisine VARCHAR(50),
    city VARCHAR(50),
    opening_date DATE
);
