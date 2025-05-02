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
SELECT 
    cust.cust_name AS "Customer Name",
    cust.city,
    s.name AS "Salesman",
    s.commission
FROM 
    customer cust
JOIN 
    salesman s ON cust.salesman_id = s.salesman_id
WHERE 
    cust.cust_name IN (
        'Nick Rimando',
        'Graham Zusi',
        'Fabian Johns',
        'Brad Davis',
        'Julian Green',
        'Jozy Altidore'
    );

```

**Output:**

![image](https://github.com/user-attachments/assets/8a0a1974-483f-475a-885d-3f0e47680a4a)

**Question 7**
---
-- Paste Question 7 here

```sql
SELECT 
    p.first_name AS patient_name, 
    a.*
FROM 
    patients p
INNER JOIN 
    appointments a 
ON 
    p.patient_id = a.patient_id;

```

**Output:**

![Screenshot 2025-05-02 114839](https://github.com/user-attachments/assets/12b0711d-d493-4c64-bc9d-3266badca611)

**Question 8**
---
-- Paste Question 8 here

```sql
SELECT 
    p.first_name AS patient_name, 
    t.result_id, 
    t.patient_id, 
    t.test_name, 
    t.result, 
    t.test_date
FROM 
    patients p
INNER JOIN 
    test_results t 
ON 
    p.patient_id = t.patient_id
WHERE 
    p.admission_date BETWEEN '2024-01-01' AND '2024-01-31'
ORDER BY 
    t.test_date;

```

**Output:**

![image](https://github.com/user-attachments/assets/6dbe8492-9061-41bf-88a0-dee9f4ed41c8)

**Question 9**
---
-- Paste Question 9 here

```sql
SELECT 
    p.first_name AS patient_name, 
    d.first_name AS doctor_name
FROM 
    patients p
INNER JOIN 
    doctors d 
ON 
    p.doctor_id = d.doctor_id
WHERE 
    p.discharge_date IS NULL;

```

**Output:**

![image](https://github.com/user-attachments/assets/ffa5a470-55f4-4a31-a632-3253545f8e6c)

**Question 10**
---
-- Paste Question 10 here

```sql
SELECT 
    o.ord_no, 
    o.purch_amt, 
    o.ord_date, 
    c.cust_name, 
    c.city AS customer_city, 
    c.grade, 
    s.name AS salesman_name, 
    s.city AS salesman_city, 
    s.commission
FROM 
    orders o
INNER JOIN 
    customer c ON o.customer_id = c.customer_id
INNER JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/ff5879fd-b22b-47b6-a72e-25417379a490)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
