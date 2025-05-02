![image](https://github.com/user-attachments/assets/3d1fe984-f2a4-4342-96fd-991ad07410d8)![image](https://github.com/user-attachments/assets/90946268-67a4-4384-b4da-0a85cd352c19)# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
-- Paste Question 1 here

```sql
SELECT p.first_name AS patient_name, t.test_name
FROM patients p
INNER JOIN test_results t ON p.patient_id = t.patient_id;
```

**Output:**


![image](https://github.com/user-attachments/assets/4752684e-715f-4c12-ac5a-c690e857740e)


**Question 2**
---
-- Paste Question 2 here

```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
JOIN salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**


![image](https://github.com/user-attachments/assets/e2f8d7aa-c07e-43b1-9da4-53ac1006de64)

**Question 3**
---
-- Paste Question 3 here

```sql

SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;

```

**Output:**


![image](https://github.com/user-attachments/assets/f9dac91f-f7ad-47d0-a792-ac3f9311e546)

**Question 4**
---
-- Paste Question 4 here

```sql

SELECT 
    c.cust_name,
    c.city AS city,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM customer c
JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.grade < 300
ORDER BY c.customer_id;

```

**Output:**


![image](https://github.com/user-attachments/assets/77d16fff-4293-4a50-813e-9c5b7e518838)

**Question 5**
---
-- Paste Question 5 here

```sql
SELECT s.name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id = c.salesman_id
WHERE c.city = 'London';

```

**Output:**

![image](https://github.com/user-attachments/assets/967f71ee-4862-4282-97e9-6fc336abdbbd)

**Question 6**
---
-- Paste Question 6 here

```sql

```

**Output:**

![Output6](output.png)

**Question 7**
---
-- Paste Question 7 here

```sql
-- Paste your SQL code below for Question 7
```

**Output:**

![Output7](output.png)

**Question 8**
---
-- Paste Question 8 here

```sql
-- Paste your SQL code below for Question 8
```

**Output:**

![Output8](output.png)

**Question 9**
---
-- Paste Question 9 here

```sql
-- Paste your SQL code below for Question 9
```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
-- Paste your SQL code below for Question 10
```

**Output:**

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
