OnlineBookShop
## Пустые
```sql
CREATE TABLE Book
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






## Заполненные
```sql
CREATE TABLE Book
id INT PRIMARY KEY,
title VARCHAR(100),
publisher VARCHAR(100),
author VARCHAR(100),
warehouse_id INT,
FOREIGN KEY (warehouse_id) REFERENCES Warehouse(id)
);

INSERT INTO Book (id, title, publisher, author, warehouse_id) VALUES (1, 'Harry Potter and the Philosopher's Stone', 'Bloomsbury Publishing', 'J.K. Rowling', 1);
INSERT INTO Book (id, title, publisher, author, warehouse_id) VALUES (2, 'It', 'Viking Press', 'Stephen King', 2);
INSERT INTO Book (id, title, publisher, author, warehouse_id) VALUES (3, 'A Game of Thrones', 'Bantam Spectra', 'George R.R. Martin', 3);
INSERT INTO Book (id, title, publisher, author, warehouse_id) VALUES (4, 'The Da Vinci Code', 'Doubleday', 'Dan Brown', 4);
INSERT INTO Book (id, title, publisher, author, warehouse_id) VALUES (5, 'Murder on the Orient Express', 'Collins Crime Club', 'Agatha Christie', 5);


CREATE TABLE Publisher (
id INT PRIMARY KEY,
name VARCHAR(100)
);

INSERT INTO Publisher (id, name) VALUES (1, 'Penguin Books');
INSERT INTO Publisher (id, name) VALUES (2, 'HarperCollins');
INSERT INTO Publisher (id, name) VALUES (3, 'Random House');
INSERT INTO Publisher (id, name) VALUES (4, 'Simon & Schuster');
INSERT INTO Publisher (id, name) VALUES (5, 'Macmillan');

CREATE TABLE Author (
id INT PRIMARY KEY,
name VARCHAR(100)
);

INSERT INTO Author (id, name) VALUES (1, 'J.K. Rowling');
INSERT INTO Author (id, name) VALUES (2, 'Stephen King');
INSERT INTO Author (id, name) VALUES (3, 'George R.R. Martin');
INSERT INTO Author (id, name) VALUES (4, 'Dan Brown');
INSERT INTO Author (id, name) VALUES (5, 'Agatha Christie');

CREATE TABLE Warehouse (
id INT PRIMARY KEY,
location VARCHAR(100),
capacity INT
);

INSERT INTO Warehouse (id, location, capacity) VALUES (1, 'New York', 10000);
INSERT INTO Warehouse (id, location, capacity) VALUES (2, 'London', 8000);
INSERT INTO Warehouse (id, location, capacity) VALUES (3, 'Paris', 6000);
INSERT INTO Warehouse (id, location, capacity) VALUES (4, 'Tokyo', 5000);
INSERT INTO Warehouse (id, location, capacity) VALUES (5, 'Sydney', 4000);

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

INSERT INTO Orders (id, customer_id, order_date) VALUES (1, 1, '2022-01-10');
INSERT INTO Orders (id, customer_id, order_date) VALUES (2, 2, '2022-01-11');
INSERT INTO Orders (id, customer_id, order_date) VALUES (3, 3, '2022-01-12');
INSERT INTO Orders (id, customer_id, order_date) VALUES (4, 4, '2022-01-13');
INSERT INTO Orders (id, customer_id, order_date) VALUES (5, 5, '2022-01-14');


CREATE TABLE ShoppingBasket (
id INT PRIMARY KEY,
customer_id INT,
created_date DATE,
FOREIGN KEY (customer_id) REFERENCES Customer(id)
);

INSERT INTO ShoppingBasket (id, customer_id, created_date) VALUES (1, 1, '2022-01-01');
INSERT INTO ShoppingBasket (id, customer_id, created_date) VALUES (2, 2, '2022-01-02');
INSERT INTO ShoppingBasket (id, customer_id, created_date) VALUES (3, 3, '2022-01-03');
INSERT INTO ShoppingBasket (id, customer_id, created_date) VALUES (4, 4, '2022-01-04');
INSERT INTO ShoppingBasket (id, customer_id, created_date) VALUES (5, 5, '2022-01-05');

CREATE TABLE Customer (
id INT PRIMARY KEY,
name VARCHAR(100),
email VARCHAR(100)
);

INSERT INTO Customer (id, name, email) VALUES (1, 'John Doe', 'john.doe@example.com');
INSERT INTO Customer (id, name, email) VALUES (2, 'Jane Smith', 'jane.smith@example.com');
INSERT INTO Customer (id, name, email) VALUES (3, 'David Johnson', 'david.johnson@example.com');
INSERT INTO Customer (id, name, email) VALUES (4, 'Emily Brown', 'emily.brown@example.com');
INSERT INTO Customer (id, name, email) VALUES (5, 'Michael Wilson', 'michael.wilson@example.com');

CREATE TABLE Orders_details (
order_id INT,
book_id INT,
quantity INT,
PRIMARY KEY (order_id, book_id),
FOREIGN KEY (order_id) REFERENCES Orders(id),
FOREIGN KEY (book_id) REFERENCES Book(id)
);

INSERT INTO Orders_details (order_id, book_id, quantity) VALUES (1, 1, 2);
INSERT INTO Orders_details (order_id, book_id, quantity) VALUES (2, 2, 1);
INSERT INTO Orders_details (order_id, book_id, quantity) VALUES (3, 3, 3);
INSERT INTO Orders_details (order_id, book_id, quantity) VALUES (4, 4, 1);
INSERT INTO Orders_details (order_id, book_id, quantity) VALUES (5, 5, 2);
