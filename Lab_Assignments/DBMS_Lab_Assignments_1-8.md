### 🟩 Assignment 1:- (CREATE, SELECT, INSERT)

![Assignment1-Tables](https://github.com/sreasgop/TIU-BCA-Database-Lab/blob/main/Lab_Assignments/Screenshots/DBMS_Lab_Assignment-1_Tables.png)



1. Create table student with above field:
```SQL
sql> CREATE TABLE Student (Student_id INT, Student_name VARCHAR(20), phone INT);
```

2. Insert the following records into the table
```SQL
sql> INSERT INTO Student VALUES (1, 'Amit', 9345628987);  
sql> INSERT INTO Student VALUES (2, 'Akash', 9123456780);  
sql> INSERT INTO Student VALUES (3, 'Karim', NULL);  
sql> INSERT INTO Student VALUES (4, 'Monika', 9123456780);
```

3. Write a query to select all columns from the table.
```SQL
sql> SELECT * FROM Student;
```

Output:

| STUDENT_ID | STUDENT_NAME | PHONE      |
| ---------- | ------------ | ---------- |
| 1          | Amit         | 9345628987 |
| 2          | Akash        | 9123456780 |
| 3          | Karim        | NULL       |
| 4          | Monika       | 9123456780 |

4. Write a query to retrieve only the student_id and name of all students.
```SQL
sql> SELECT Student_id, Student_name FROM Student;
```

Output:

| STUDENT_ID | STUDENT_NAME |
| ---------- | ------------ |
| 1          | Amit         |
| 2          | Akash        |
| 3          | Karim        |
| 4          | Monika       |

---

### 🟩 Assignment 2:- (DDL and Different Constraints)

1. Create a tables Employees with the following fields:
- a. EmployeeID (INT) (Primary Key)
- b. FirstName (VARCHAR) (10)
- c. Department (VARCHAR) (5)
- d. Salary (INT)
	
```SQL
sql> CREATE TABLE Employees (EmployeeID INT PRIMARY KEY, FirstName VARCHAR(10),

Department VARCHAR(5), Salary INT);
```


2. Insert the records in the table.
```SQL
sql> INSERT INTO Employees VALUES (1, 'Amit', 'IT', 60000);  
sql> INSERT INTO Employees VALUES (2, 'Sara', 'HR', 55000);  
sql> INSERT INTO Employees VALUES (3, 'Ravi', 'MKT', 45000);
```


3. Show all records.
```SQL
sql> SELECT * FROM Employees;
```

Output:

| EMPLOYEEID | FIRSTNAME | DEPARTMENT | SALARY |
| ---------- | --------- | ---------- | ------ |
| 1          | Amit      | IT         | 60000  |
| 2          | Sara      | HR         | 55000  |
| 3          | Ravi      | MKT        | 45000  |

4. Alter the Employees table to add a new column Email.
```SQL
sql> ALTER TABLE Employees ADD Email VARCHAR(50);
```

5. Add a NOT NULL constraint to the salary field in the Employees table.
```SQL
sql> ALTER TABLE Employees MODIFY Salary INT NOT NULL;
```

6. Add a default value to the Salary field in the Employees table. The default salary should be 50000.
```SQL
sql> ALTER TABLE Employees ALTER Salary SET DEFAULT 50000;
```

7. Add a unique constraint to the Department field in the Employees table to ensure that each employee has a unique Department. 
```SQL
sql> ALTER TABLE Employees ADD CONSTRAINT unique_dept UNIQUE (Department);
```

8. Rename the FirstName field in the Employees table to EmployeeFirstName.
```SQL
sql> ALTER TABLE Employees RENAME COLUMN FirstName TO EmployeeFirstName;
```

9. Modify the Employee table to change the Department field type from VARCHAR (5) to VARCHAR (10).
```SQL
sql> ALTER TABLE Employees MODIFY Department VARCHAR(10);
```

10. Drop the Employees table from the database.
```SQL
sql> DROP TABLE Employees;
```

---

### 🟩 Assignment 3:- (WHERE, UPDATE, DELETE)

##### 🟦 Part 1: Table Creation and Data Insertion

1. Write an SQL statement to create a table named Products with the following
structure:
- ProductlD (INTEGER, Primary Key)
- ProductName (VARCHAR(20), NOT NULL)
- CategoryID (INTEGER, NOT NULL)
- Price (INTEGER, NOT NULL)
- StockQuantity (INTEGER, NOT NULL)
```SQL
sql> CREATE TABLE Products (ProductID INT PRIMARY KEY, ProductName VARCHAR(20) NOT NULL, CategoryID INT NOT NULL, Price INT NOT NULL, StockQuantity INT NOT NULL);
```

2. Insert the following data into the Products table:

| PRODUCTID | PRODUCTNAME        | CATEGORYID | PRICE | STOCKQUANTITY |
| --------- | ------------------ | ---------- | ----- | ------------- |
| 1         | Chais              | 1          | 18    | 50            |
| 2         | Chang              | 1          | 19    | 30            |
| 3         | Aniseed Syrup      | 2          | 10    | 60            |
| 4         | Cajun Seasoning    | 2          | 22    | 20            |
| 5         | Boysenberry Spread | 2          | 25    | 0             |

```SQL
sql> INSERT INTO Products VALUES (1, 'Chais', 1, 18, 50);  
sql> INSERT INTO Products VALUES (2, 'Chang', 1, 19, 30);  
sql> INSERT INTO Products VALUES (3, 'Aniseed Syrup', 2, 10, 60);  
sql> INSERT INTO Products VALUES (4, 'Cajun Seasoning', 2, 22, 20);  
sql> INSERT INTO Products VALUES (5, 'Boysenberry Spread', 2, 25, 0);
```


3. Write a query to view all records.
```SQL
sql> SELECT * FROM Products;
```

Output:

| PRODUCTID | PRODUCTNAME        | CATEGORYID | PRICE | STOCKQUANTITY |
| --------- | ------------------ | ---------- | ----- | ------------- |
| 1         | Chais              | 1          | 18    | 50            |
| 2         | Chang              | 1          | 19    | 30            |
| 3         | Aniseed Syrup      | 2          | 10    | 60            |
| 4         | Cajun Seasoning    | 2          | 22    | 20            |
| 5         | Boysenberry Spread | 2          | 25    | 0             |

##### 🟦 Part 2: WHERE Clause Practice

4. Retrieve all products where the price is greater than 20:
```SQL
sql> SELECT * FROM Products WHERE Price > 20;
```

Output:

| PRODUCTID | PRODUCTNAME        | CATEGORYID | PRICE | STOCKQUANTITY |
| --------- | ------------------ | ---------- | ----- | ------------- |
| 4         | Cajun Seasoning    | 2          | 22    | 20            |
| 5         | Boysenberry Spread | 2          | 25    | 0             |

5. Retrieve all products where CategoryID = 2. 
```SQL
sql> SELECT * FROM Products WHERE CategoryID = 2;
```


Output:

| PRODUCTID | PRODUCTNAME        | CATEGORYID | PRICE | STOCKQUANTITY |
| --------- | ------------------ | ---------- | ----- | ------------- |
| 3         | Aniseed Syrup      | 2          | 10    | 60            |
| 4         | Cajun Seasoning    | 2          | 22    | 20            |
| 5         | Boysenberry Spread | 2          | 25    | 0             |

6. Retrieve all products the have StockQuantity less than 40.
```SQL
sql> SELECT * FROM Products WHERE StockQuantity < 40;
```


Output:

| PRODUCTID | PRODUCTNAME        | CATEGORYID | PRICE | STOCKQUANTITY |
| --------- | ------------------ | ---------- | ----- | ------------- |
| 2         | Chang              | 1          | 19    | 30            |
| 4         | Cajun Seasoning    | 2          | 22    | 20            |
| 5         | Boysenberry Spread | 2          | 25    | 0             |

##### 🟦 Part 3: UPDATE Records

7. Update the price of Chais to 20 where ProductlD = 1.
```SQL
sql> UPDATE Products SET Price = 20 WHERE ProductID = 1;
```


8. Increase the price of all products in CategoryID = 2 by 10%.D
```SQL
sql> UPDATE Products SET Price = Price * 1.10 WHERE CategoryID = 2;
```


9. Reduce StockQuantity by 5 for all products where StockQuantity is greater than 40.
```SQL
sql> UPDATE Products SET StockQuantity = StockQuantity - 5 WHERE StockQuantity > 40;
```


##### 🟦 Part 4: DELETE Records

10. Delete the product Chang where ProductlD = 2.
```SQL
sql> DELETE FROM Products WHERE ProductID = 2;
```


11. Delete all products where the price is less than 12.
```SQL
sql> DELETE FROM Products WHERE Price < 12;
```


12. Delete all products where StockQuantity is 0.
```SQL
sql> DELETE FROM Products WHERE StockQuantity = 0;
```

---
### 🟩 Assignment 4:- (Aggregation Function)

# Assignment - 4 (Aggregate Function)

## 1. Create the Employee Table
- EmpID INT PRIMARY KEY,
- Name VARCHAR(50),
- Department VARCHAR(50),
- Salary INT,
- YearOfJoining INT

```sql
CREATE TABLE Employee (
    EmpID INT PRIMARY KEY,
    Name VARCHAR(50),
    Department VARCHAR(50),
    Salary INT,
    YearOfJoining INT
);
```

## 2. Insert Sample Data
```sql
INSERT INTO Employee (EmpID, Name, Department, Salary, YearOfJoining) VALUES
(1, 'Alice', 'HR', 50000, 2022),
(2, 'Bob', 'IT', 70000, 2021),
(3, 'Charlie', 'Finance', 60000, 2020),
(4, 'David', 'HR', 55000, 2019),
(5, 'Eva', 'IT', 80000, 2022),
(6, 'Frank', 'Finance', 62000, 2021),
(7, 'Grace', 'HR', 48000, 2018),
(8, 'Hank', 'IT', 90000, 2017),
(9, 'Ivy', 'Finance', 75000, 2019),
(10, 'Jack', 'IT', 85000, 2020);
```

## 3. View all the records.
```sql
SELECT * FROM Employee;
```

**Output:**

| EmpID | Name    | Department | Salary | YearOfJoining |
|-------|---------|------------|--------|---------------|
| 1     | Alice   | HR         | 50000  | 2022          |
| 2     | Bob     | IT         | 70000  | 2021          |
| 3     | Charlie | Finance    | 60000  | 2020          |
| 4     | David   | HR         | 55000  | 2019          |
| 5     | Eva     | IT         | 80000  | 2022          |
| 6     | Frank   | Finance    | 62000  | 2021          |
| 7     | Grace   | HR         | 48000  | 2018          |
| 8     | Hank    | IT         | 90000  | 2017          |
| 9     | Ivy     | Finance    | 75000  | 2019          |
| 10    | Jack    | IT         | 85000  | 2020          |

## 4. Find the total salary of all employees.
```sql
SELECT SUM(Salary) AS TotalSalary
FROM Employee;
```

**Output:**

| TotalSalary |
|-------------|
| 675000      |

## 5. Find the average salary of all employees.
```sql
SELECT AVG(Salary) AS AvgSalary
FROM Employee;
```

**Output:**

| AvgSalary |
|-----------|
| 67500     |

## 6. Count the total number of employees.
```sql
SELECT COUNT(*) AS TotalEmployees
FROM Employee;
```

**Output:**

| TotalEmployees |
|----------------|
| 10             |

## 7. Find the highest salary in the company.
```sql
SELECT MAX(Salary) AS HighestSalary
FROM Employee;
```

**Output:**

| HighestSalary |
|---------------|
| 90000         |

## 8. Find the lowest salary in the company.
```sql
SELECT MIN(Salary) AS LowestSalary
FROM Employee;
```

**Output:**

| LowestSalary |
|--------------|
| 48000        |

## 9. Find the total salary of employees who joined after 2020.
```sql
SELECT SUM(Salary) AS TotalSalary
FROM Employee
WHERE YearOfJoining > 2020;
```

**Output:**

| TotalSalary |
|-------------|
| 200000      |

## 10. Find the average salary of employees who joined in 2021.
```sql
SELECT AVG(Salary) AS AvgSalary
FROM Employee
WHERE YearOfJoining = 2021;
```

**Output:**

| AvgSalary |
|-----------|
| 66000     |

## 11. Count the number of employees who joined before 2020.
```sql
SELECT COUNT(*) AS EmployeeCount
FROM Employee
WHERE YearOfJoining < 2020;
```

**Output:**

| EmployeeCount |
|---------------|
| 4             |

## 12. Find the highest salary of employees earning less than 80,000.
```sql
SELECT MAX(Salary) AS HighestSalary
FROM Employee
WHERE Salary < 80000;
```

**Output:**

| HighestSalary |
|---------------|
| 75000         |

## 13. Find the total salary of employees earning more than 50,000.
```sql
SELECT SUM(Salary) AS TotalSalary
FROM Employee
WHERE Salary > 50000;
```

**Output:**

| TotalSalary |
|-------------|
| 575000      |

## 14. Find the number of employees who earn less than 60,000.
```sql
SELECT COUNT(*) AS EmployeeCount
FROM Employee
WHERE Salary < 60000;
```

**Output:**

| EmployeeCount |
|---------------|
| 3             |

## 15. Find the total salary of employees in the IT department.
```sql
SELECT SUM(Salary) AS TotalSalary
FROM Employee
WHERE Department = 'IT';
```

**Output:**

| TotalSalary |
|-------------|
| 325000      |

## 16. Find the highest salary in the HR department.
```sql
SELECT MAX(Salary) AS HighestSalary
FROM Employee
WHERE Department = 'HR';
```

**Output:**

| HighestSalary |
|---------------|
| 55000         |

## 17. Find the lowest salary in the Finance department.
```sql
SELECT MIN(Salary) AS LowestSalary
FROM Employee
WHERE Department = 'Finance';
```

**Output:**

| LowestSalary |
|--------------|
| 60000        |

## 18. Find the highest salary of employees who joined before 2019.
```sql
SELECT MAX(Salary) AS HighestSalary
FROM Employee
WHERE YearOfJoining < 2019;
```

**Output:**

| HighestSalary |
|---------------|
| 90000         |
```
