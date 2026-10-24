**1. Customers**<br>
CREATE TABLE customers (<br>
    customer_id INT PRIMARY KEY AUTO_INCREMENT,<br>
    customer_name VARCHAR(100) NOT NULL,<br>
    city VARCHAR(50),<br>
    signup_date DATE<br>
);<br>

**2. Restaurants**<br>
CREATE TABLE restaurants (<br>
    restaurant_id INT PRIMARY KEY AUTO_INCREMENT,<br>
    restaurant_name VARCHAR(100) NOT NULL,<br>
    cuisine VARCHAR(50),<br>
    city VARCHAR(50),<br>
    opening_date DATE<br>
);<br>

**3. Menu items**<br>
CREATE TABLE menu_items (<br>
    item_id INT PRIMARY KEY AUTO_INCREMENT,<br>
    restaurant_id INT NOT NULL,<br>
    item_name VARCHAR(100) NOT NULL,<br>
    category VARCHAR(50),<br>
    price DECIMAL(10,2) NOT NULL,<br>
    is_available BOOLEAN DEFAULT TRUE,<br>
    CONSTRAINT chk_item_price CHECK (price >= 0),<br>
    FOREIGN KEY (restaurant_id)<br>
        REFERENCES restaurants(restaurant_id)<br>
);<br>

**4. Delivery partners**<br>
CREATE TABLE delivery_partners (<br>
    partner_id INT PRIMARY KEY AUTO_INCREMENT,<br>
    partner_name VARCHAR(100) NOT NULL,<br>
    city VARCHAR(50),<br>
    joining_date DATE<br>
);<br>

**5. Orders**<br>
CREATE TABLE orders (<br>
    order_id INT PRIMARY KEY AUTO_INCREMENT,<br>
    customer_id INT NOT NULL,<br>
    restaurant_id INT NOT NULL,<br>
    partner_id INT,<br>
    order_time DATETIME NOT NULL,<br>
    promised_delivery_time DATETIME,<br>
    actual_delivery_time DATETIME,<br>
    order_status VARCHAR(20) NOT NULL,<br>
    delivery_fee DECIMAL(10,2) DEFAULT 0,<br>
    cancellation_reason VARCHAR(255),<br>
    FOREIGN KEY (customer_id)<br>
        REFERENCES customers(customer_id),<br>
    FOREIGN KEY (restaurant_id)<br>
        REFERENCES restaurants(restaurant_id),<br>
    FOREIGN KEY (partner_id)<br>
        REFERENCES delivery_partners(partner_id),<br>
    CONSTRAINT chk_order_status CHECK (<br>
        order_status IN (<br>
            'Delivered',<br>
            'Cancelled',<br>
            'Preparing',<br>
            'Out for Delivery'<br>
        )<br>
    ),<br>
    CONSTRAINT chk_delivery_fee CHECK (delivery_fee >= 0)<br>
);<br>

**6. Order items**<br>
CREATE TABLE order_items (<br>
    order_item_id INT PRIMARY KEY AUTO_INCREMENT,<br>
    order_id INT NOT NULL,<br>
    item_id INT NOT NULL,<br>
    quantity INT NOT NULL,<br>
    unit_price DECIMAL(10,2) NOT NULL,<br>
    FOREIGN KEY (order_id)<br>
        REFERENCES orders(order_id),<br>
    FOREIGN KEY (item_id)<br>
        REFERENCES menu_items(item_id),<br>
    CONSTRAINT chk_quantity CHECK (quantity > 0),<br>
    CONSTRAINT chk_unit_price CHECK (unit_price >= 0)<br>
);<br>


