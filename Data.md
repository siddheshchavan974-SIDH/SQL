**1. Customers**<br>
CREATE TABLE customers (<br>
    customer_id INT PRIMARY KEY AUTO_INCREMENT,<br>
    customer_name VARCHAR(100) NOT NULL,<br>
    city VARCHAR(50),<br>
    signup_date DATE<br>
);<br>

**-- 2. Restaurants**<br>
CREATE TABLE restaurants (<br>
    restaurant_id INT PRIMARY KEY AUTO_INCREMENT,<br>
    restaurant_name VARCHAR(100) NOT NULL,<br>
    cuisine VARCHAR(50),<br>
    city VARCHAR(50),<br>
    opening_date DATE<br>
);<br>
