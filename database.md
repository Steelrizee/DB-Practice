## OnlineBookShop Diagram
![image](https://github.com/Steelrizee/DB-Practice/assets/144115438/9952b07e-d875-45cc-99ff-a2f0c457f294)




## Пустые
```sql
CREATE TABLE Book(
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
```
### Заполненные
```sql
CREATE TABLE Book(
id INT PRIMARY KEY,
title VARCHAR(100),
publisher VARCHAR(100),
author VARCHAR(100),
warehouse_id INT,
FOREIGN KEY (warehouse_id) REFERENCES Warehouse(id)
);

INSERT INTO Book (id, title, publisher, author, warehouse_id) VALUES (1, 'Harry Potter and the Philosophers Stone', 'Bloomsbury Publishing', 'J.K. Rowling', 1);
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

INSERT INTO ShoppingBasket_Book (shopping_basket_id, book_id) VALUES (1, 1);
INSERT INTO ShoppingBasket_Book (shopping_basket_id, book_id) VALUES (2, 2);
INSERT INTO ShoppingBasket_Book (shopping_basket_id, book_id) VALUES (3, 3);
INSERT INTO ShoppingBasket_Book (shopping_basket_id, book_id) VALUES (4, 4);
INSERT INTO ShoppingBasket_Book (shopping_basket_id, book_id) VALUES (5, 5);

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

INSERT INTO Orders_details (order_id, book_id, quantity) VALUES (2, 2, 1);
INSERT INTO Orders_details (order_id, book_id, quantity) VALUES (3, 3, 3);
INSERT INTO Orders_details (order_id, book_id, quantity) VALUES (4, 4, 1);
INSERT INTO Orders_details (order_id, book_id, quantity) VALUES (5, 5, 2);
```
## Views
```sql
1.For Book table:
CREATE VIEW BookView AS
SELECT b.id, b.title, p.name as publisher, a.name as author, w.location as warehouse_location
FROM Book b
INNER JOIN Publisher p ON b.publisher = p.id
INNER JOIN Author a ON b.author = a.id
INNER JOIN Warehouse w ON b.warehouse_id = w.id;

2.For Publisher table:
CREATE VIEW PublisherView AS
SELECT id, name
FROM Publisher;

3.For Author table:
CREATE VIEW AuthorView AS
SELECT id, name
FROM Author;

4.For Warehouse table:
CREATE VIEW WarehouseView AS
SELECT id, location, capacity
FROM Warehouse;

5.For ShoppingBasket_Book table:
CREATE VIEW ShoppingBasket_BookView AS
SELECT sb.shopping_basket_id, b.title, b.author
FROM ShoppingBasket_Book sb
INNER JOIN Book b ON sb.book_id = b.id;

6.For Orders table:
CREATE VIEW OrdersView AS
SELECT o.id, c.name as customer_name, o.order_date
FROM Orders o
INNER JOIN Customer c ON o.customer_id = c.id;

7.For ShoppingBasket table:
CREATE VIEW ShoppingBasketView AS
SELECT sb.id, c.name as customer_name, sb.created_date
FROM ShoppingBasket sb
INNER JOIN Customer c ON sb.customer_id = c.id;

8.For Customer table:
CREATE VIEW CustomerView AS
SELECT id, name, email
FROM Customer;

9.For Orders_details table:
CREATE VIEW Orders_detailsView AS
SELECT o.id as order_id, b.title, od.quantity
FROM Orders o
INNER JOIN Orders_details od ON o.id = od.order_id
INNER JOIN Book b ON od.book_id = b.id;
```

## Select
```sql
1. Get all the books:
SELECT * FROM Book;

2. Get all the publishers:
SELECT * FROM Publisher;

3. Get all the authors:
SELECT * FROM Author;

4. Get all the warehouses:
SELECT * FROM Warehouse;

5. Get all the books in a specific warehouse:
SELECT * FROM Book WHERE warehouse_id = 1;

6. Get all the books published by a specific publisher:
SELECT * FROM Book WHERE publisher = 'Bloomsbury Publishing';

7. Get all the books written by a specific author:
SELECT * FROM Book WHERE author = 'J.K. Rowling';

8. Get all the books in a shopping basket:
SELECT b.* FROM Book b
JOIN ShoppingBasket_Book sb ON b.id = sb.book_id
WHERE sb.shopping_basket_id = 1;

9. Get all the orders made by a specific customer:
SELECT * FROM Orders WHERE customer_id = 1;

10. Get all the orders made on a specific date:
SELECT * FROM Orders WHERE order_date = '2022-01-10';
```

## Triggers
```sql
1. Для обновления общего количества книг на складе после добавления книги в таблицу ShoppingBasket_Book:

CREATE OR REPLACE FUNCTION update_book_quantity()
RETURNS TRIGGER AS
$$
BEGIN
    UPDATE Warehouse
    SET capacity = capacity - 1 -- Уменьшите количество на 1
    WHERE id = NEW.warehouse_id;
  
    RETURN NEW;
END;
$$
LANGUAGE plpgsql;

CREATE TRIGGER update_book_quantity_trigger
AFTER INSERT ON ShoppingBasket_Book
FOR EACH ROW
EXECUTE FUNCTION update_book_quantity();

2. Чтобы обновить общее количество книг на складе после удаления книги из таблицы ShoppingBasket_Book:

CREATE OR REPLACE FUNCTION restore_book_quantity()
RETURNS TRIGGER AS
$$
BEGIN
    UPDATE Warehouse
    SET capacity = capacity + 1 -- Увеличить количество на 1
    WHERE id = OLD.warehouse_id;
  
    RETURN OLD;
END;
$$
LANGUAGE plpgsql;

CREATE TRIGGER restore_book_quantity_trigger
AFTER DELETE ON ShoppingBasket_Book
FOR EACH ROW
EXECUTE FUNCTION restore_book_quantity();

3. Чтобы автоматически назначить издателя книге на основе данных автора:

CREATE OR REPLACE FUNCTION assign_publisher()
RETURNS TRIGGER AS
$$
DECLARE
    publisher_id INT;
BEGIN
    SELECT id INTO publisher_id
    FROM Publisher
    WHERE name = NEW.author;
    
    IF publisher_id IS NOT NULL THEN
        UPDATE Book
        SET publisher = (SELECT name FROM Publisher WHERE id = publisher_id)
        WHERE id = NEW.id;
    ELSE
        -- Assign a default publisher if the author's publisher is not found
        UPDATE Book
        SET publisher = 'Unknown'
        WHERE id = NEW.id;
    END IF;
    
    RETURN NEW;
END;
$$
LANGUAGE plpgsql;

CREATE TRIGGER assign_publisher_trigger
BEFORE INSERT ON Book
FOR EACH ROW
EXECUTE FUNCTION assign_publisher();

4. чтобы обновить created_date корзины покупок после добавления нового заказа:

CREATE OR REPLACE FUNCTION update_basket_created_date()
RETURNS TRIGGER AS
$$
BEGIN
    UPDATE ShoppingBasket
    SET created_date = CURRENT_DATE
    WHERE id = NEW.shopping_basket_id;
  
    RETURN NEW;
END;
$$
LANGUAGE plpgsql;

CREATE TRIGGER update_basket_created_date_trigger
AFTER INSERT ON Orders
FOR EACH ROW
EXECUTE FUNCTION update_basket_created_date();
```
## Отчет
[OnlineBookShop) 23.docx](https://github.com/Steelrizee/DB-Practice/files/13594135/OnlineBookShop.23.docx)
```
