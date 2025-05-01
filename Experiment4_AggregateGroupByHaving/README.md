# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
-- Paste Question 1 here

```sql
SELECT Department, COUNT(*) AS "Total Students"
FROM Students
GROUP BY Department;

```

**Output:**

![output1](https://github.com/user-attachments/assets/e1ae9364-c353-4c5c-9cfc-d2d15a468b9c)

**Question 2**
---
-- Paste Question 2 here

```sql
SELECT Department, AVG(Marks) AS "Average Marks"
FROM Students
GROUP BY Department;

```

**Output:**

![output2](https://github.com/user-attachments/assets/2d1bd19f-64d2-4029-96ec-559af2c99dd5)


**Question 3**
---
-- Paste Question 3 here

```sql
SELECT Product, SUM(Sales) AS "Total Sales"
FROM Sales
GROUP BY Product;

```

**Output:**

![output3](https://github.com/user-attachments/assets/987f18b5-0952-44a7-89a4-ada30c91501c)


**Question 4**
---
-- Paste Question 4 here

```sql
SELECT Dept, MIN(Salary) AS "Min Salary"
FROM Employees
GROUP BY Dept;

```

**Output:**

![output4](https://github.com/user-attachments/assets/85b83e8f-a907-4d0f-86d5-5ce8753f78c1)


**Question 5**
---
-- Paste Question 5 here

```sql
SELECT Dept, MAX(Salary) AS "Max Salary"
FROM Employees
GROUP BY Dept;

```

**Output:**

![output5](https://github.com/user-attachments/assets/c8ff36dd-0092-46d7-941f-6ef6284c6c91)


**Question 6**
---
-- Paste Question 6 here

```sql
SELECT Region, COUNT(*) AS "Sales Count"
FROM Sales
GROUP BY Region;

```

**Output:**

![output6](https://github.com/user-attachments/assets/f98e98ae-c6e0-444c-969f-c46533b0d61c)


**Question 7**
---
-- Paste Question 7 here

```sql
SELECT Item, AVG(Price) AS "AVG(Price)"
FROM Products
GROUP BY Item;

```

**Output:**

![output7](https://github.com/user-attachments/assets/796e4703-1622-4b21-87ef-ebb4c2512432)


**Question 8**
---
-- Paste Question 8 here

```sql
SELECT Course, SUM(Enrolled) AS "SUM(Enrolled)"
FROM Courses
GROUP BY Course;

```

**Output:**

![output8](https://github.com/user-attachments/assets/acf2b945-5ea9-4ae5-9659-62f9a99a59d0)


**Question 9**
---
-- Paste Question 9 here

```sql
SELECT City, COUNT(*) AS "COUNT(*)"
FROM Users
GROUP BY City;

```

**Output:**

![output9](https://github.com/user-attachments/assets/85b4ef08-fe0d-4db3-9dba-9aec729ae9cf)


**Question 10**
---
-- Paste Question 10 here

```sql
SELECT Employee, SUM(Hours) AS "Total Hours"
FROM Timesheet
GROUP BY Employee;

```

**Output:**

![output10](https://github.com/user-attachments/assets/aa612ae0-05b7-4abd-9ca3-87d0f4115c03)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
