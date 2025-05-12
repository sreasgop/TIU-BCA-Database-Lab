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
sql> ALTER TABLE Employees MODIFY Salary DEFAULT 50000;
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
sql> insert into Products values (1, 'Chais', 1, 18, 50);  
sql> insert into Products values (2, 'Chang', 1, 19, 30);  
sql> insert into Products values (3, 'Aniseed Syrup', 2, 10, 60);  
sql> insert into Products values (4, 'Cajun Seasoning', 2, 22, 20);  
sql> insert into Products values (5, 'Boysenberry Spread', 2, 25, 0);
```


3. Write a query to view all records.
```SQL
sql> select * from Products;
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
sql> select * from Products where Price > 20;
```

Output:

| PRODUCTID | PRODUCTNAME        | CATEGORYID | PRICE | STOCKQUANTITY |
| --------- | ------------------ | ---------- | ----- | ------------- |
| 4         | Cajun Seasoning    | 2          | 22    | 20            |
| 5         | Boysenberry Spread | 2          | 25    | 0             |

5. Retrieve all products where CategoryID = 2. 
```SQL
sql> select * from Products where CategoryID = 2;
```


Output:

| PRODUCTID | PRODUCTNAME        | CATEGORYID | PRICE | STOCKQUANTITY |
| --------- | ------------------ | ---------- | ----- | ------------- |
| 3         | Aniseed Syrup      | 2          | 10    | 60            |
| 4         | Cajun Seasoning    | 2          | 22    | 20            |
| 5         | Boysenberry Spread | 2          | 25    | 0             |

6. Retrieve all products the have StockQuantity less than 40.
```SQL
sql>select * from Products where StockQuantity < 40;
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
sql> update Products set Price = 20 where ProductID = 1;
```


8. Increase the price of all products in CategoryID = 2 by 10%.D
```SQL
sql> update Products set Price = Price * 1.10 where CategoryID = 2;
```


9. Reduce StockQuantity by 5 for all products where StockQuantity is greater than 40.
```SQL
sql> update Products set StockQuantity = StockQuantity - 5 where StockQuantity > 40;
```


##### 🟦 Part 4: DELETE Records

10. Delete the product Chang where ProductlD = 2.
```SQL
sql> delete from Products where ProductID = 2;
```


11. Delete all products where the price is less than 12.
```SQL
sql> delete from Products where Price < 12;
```


12. Delete all products where StockQuantity is 0.
```SQL
sql> delete from Products where StockQuantity = 0;
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
sql> create table Employee (EmpID int primary key, Name varchar (50), Department varchar (50), Salary int, YearOfJoining int);
```

## 2. Insert Sample Data
```sql
sql> insert into Employee values (1, 'Alice', 'HR', 50000, 2022);
sql> insert into Employee values (2, 'Bob', 'IT', 70000, 2021);
sql> insert into Employee values(3, 'Charlie', 'Finance', 60000, 2020);
sql> insert into Employee values (4, 'David', 'HR', 55000, 2019);
sql> insert into Employee values (5, 'Eva', 'IT', 80000, 2022);
sql> insert into Employee values (6, 'Frank', 'Finance', 62000, 2021); 
sql> insert into Employee values (7, 'Grace', 'HR', 48000, 2018);
sql> insert into Employee values (8, 'Hank', 'IT', 90000, 2017);
sql> insert into Employee values (9, 'Ivy', 'Finance', 75000, 2019);
sql> insert into Employee values (10, 'Jack', 'IT', 85000, 2020);
```

## 3. View all the records.
```sql
sql> select * from Employee;
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
sql> select sum(Salary) as TotalSalary from Employee;
```

**Output:**

| TotalSalary |
|-------------|
| 675000      |

## 5. Find the average salary of all employees.
```sql
sql> select avg(Salary) as AvgSalary from Employee;
```

**Output:**

| AvgSalary |
|-----------|
| 67500     |

## 6. Count the total number of employees.
```sql 
sql> select count(*) as TotalEmployees from Employee;
```

**Output:**

| TotalEmployees |
|----------------|
| 10             |

## 7. Find the highest salary in the company.
```sql
sql> select max(Salary) as HighestSalary from Employee;
```

**Output:**

| HighestSalary |
|---------------|
| 90000         |

## 8. Find the lowest salary in the company.
```sql
sql> select min(Salary) as LowestSalary from Employee;
```

**Output:**

| LowestSalary |
|--------------|
| 48000        |

## 9. Find the total salary of employees who joined after 2020.
```sql
sql> select sum(Salary) as TotalSalary from Employee where YearOfJoining > 2020;
```

**Output:**

| TotalSalary |
|-------------|
| 200000      |

## 10. Find the average salary of employees who joined in 2021.
```sql
sql> select AVG(Salary) as AvgSalary from Employee where YearOfJoining = 2021;
```

**Output:**

| AvgSalary |
|-----------|
| 66000     |

## 11. Count the number of employees who joined before 2020.
```sql
sql> select count(*) AS EmployeeCount from Employee where YearOfJoining < 2020;
```

**Output:**

| EmployeeCount |
|---------------|
| 4             |

## 12. Find the highest salary of employees earning less than 80,000.
```sql
sql> select max(Salary) as HighestSalary from Employee where Salary < 80000;
```

**Output:**

| HighestSalary |
|---------------|
| 75000         |

## 13. Find the total salary of employees earning more than 50,000.
```sql
sql> select sum(Salary) as TotalSalary from Employee where Salary > 50000;
```

**Output:**

| TotalSalary |
|-------------|
| 575000      |

## 14. Find the number of employees who earn less than 60,000.
```sql
sql> select count(*) as EmployeeCount from Employee where Salary < 60000;
```

**Output:**

| EmployeeCount |
|---------------|
| 3             |

## 15. Find the total salary of employees in the IT department.
```sql
sql> select sum(Salary) as TotalSalary from Employee where Department = 'IT';
```

**Output:**

| TotalSalary |
|-------------|
| 325000      |

## 16. Find the highest salary in the HR department.
```sql
sql> select max(Salary) as HighestSalary from Employee where Department = 'HR';
```

**Output:**

| HighestSalary |
|---------------|
| 55000         |

## 17. Find the lowest salary in the Finance department.
```sql
sql> select min(Salary) as LowestSalary from Employee where Department = 'Finance';
```

**Output:**

| LowestSalary |
|--------------|
| 60000        |

## 18. Find the highest salary of employees who joined before 2019.
```sql
sql> select max(Salary) as HighestSalary from Employee where YearOfJoining < 2019;
```

**Output:**

| HighestSalary |
|---------------|
| 90000         |

___

# Assignment - 5 (Queries using LIKE, IN, and BETWEEN)

## Part 1: Creating Tables and Inserting Data

### Q1. Create a table named Employees with the following structure.
**Table Structure:**  
- EmpID (Primary Key)  
- Name  
- Department  
- Salary  
- JoiningYear  

```sql
sql> create table Employees (EmpID int primary key, Name varchar(50), Department varchar(20), Salary int, JoiningYear int);
```

### Q2. Insert at least 10 records into the Employees table.

| EmpID | Name          | Department | Salary | JoiningYear |
|-------|---------------|------------|--------|-------------|
| 1     | John Doe      | HR         | 50000  | 2020        |
| 2     | Jane Smith    | IT         | 75000  | 2019        |
| 3     | Alice Brown   | Finance    | 62000  | 2021        |
| 4     | Bob Johnson   | IT         | 80000  | 2018        |
| 5     | Charlie White | HR         | 47000  | 2020        |
| 6     | Eve Black     | Finance    | 55000  | 2020        |
| 7     | David Green   | IT         | 90000  | 2017        |
| 8     | Olivia Blue   | HR         | 52000  | 2019        |
| 9     | Liam Yellow   | Finance    | 70000  | 2021        |
| 10    | Sophia Red    | IT         | 72000  | 2022        |

```sql
sql> insert into employees values (1, 'John Doe', 'HR', 50000, 2020);
sql> insert into employees values (2, 'Jane Smith', 'IT', 75000, 2019);
sql> insert into employees values (3, 'Alice Brown', 'Finance', 62000, 2021);
sql> insert into employees values (4, 'Bob Johnson', 'IT', 80000, 2018);
sql> insert into employees values (5, 'Charlie White', 'HR', 47000, 2020);
sql> insert into employees values (6, 'Eve Black', 'Finance', 55000, 2020);
sql> insert into employees values (7, 'David Green', 'IT', 90000, 2017);
sql> insert into employees values (8, 'Olivia Blue', 'HR', 52000, 2019);
sql> insert into employees values (9, 'Liam Yellow', 'Finance', 70000, 2021);
sql> insert into employees values (10, 'Sophia Red', 'IT', 72000, 2022);
```

### Q3. Show all records of table.
```sql
sql> select * from employees;
```

**Output:**

| EmpID | Name          | Department | Salary | JoiningYear |
|-------|---------------|------------|--------|-------------|
| 1     | John Doe      | HR         | 50000  | 2020        |
| 2     | Jane Smith    | IT         | 75000  | 2019        |
| 3     | Alice Brown   | Finance    | 62000  | 2021        |
| 4     | Bob Johnson   | IT         | 80000  | 2018        |
| 5     | Charlie White | HR         | 47000  | 2020        |
| 6     | Eve Black     | Finance    | 55000  | 2020        |
| 7     | David Green   | IT         | 90000  | 2017        |
| 8     | Olivia Blue   | HR         | 52000  | 2019        |
| 9     | Liam Yellow   | Finance    | 70000  | 2021        |
| 10    | Sophia Red    | IT         | 72000  | 2022        |

## Part 2: Queries using LIKE, IN, and BETWEEN

### Q4. Retrieve employees whose names start with 'J' using LIKE.
```sql
sql> select * from Employees where name like 'J%';
```

**Output:**

| EmpID | Name       | Department | Salary | JoiningYear |
|-------|------------|------------|--------|-------------|
| 1     | John Doe   | HR         | 50000  | 2020        |
| 2     | Jane Smith | IT         | 75000  | 2019        |

### Q5. Retrieve employees whose names end with 'e' using LIKE.
```sql
sql> select * from Employees where name like '%e';
```

**Output:**

| EmpID | Name          | Department | Salary | JoiningYear |
|-------|---------------|------------|--------|-------------|
| 1     | John Doe      | HR         | 50000  | 2020        |
| 5     | Charlie White | HR         | 47000  | 2020        |
| 8     | Olivia Blue   | HR         | 52000  | 2019        |

### Q6. Retrieve employees whose names contain 'o' using LIKE.
```sql
sql> select * from Employees where name like '%o%';
```

**Output:**

| EmpID | Name         | Department | Salary | JoiningYear |
|-------|--------------|------------|--------|-------------|
| 1     | John Doe     | HR         | 50000  | 2020        |
| 3     | Alice Brown  | Finance    | 62000  | 2021        |
| 4     | Bob Johnson  | IT         | 80000  | 2018        |
| 8     | Olivia Blue  | HR         | 52000  | 2019        |
| 9     | Liam Yellow  | Finance    | 70000  | 2021        |
| 10    | Sophia Red   | IT         | 72000  | 2022        |

### Q7. Retrieve employees in the IT or HR department using IN.
```sql
sql> select * from Employees where Department in ('IT', 'HR');
```

**Output:**

| EmpID | Name          | Department | Salary | JoiningYear |
|-------|---------------|------------|--------|-------------|
| 1     | John Doe      | HR         | 50000  | 2020        |
| 2     | Jane Smith    | IT         | 75000  | 2019        |
| 4     | Bob Johnson   | IT         | 80000  | 2018        |
| 5     | Charlie White | HR         | 47000  | 2020        |
| 7     | David Green   | IT         | 90000  | 2017        |
| 8     | Olivia Blue   | HR         | 52000  | 2019        |
| 10    | Sophia Red    | IT         | 72000  | 2022        |

### Q8. Retrieve employees who have a salary of 50000, 70000, or 90000 using IN.
```sql
sql> select * from Employees where Salary in (50000, 70000, 90000);
```

**Output:**

| EmpID | Name        | Department | Salary | JoiningYear |
|-------|-------------|------------|--------|-------------|
| 1     | John Doe    | HR         | 50000  | 2020        |
| 7     | David Green | IT         | 90000  | 2017        |
| 9     | Liam Yellow | Finance    | 70000  | 2021        |

### Q9. Retrieve employees who joined between 2019 and 2021 using BETWEEN.
```sql
sql> select * from Employees where JoiningYear between 2019 and 2021;
```

**Output:**

| EmpID | Name          | Department | Salary | JoiningYear |
|-------|---------------|------------|--------|-------------|
| 1     | John Doe      | HR         | 50000  | 2020        |
| 2     | Jane Smith    | IT         | 75000  | 2019        |
| 3     | Alice Brown   | Finance    | 62000  | 2021        |
| 5     | Charlie White | HR         | 47000  | 2020        |
| 6     | Eve Black     | Finance    | 55000  | 2020        |
| 8     | Olivia Blue   | HR         | 52000  | 2019        |
| 9     | Liam Yellow   | Finance    | 70000  | 2021        |

### Q10. Retrieve employees whose salaries are between 60000 and 80000 using BETWEEN.
```sql
sql> select * from Employees where Salary between 60000 and 80000;
```

**Output:**

| EmpID | Name         | Department | Salary | JoiningYear |
|-------|--------------|------------|--------|-------------|
| 2     | Jane Smith   | IT         | 75000  | 2019        |
| 3     | Alice Brown  | Finance    | 62000  | 2021        |
| 4     | Bob Johnson  | IT         | 80000  | 2018        |
| 9     | Liam Yellow  | Finance    | 70000  | 2021        |
| 10    | Sophia Red   | IT         | 72000  | 2022        |

### Q11. Retrieve employees whose joining year is between 2018 and 2020 using BETWEEN.
```sql
sql> select * from Employees where JoiningYear between 2018 and 2020;
```

**Output:**

| EmpID | Name          | Department | Salary | JoiningYear |
|-------|---------------|------------|--------|-------------|
| 1     | John Doe      | HR         | 50000  | 2020        |
| 2     | Jane Smith    | IT         | 75000  | 2019        |
| 4     | Bob Johnson   | IT         | 80000  | 2018        |
| 5     | Charlie White | HR         | 47000  | 2020        |
| 6     | Eve Black     | Finance    | 55000  | 2020        |
| 8     | Olivia Blue   | HR         | 52000  | 2019        |

### Q12. Retrieve employees whose department names start with 'F' using LIKE.
```sql
sql> select * from Employees where Department like 'F%';
```

**Output:**

| EmpID | Name         | Department | Salary | JoiningYear |
|-------|--------------|------------|--------|-------------|
| 3     | Alice Brown  | Finance    | 62000  | 2021        |
| 6     | Eve Black    | Finance    | 55000  | 2020        |
| 9     | Liam Yellow  | Finance    | 70000  | 2021        |

### Q13. Retrieve employees whose names have 'a' as the second letter using LIKE.
```sql
sql> select * from Employees where name like '_a%';
```

**Output:**

| EmpID | Name        | Department | Salary | JoiningYear |
|-------|-------------|------------|--------|-------------|
| 2     | Jane Smith  | IT         | 75000  | 2019        |

### Q14. Retrieve employees whose salaries are not between 50000 and 80000 using NOT BETWEEN.
```sql
sql> select * from Employees where Salary not between 50000 and 80000;
```

**Output:**

| EmpID | Name          | Department | Salary | JoiningYear |
|-------|---------------|------------|--------|-------------|
| 5     | Charlie White | HR         | 47000  | 2020        |
| 7     | David Green   | IT         | 90000  | 2017        |

### Q15. Retrieve employees whose names do not contain 'e' using NOT LIKE.
```sql
sql> select * from Employees where Name not like '%e%';
```

**Output:**

| EmpID | Name         | Department | Salary | JoiningYear |
|-------|--------------|------------|--------|-------------|
| 3     | Alice Brown  | Finance    | 62000  | 2021        |
| 4     | Bob Johnson  | IT         | 80000  | 2018        |
| 6     | Eve Black    | Finance    | 55000  | 2020        |
| 9     | Liam Yellow  | Finance    | 70000  | 2021        |
| 10    | Sophia Red   | IT         | 72000  | 2022        |

### Q16. Retrieve employees who are not in the IT department using NOT IN.
```sql
sql> select * from Employees where Department not in ('IT');
```

**Output:**

| EmpID | Name          | Department | Salary | JoiningYear |
|-------|---------------|------------|--------|-------------|
| 1     | John Doe      | HR         | 50000  | 2020        |
| 3     | Alice Brown   | Finance    | 62000  | 2021        |
| 5     | Charlie White | HR         | 47000  | 2020        |
| 6     | Eve Black     | Finance    | 55000  | 2020        |
| 8     | Olivia Blue   | HR         | 52000  | 2019        |
| 9     | Liam Yellow   | Finance    | 70000  | 2021        |

### Q17. Retrieve employees whose joining years are not between 2019 and 2022 using NOT BETWEEN.
```sql
sql> select * from Employees where JoiningYear not between 2019 and 2022;
```

**Output:**

| EmpID | Name        | Department | Salary | JoiningYear |
|-------|-------------|------------|--------|-------------|
| 4     | Bob Johnson | IT         | 80000  | 2018        |
| 7     | David Green | IT         | 90000  | 2017        |

### Q18. Retrieve employees whose salaries are exactly 47000 or 55000 using IN.
```sql
sql> select * from Employees where Salary in (47000, 55000);
```

**Output:**

| EmpID | Name          | Department | Salary | JoiningYear |
|-------|---------------|------------|--------|-------------|
| 5     | Charlie White | HR         | 47000  | 2020        |
| 6     | Eve Black     | Finance    | 55000  | 2020        |

### Q19. Retrieve employees whose names contain 'a' using LIKE.
```sql
sql> select * from Employees where Name like '%a%';
```

**Output:**

| EmpID | Name          | Department | Salary | JoiningYear |
|-------|---------------|------------|--------|-------------|
| 2     | Jane Smith    | IT         | 75000  | 2019        |
| 3     | Alice Brown   | Finance    | 62000  | 2021        |
| 5     | Charlie White | HR         | 47000  | 2020        |
| 8     | Olivia Blue   | HR         | 52000  | 2019        |
| 10    | Sophia Red    | IT         | 72000  | 2022        |

### Q20. Retrieve employees whose names have 'o' as the third letter using LIKE.
```sql
sql> select * from Employees where Name like '__o%';
```

**Output:**

```SQL
-- no rows selected
```

___

# Assignment - 6 (ORDER BY, GROUP BY, HAVING Clause)

## Part 1: Create and Insert Statements

### Q1. Write a query to create a table named Sales with columns: SaleID (INT, Primary Key), ProductName (VARCHAR), Category (VARCHAR), Quantity (INT), PricePerUnit (INT), Region (VARCHAR).
```sql
sql> create table Sales (SaleID int primary key, ProductName varchar(50), Category varchar(50), Quantity int, PricePerUnit int, Region varchar(50));
```

### Q2. Write queries to insert at least 8 sample records into the Sales table.
```sql
sql> insert into Sales values (1, 'Laptop', 'Electronics', 2, 600, 'North');
sql> insert into Sales values (2, 'Smartphone', 'Electronics', 4, 300, 'South');
sql> insert into Sales values (3, 'Desk Chair', 'Furniture', 1, 150, 'West');
sql> insert into Sales values (4, 'Book', 'Stationery', 10, 20, 'East');
sql> insert into Sales values (5, 'Monitor', 'Electronics', 3, 200, 'North');
sql> insert into Sales values (6, 'Notebook', 'Stationery', 5, 10, 'South');
sql> insert into Sales values (7, 'Sofa', 'Furniture', 1, 800, 'West');
sql> insert into Sales values (8, 'Pen', 'Stationery', 12, 5, 'East');
```

## Part 2: ORDER BY Clause

### Q3. List all sales sorted by product name in ascending order.
```sql
sql> select * from Sales order by ProductName asc;
```

**Output:**

| SaleID | ProductName | Category    | Quantity | PricePerUnit | Region |
|--------|-------------|-------------|----------|--------------|--------|
| 4      | Book        | Stationery  | 10       | 20           | East   |
| 3      | Desk Chair  | Furniture   | 1        | 150          | West   |
| 1      | Laptop      | Electronics | 2        | 600          | North  |
| 5      | Monitor     | Electronics | 3        | 200          | North  |
| 6      | Notebook    | Stationery  | 5        | 10           | South  |
| 8      | Pen         | Stationery  | 12       | 5            | East   |
| 2      | Smartphone  | Electronics | 4        | 300          | South  |
| 7      | Sofa        | Furniture   | 1        | 800          | West   |

### Q4. List all sales sorted by quantity in descending order.
```sql
sql> select * from Sales order by Quantity desc;
```

**Output:**

| SaleID | ProductName | Category    | Quantity | PricePerUnit | Region |
|--------|-------------|-------------|----------|--------------|--------|
| 8      | Pen         | Stationery  | 12       | 5            | East   |
| 4      | Book        | Stationery  | 10       | 20           | East   |
| 6      | Notebook    | Stationery  | 5        | 10           | South  |
| 2      | Smartphone  | Electronics | 4        | 300          | South  |
| 5      | Monitor     | Electronics | 3        | 200          | North  |
| 1      | Laptop      | Electronics | 2        | 600          | North  |
| 3      | Desk Chair  | Furniture   | 1        | 150          | West   |
| 7      | Sofa        | Furniture   | 1        | 800          | West   |

### Q5. Display sales in the ‘Electronics’ category, sorted by product name (A–Z).
```sql
sql> select * from Sales where Category = 'Electronics' order by ProductName asc;
```

**Output:**

| SaleID | ProductName | Category    | Quantity | PricePerUnit | Region |
|--------|-------------|-------------|----------|--------------|--------|
| 1      | Laptop      | Electronics | 2        | 600          | North  |
| 5      | Monitor     | Electronics | 3        | 200          | North  |
| 2      | Smartphone  | Electronics | 4        | 300          | South  |

### Q6. List all sales sorted first by category (A–Z), then by price per unit (lowest to highest).
```sql
sql> select * from Sales order by Category asc, PricePerUnit asc;
```

**Output:**

| SaleID | ProductName | Category    | Quantity | PricePerUnit | Region |
| ------ | ----------- | ----------- | -------- | ------------ | ------ |
| 5      | Monitor     | Electronics | 3        | 200          | North  |
| 2      | Smartphone  | Electronics | 4        | 300          | South  |
| 1      | Laptop      | Electronics | 2        | 600          | North  |
| 3      | Desk Chair  | Furniture   | 1        | 150          | West   |
| 7      | Sofa        | Furniture   | 1        | 800          | West   |
| 8      | Pen         | Stationery  | 12       | 5            | East   |
| 6      | Notebook    | Stationery  | 5        | 10           | South  |
| 4      | Book        | Stationery  | 10       | 20           | East   |

### Q7. List the top 3 highest priced sales.
```sql
sql> select * from Sales order by PricePerUnit desc limit 3;
```

**Output:**

| SaleID | ProductName | Category    | Quantity | PricePerUnit | Region |
|--------|-------------|-------------|----------|--------------|--------|
| 7      | Sofa        | Furniture   | 1        | 800          | West   |
| 1      | Laptop      | Electronics | 2        | 600          | North  |
| 2      | Smartphone  | Electronics | 4        | 300          | South  |

## Part 3: GROUP BY Clause

### Q8. Calculate the total quantity sold per product.
```sql
sql> select ProductName, sum(Quantity) as TotalQuantity from Sales group by ProductName;
```

**Output:**

| ProductName | TotalQuantity |
|-------------|---------------|
| Laptop      | 2             |
| Smartphone  | 4             |
| Desk Chair  | 1             |
| Book        | 10            |
| Monitor     | 3             |
| Notebook    | 5             |
| Sofa        | 1             |
| Pen         | 12            |

### Q9. Find average quantity sold per region.
```sql
sql> select Region, avg(Quantity) as AvgQuantity from Sales group by Region;
```

**Output:**

| Region | AvgQuantity |
|--------|-------------|
| North  | 2.5         |
| South  | 4.5         |
| West   | 1.0         |
| East   | 11.0        |

### Q10. Show the total revenue per category. (Revenue = Quantity × PricePerUnit)
```sql
sql> select Category, sum(Quantity * PricePerUnit) as TotalRevenue from Sales group by Category;
```

**Output:**

| Category    | TotalRevenue |
|-------------|--------------|
| Electronics | 3100         |
| Furniture   | 950          |
| Stationery  | 400          |

### Q11. Find how many different sales were made per category.
```sql
sql> select Category, count(*) as NumberOfSales from Sales group by Category;
```

**Output:**

| Category    | NumberOfSales |
|-------------|---------------|
| Electronics | 3             |
| Furniture   | 2             |
| Stationery  | 3             |

### Q12. Show total sales (revenue) per product per region.
```sql
sql> select ProductName, Region, sum(Quantity * PricePerUnit) as TotalRevenue from Sales group by ProductName, Region;
```

**Output:**

| ProductName | Region | TotalRevenue |
|-------------|--------|--------------|
| Laptop      | North  | 1200         |
| Smartphone  | South  | 1200         |
| Desk Chair  | West   | 150          |
| Book        | East   | 200          |
| Monitor     | North  | 600          |
| Notebook    | South  | 50           |
| Sofa        | West   | 800          |
| Pen         | East   | 60           |

## Part 4: HAVING Clause

### Q13. List all products where the total quantity sold is greater than 5.
```sql
sql> select ProductName, sum(Quantity) as TotalQuantity from Sales group by ProductName having SUM(Quantity) > 5;
```

**Output:**

| ProductName | TotalQuantity |
|-------------|---------------|
| Book        | 10            |
| Pen         | 12            |

### Q14. Show each region where the average quantity sold is more than 3.
```sql
sql> select Region, avg(Quantity) as AvgQuantity from Sales group by Region having AVG(Quantity) > 3;
```

**Output:**

| Region | AvgQuantity |
|--------|-------------|
| South  | 4.5         |
| East   | 11.0        |

### Q15. Show products where the maximum quantity sold in a single sale is at least 4.
```sql
sql> select ProductName, max(Quantity) as MaxQuantity from Sales group by ProductName having MAX(Quantity) >= 4;
```

**Output:**

| ProductName | MaxQuantity |
|-------------|-------------|
| Smartphone  | 4           |
| Book        | 10          |
| Notebook    | 5           |
| Pen         | 12          |

### Q16. Display categories where the total revenue exceeds $500.
```sql
sql> select Category, sum(Quantity * PricePerUnit) as TotalRevenue from Sales group by Category having sum(Quantity * PricePerUnit) > 500;
```

**Output:**

| Category    | TotalRevenue |
|-------------|--------------|
| Electronics | 3100         |
| Furniture   | 950          |

### Q17. Show products with an average quantity sold per transaction less than 3.
```sql
sql> select ProductName, avg(Quantity) as AvgQuantity from Sales group by ProductName having avg(Quantity) < 3;
```

**Output:**

| ProductName | AvgQuantity |
|-------------|-------------|
| Laptop      | 2.0         |
| Desk Chair  | 1.0         |
| Sofa        | 1.0         |

___

# Assignment - 7 (JOIN Operation)

## Part A: Table Creation and Data Insertion

### 1. Create a table named DEPARTMENT with the following structure:
- dept_id (Integer, Primary Key)
- dept_name (Variable-length string, up to 20 characters)

```sql
sql> CREATE TABLE DEPARTMENT (dept_id INT PRIMARY KEY, dept_name VARCHAR(20));
```

### 2. Create a table named EMPLOYEE with the following structure:
- emp_id (Integer, Primary Key)
- emp_name (Variable-length string, up to 20 characters)
- dept_id (Integer, foreign key referencing DEPARTMENT)

```sql
sql> CREATE TABLE EMPLOYEE ( emp_id INT PRIMARY KEY, emp_name VARCHAR(20), dept_id INT, FOREIGN KEY (dept_id) REFERENCES DEPARTMENT(dept_id));
```

### 3. Insert the following records into the DEPARTMENT table:
```sql
sql> INSERT INTO DEPARTMENT VALUES (1, 'Sales'); 
sql> INSERT INTO DEPARTMENT VALUES (2, 'HR');
sql> INSERT INTO DEPARTMENT VALUES (3, 'IT');
sql> INSERT INTO DEPARTMENT VALUES (4, 'Marketing');
```

### 4. Insert the following records into the EMPLOYEE table:
```sql
sql> INSERT INTO EMPLOYEE VALUES (101, 'Alice', 1); 
sql> INSERT INTO EMPLOYEE VALUES (102, 'Bob', 2); 
sql> INSERT INTO EMPLOYEE VALUES (103, 'Charlie', 3); 
sql> INSERT INTO EMPLOYEE VALUES (104, 'David', NULL); 
```

### 5. Write a query to view all records from the DEPARTMENT table.
```sql
sql> SELECT * FROM DEPARTMENT;
```

**Output:**

| dept_id | dept_name  |
|---------|------------|
| 1       | Sales      |
| 2       | HR         |
| 3       | IT         |
| 4       | Marketing  |

### 6. Write a query to view all records from the EMPLOYEE table.
```sql
sql> SELECT * FROM EMPLOYEE;
```

**Output:**

| emp_id | emp_name | dept_id |
|--------|----------|---------|
| 101    | Alice    | 1       |
| 102    | Bob      | 2       |
| 103    | Charlie  | 3       |
| 104    | David    | NULL    |

## Part B: Join Operations

### 7. Write a query using INNER JOIN to display employee names, department IDs, and department names for employees who belong to an existing department.
```sql
sql> SELECT e.emp_name, e.dept_id, d.dept_name FROM EMPLOYEE e INNER JOIN DEPARTMENT d ON e.dept_id = d.dept_id;
```

**Output:**

| emp_name | dept_id | dept_name |
|----------|---------|-----------|
| Alice    | 1       | Sales     |
| Bob      | 2       | HR        |
| Charlie  | 3       | IT        |

### 8. Write a query using LEFT JOIN to display all employee names, their department IDs, and department names. Include employees even if they don’t belong to a valid department.
```sql
sql> SELECT e.emp_name, e.dept_id, d.dept_name FROM EMPLOYEE e LEFT JOIN DEPARTMENT d ON e.dept_id = d.dept_id;
```

**Output:**

| emp_name | dept_id | dept_name |
|----------|---------|-----------|
| Alice    | 1       | Sales     |
| Bob      | 2       | HR        |
| Charlie  | 3       | IT        |
| David    | NULL    | NULL      |

### 9. Write a query using RIGHT JOIN to display all departments along with employee names (if any) and employee department IDs.
```sql
sql> SELECT d.dept_name, e.emp_name, e.dept_id FROM EMPLOYEE e RIGHT JOIN DEPARTMENT d ON e.dept_id = d.dept_id;
```

**Output:**

| dept_name | emp_name | dept_id |
|-----------|----------|---------|
| Sales     | Alice    | 1       |
| HR        | Bob      | 2       |
| IT        | Charlie  | 3       |
| Marketing | NULL     | NULL    |

### 10. Write a query using FULL OUTER JOIN to display all employees and all departments, matching them where possible. Include unmatched rows from both tables.
*Note: Since some SQL databases (e.g., MySQL) don’t support FULL OUTER JOIN directly, we can simulate it using LEFT JOIN and RIGHT JOIN with UNION.*

```sql
sql> SELECT e.emp_name, e.dept_id, d.dept_name FROM EMPLOYEE e LEFT JOIN DEPARTMENT d ON e.dept_id = d.dept_id UNION SELECT e.emp_name, e.dept_id, d.dept_name FROM EMPLOYEE e RIGHT JOIN DEPARTMENT d ON e.dept_id = d.dept_id WHERE e.emp_id IS NULL;
```

**Output:**

| emp_name | dept_id | dept_name |
|----------|---------|-----------|
| Alice    | 1       | Sales     |
| Bob      | 2       | HR        |
| Charlie  | 3       | IT        |
| David    | NULL    | NULL      |
| NULL     | NULL    | Marketing |

### 11. Write a query using CROSS JOIN to display all possible combinations of employees and departments. Include employee department ID and department ID from both tables.
```sql
sql> SELECT e.emp_name, e.dept_id AS emp_dept_id, d.dept_id AS dept_dept_id, d.dept_name FROM EMPLOYEE e CROSS JOIN DEPARTMENT d;
```

**Output:**

| emp_name | emp_dept_id | dept_dept_id | dept_name  |
|----------|-------------|--------------|------------|
| Alice    | 1           | 1            | Sales      |
| Alice    | 1           | 2            | HR         |
| Alice    | 1           | 3            | IT         |
| Alice    | 1           | 4            | Marketing  |
| Bob      | 2           | 1            | Sales      |
| Bob      | 2           | 2            | HR         |
| Bob      | 2           | 3            | IT         |
| Bob      | 2           | 4            | Marketing  |
| Charlie  | 3           | 1            | Sales      |
| Charlie  | 3           | 2            | HR         |
| Charlie  | 3           | 3            | IT         |
| Charlie  | 3           | 4            | Marketing  |
| David    | NULL        | 1            | Sales      |
| David    | NULL        | 2            | HR         |
| David    | NULL        | 3            | IT         |
| David    | NULL        | 4            | Marketing  |


___

# Assignment - 8 (Nested Queries)

## Table Creation & Data Insertion

### Q1. Write a SQL query to create the DEPARTMENT table with the following columns:
- Dept_ID (Primary Key)
- Dept_Name
- Location

```sql
CREATE TABLE DEPARTMENT (
    Dept_ID INT PRIMARY KEY,
    Dept_Name VARCHAR(50),
    Location VARCHAR(50)
);
```

### Q2. Write a SQL query to create the EMPLOYEE table with the following columns:
- Emp_ID (Primary Key)
- Emp_Name
- Salary
- Dept_ID (Foreign Key referencing DEPARTMENT(Dept_ID))

```sql
CREATE TABLE EMPLOYEE (
    Emp_ID INT PRIMARY KEY,
    Emp_Name VARCHAR(50),
    Salary INT,
    Dept_ID INT,
    FOREIGN KEY (Dept_ID) REFERENCES DEPARTMENT(Dept_ID)
);
```

### Q3. Insert the following records into the DEPARTMENT table:
```sql
INSERT INTO DEPARTMENT (Dept_ID, Dept_Name, Location) VALUES (1, 'HR', 'New York'),
(2, 'IT', 'San Jose'),
(3, 'Marketing', 'Chicago');
```

### Q4. Insert the following records into the EMPLOYEE table:
```sql
INSERT INTO EMPLOYEE VALUES (101, 'Alice', 70000, 1);
INSERT INTO EMPLOYEE VALUES (102, 'Bob', 90000, 2);
INSERT INTO EMPLOYEE VALUES (103, 'Carol', 85000, 2);
INSERT INTO EMPLOYEE VALUES (104, 'Dave', 60000, 3);
INSERT INTO EMPLOYEE VALUES (105, 'Eve', 95000, 2);
```

### Q5. Write a SQL query to display all records from the EMPLOYEE table.
```sql
SELECT * FROM EMPLOYEE;
```

**Output:**

| Emp_ID | Emp_Name | Salary | Dept_ID |
|--------|----------|--------|---------|
| 101    | Alice    | 70000  | 1       |
| 102    | Bob      | 90000  | 2       |
| 103    | Carol    | 85000  | 2       |
| 104    | Dave     | 60000  | 3       |
| 105    | Eve      | 95000  | 2       |

### Q6. Write a SQL query to display all records from the DEPARTMENT table.
```sql
SELECT * FROM DEPARTMENT;
```

**Output:**

| Dept_ID | Dept_Name | Location  |
|---------|-----------|-----------|
| 1       | HR        | New York  |
| 2       | IT        | San Jose  |
| 3       | Marketing | Chicago   |

## Nested Queries

### Q7. Write a SQL query to list the department name where the employee ‘Carol’ works.
```sql
SELECT Dept_Name
FROM DEPARTMENT
WHERE Dept_ID = (SELECT Dept_ID FROM EMPLOYEE WHERE Emp_Name = 'Carol');
```

**Output:**

| Dept_Name |
|-----------|
| IT        |

### Q8. Write a SQL query to list employees who work in departments located in ‘New York’ or ‘Chicago’.
```sql
SELECT Emp_Name
FROM EMPLOYEE
WHERE Dept_ID IN (SELECT Dept_ID FROM DEPARTMENT WHERE Location IN ('New York', 'Chicago'));
```

**Output:**

| Emp_Name |
|----------|
| Alice    |
| Dave     |

### Q9. Write a SQL query to display employees whose salary is between the salary of ‘Bob’ and ‘Eve’.
```sql
SELECT Emp_Name, Salary
FROM EMPLOYEE
WHERE Salary BETWEEN 
    (SELECT Salary FROM EMPLOYEE WHERE Emp_Name = 'Bob') 
    AND 
    (SELECT Salary FROM EMPLOYEE WHERE Emp_Name = 'Eve');
```

**Output:**

| Emp_Name | Salary |
|----------|--------|
| Bob      | 90000  |
| Carol    | 85000  |

### Q10. Write a SQL query to display department names where any employee’s name starts with the letter ‘A’.
```sql
SELECT Dept_Name
FROM DEPARTMENT
WHERE Dept_ID IN (SELECT Dept_ID FROM EMPLOYEE WHERE Emp_Name LIKE 'A%');
```

**Output:**

| Dept_Name |
|-----------|
| HR        |

### Q11. Write a SQL query to show employees who have the highest salary.
```sql
SELECT Emp_Name, Salary
FROM EMPLOYEE
WHERE Salary = (SELECT MAX(Salary) FROM EMPLOYEE);
```

**Output:**

| Emp_Name | Salary |
|----------|--------|
| Eve      | 95000  |
