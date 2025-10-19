CREATE DATABASE sales_insights;
USE sales_insights;

-- Create customers table
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    customer_name VARCHAR(100),
    region VARCHAR(50),
    country VARCHAR(50)
);

-- Create products table
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(100),
    category VARCHAR(50),
    price DECIMAL(10,2)
);

-- Create sales table
CREATE TABLE sales (
    sale_id INT PRIMARY KEY,
    customer_id INT,
    product_id INT,
    sale_date DATE,
    quantity INT,
    total_amount DECIMAL(10,2),
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);

CREATE DATABASE sales_insights;
USE sales_insights;

-- Create customers table
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    customer_name VARCHAR(100),
    region VARCHAR(50),
    country VARCHAR(50)
);

-- Create products table
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(100),
    category VARCHAR(50),
    price DECIMAL(10,2)
);

-- Create sales table
CREATE TABLE sales (
    sale_id INT PRIMARY KEY,
    customer_id INT,
    product_id INT,
    sale_date DATE,
    quantity INT,
    total_amount DECIMAL(10,2),
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);

-- Customers
INSERT INTO customers VALUES
(1, 'Amit Sharma', 'North', 'India'),
(2, 'John Doe', 'West', 'USA'),
(3, 'Sana Khan', 'East', 'India'),
(4, 'Mary Lee', 'South', 'Singapore');

-- Products
INSERT INTO products VALUES
(101, 'Laptop', 'Electronics', 55000),
(102, 'Smartphone', 'Electronics', 30000),
(103, 'Tablet', 'Electronics', 20000),
(104, 'Headphones', 'Accessories', 3000);

-- Sales
INSERT INTO sales VALUES
(1001, 1, 101, '2023-01-15', 1, 55000),
(1002, 2, 102, '2023-02-10', 2, 60000),
(1003, 3, 103, '2023-03-05', 1, 20000),
(1004, 4, 104, '2023-03-18', 3, 9000),
(1005, 1, 102, '2023-04-25', 1, 30000);


