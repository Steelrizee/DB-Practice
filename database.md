OnlineBookShop
## Пустые
```sql
— Create the database
CREATE DATABASE OnlineBookShop;

— Use the database
USE OnlineBookShop;

— Create the tables
CREATE TABLE Book (
BookID INT PRIMARY KEY,
BookName VARCHAR(100),
Publisher VARCHAR(100),
Author VARCHAR(100),
WarehouseID INT,
FOREIGN KEY (WarehouseID) REFERENCES Warehouse(WarehouseID)
);

CREATE TABLE Publisher (
PublisherID INT PRIMARY KEY,
PublisherName VARCHAR(100)
);

CREATE TABLE Author (
AuthorID INT PRIMARY KEY,
AuthorName VARCHAR(100)
);

CREATE TABLE Warehouse (
WarehouseID INT PRIMARY KEY,
WarehouseName VARCHAR(100)
);

CREATE TABLE ShoppingBasket_Book (
BasketID INT,
BookID INT,
FOREIGN KEY (BasketID) REFERENCES ShoppingBasket(BasketID),
FOREIGN KEY (BookID) REFERENCES Book(BookID)
);

CREATE TABLE Orders (
OrderID INT PRIMARY KEY,
OrderDate DATE,
CustomerID INT,
FOREIGN KEY (CustomerID) REFERENCES Customer(CustomerID)
);

CREATE TABLE ShoppingBasket (
BasketID INT PRIMARY KEY,
CustomerID INT,
FOREIGN KEY (CustomerID) REFERENCES Customer(CustomerID)
);

CREATE TABLE Customer (
CustomerID INT PRIMARY KEY,
CustomerName VARCHAR(100),
Address VARCHAR(100),
Phone VARCHAR(20)
);

CREATE TABLE Order_Details (
OrderID INT,
BookID INT,
Quantity INT,
FOREIGN KEY (OrderID) REFERENCES Orders(OrderID),
FOREIGN KEY (BookID) REFERENCES Book(BookID)
Более крутой ниггер
CREATE DATABASE online_book_shop;

USE online_book_shop;

CREATE TABLE Book (
id INT PRIMARY KEY,
title VARCHAR(100),
publisher VARCHAR(100),
author VARCHAR(100),
warehouse_id INT,
FOREIGN KEY (warehouse_id) REFERENCES Warehouse(id)
);

CREATE TABLE Publisher (
id INT PRIMARY KEY,
name VARCHAR(100)
);

CREATE TABLE Author (
id INT PRIMARY KEY,
name VARCHAR(100)
);

CREATE TABLE Warehouse (
id INT PRIMARY KEY,
location VARCHAR(100),
capacity INT
);

CREATE TABLE ShoppingBasket_Book (
shopping_basket_id INT,
book_id INT,
PRIMARY KEY (shopping_basket_id, book_id),
FOREIGN KEY (shopping_basket_id) REFERENCES ShoppingBasket(id),
FOREIGN KEY (book_id) REFERENCES Book(id)
);

CREATE TABLE Orders (
id INT PRIMARY KEY,
customer_id INT,
order_date DATE,
FOREIGN KEY (customer_id) REFERENCES Customer(id)
);

CREATE TABLE ShoppingBasket (
id INT PRIMARY KEY,
customer_id INT,
created_date DATE,
FOREIGN KEY (customer_id) REFERENCES Customer(id)
);

CREATE TABLE Customer (
id INT PRIMARY KEY,
name VARCHAR(100),
email VARCHAR(100)
);

CREATE TABLE Orders_details (
order_id INT,
book_id INT,
quantity INT,
PRIMARY KEY (order_id, book_id),
FOREIGN KEY (order_id) REFERENCES Orders(id),
FOREIGN KEY (book_id) REFERENCES Book(id)
);
