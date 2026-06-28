# Advanced SQL Server Assignment: CTEs & Window Functions

This repository contains the practical implementation of advanced SQL Server techniques, including Common Table Expressions (CTEs), Recursive Queries, and Window Functions.

---

## 📊 Database Schema & Setup

The database consists of three main tables: `Customers`, `Products`, and `Orders`.

### 1. Database Creation & Schema
```sql
CREATE DATABASE ECommerceDB;
GO
USE ECommerceDB;
GO

CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY IDENTITY(1,1),
    CustomerName VARCHAR(100) NOT NULL,
    City VARCHAR(50)
);

CREATE TABLE Products (
    ProductID INT PRIMARY KEY IDENTITY(1,1),
    ProductName VARCHAR(100) NOT NULL,
    Category VARCHAR(50),
    Price DECIMAL(10,2)
);

CREATE TABLE Orders (
    OrderID INT PRIMARY KEY IDENTITY(1,1),
    CustomerID INT FOREIGN KEY REFERENCES Customers(CustomerID),
    ProductID INT FOREIGN KEY REFERENCES Products(ProductID),
    OrderDate DATE,
    Quantity INT,
    TotalAmount DECIMAL(10,2)
);
