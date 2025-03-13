# Internship_DB SQL Tasks

## Overview
This project involves setting up a database named **Internship_DB**, creating tables for employees and departments, inserting sample records, and performing SQL queries for data retrieval, filtering, and sorting.

---
## Database & Table Setup

### **1. Create Database**
```sql
CREATE DATABASE Internship_DB;
USE Internship_DB;
```

### **2. Create Tables**
#### **Departments Table**
```sql
CREATE TABLE Departments (
    DeptID INT PRIMARY KEY AUTO_INCREMENT,
    DeptName VARCHAR(100) NOT NULL,
    Location VARCHAR(100) -- Added Location Column
);
```

#### **Employees Table**
```sql
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY AUTO_INCREMENT,
    EmpName VARCHAR(100) NOT NULL,
    Position VARCHAR(100),
    Salary DECIMAL(10,2),
    DeptID INT,
    FOREIGN KEY (DeptID) REFERENCES Departments(DeptID)
);
```

### **3. Insert Sample Data**
#### **Insert Data into Departments Table**
```sql
INSERT INTO Departments (DeptName, Location) VALUES
('Software Development', 'New York'),
('Quality Assurance', 'San Francisco'),
('Human Resources', 'Los Angeles'),
('Marketing', 'Chicago'),
('Finance', 'Boston');
```

#### **Insert Data into Employees Table**
```sql
INSERT INTO Employees (EmpName, Position, Salary, DeptID) VALUES
('Alice Johnson', 'Frontend Developer', 60000.00, 1),
('Bob Smith', 'Backend Developer', 65000.00, 1),
('Charlie Brown', 'QA Engineer', 55000.00, 2),
('Diana Wilson', 'HR Manager', 70000.00, 3),
('Ethan Davis', 'Marketing Specialist', 50000.00, 4);
```

---
## SQL Queries

### **1. Retrieve Employees' Names and Positions**
```sql
SELECT EmpName, Position FROM Employees;
```

### **2. List Departments with Locations**
```sql
SELECT DeptName, Location FROM Departments;
```

### **3. Query Employees Earning More Than $50,000**
```sql
SELECT EmpName, Position, Salary FROM Employees WHERE Salary > 50000;
```

### **4. Sort Employees by Name**
```sql
SELECT EmpName, Position, Salary, DeptID FROM Employees ORDER BY EmpName ASC;
```

### **5. List Departments in Specific Cities (e.g., New York & San Francisco)**
```sql
SELECT DeptName, Location FROM Departments WHERE Location IN ('New York', 'San Francisco');
```

---
## Notes
- The **Departments** table includes a `Location` column.
- The **Employees** table references `DeptID` as a foreign key.
- Sorting and filtering operations help organize and analyze the data efficiently.

---
## Author
Nimra Ambreen
Date: March 2025

