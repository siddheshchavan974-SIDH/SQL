**-- 1. Customers**
CREATE TABLE customers (
    customer_id INT PRIMARY KEY AUTO_INCREMENT,
    customer_name VARCHAR(100) NOT NULL,
    city VARCHAR(50),
    signup_date DATE
);

**-- 2. Restaurants**
CREATE TABLE restaurants (
    restaurant_id INT PRIMARY KEY AUTO_INCREMENT,
    restaurant_name VARCHAR(100) NOT NULL,
    cuisine VARCHAR(50),
    city VARCHAR(50),
    opening_date DATE
);
