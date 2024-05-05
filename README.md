-- Create the database
CREATE DATABASE IF NOT EXISTS ECommerceDB;
USE ECommerceDB;

-- Create the Products table
CREATE TABLE Products (
    ProductID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(255) NOT NULL,
    Price DECIMAL(10, 2) NOT NULL,
    Quantity INT NOT NULL
);

-- Create the Customers table
CREATE TABLE Customers (
    CustomerID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(255) NOT NULL,
    Email VARCHAR(255) UNIQUE NOT NULL,
    Address TEXT
);

-- Create the Orders table
CREATE TABLE Orders (
    OrderID INT AUTO_INCREMENT PRIMARY KEY,
    CustomerID INT,
    OrderDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    TotalAmount DECIMAL(10, 2) NOT NULL,
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);

-- Create the OrderDetails table
CREATE TABLE OrderDetails (
    OrderDetailID INT AUTO_INCREMENT PRIMARY KEY,
    OrderID INT,
    ProductID INT,
    Quantity INT NOT NULL,
    UnitPrice DECIMAL(10, 2) NOT NULL,
    TotalPrice DECIMAL(10, 2) NOT NULL,
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID),
    FOREIGN KEY (ProductID) REFERENCES Products(ProductID)
);

1.Inserting data into the Products table:

INSERT INTO Products (Name, Price, Quantity) VALUES ('Product A', 10.99, 100);
INSERT INTO Products (Name, Price, Quantity) VALUES ('Product B', 19.99, 50);

2.Inserting data into the Customers table:

INSERT INTO Customers (Name, Email, Address) VALUES ('John Doe', 'john.doe@example.com', '123 Main St');
INSERT INTO Customers (Name, Email, Address) VALUES ('Jane Smith', 'jane.smith@example.com', '456 Elm St');

3.Inserting data into the Orders table:

INSERT INTO Orders (CustomerID, TotalAmount) VALUES (1, 45.98);
INSERT INTO Orders (CustomerID, TotalAmount) VALUES (2, 30.00);

4.Inserting data into the OrderDetails table:

INSERT INTO OrderDetails (OrderID, ProductID, Quantity, UnitPrice, TotalPrice) VALUES (1, 1, 3, 10.99, 32.97);
INSERT INTO OrderDetails (OrderID, ProductID, Quantity, UnitPrice, TotalPrice) VALUES (1, 2, 2, 19.99, 39.98);
INSERT INTO OrderDetails (OrderID, ProductID, Quantity, UnitPrice, TotalPrice) VALUES (2, 1, 5, 10.99, 54.95);

After inserting this data, you can then query the database to retrieve information. For example:

SELECT * FROM Products;
SELECT * FROM Customers;
SELECT * FROM Orders;
SELECT * FROM OrderDetails;
