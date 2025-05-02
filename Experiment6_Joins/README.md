# Experiment 6: Joins

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
SELECT e.employee_id, e.name, d.department_name
FROM employees e
INNER JOIN departments d ON e.dept_id = d.department_id;
```

**Output:**

![Output1](output.png)

**Question 2**
---
-- Paste Question 2 here

```sql
SELECT s.student_id, s.name, m.course_name
FROM students s
LEFT JOIN marks m ON s.student_id = m.student_id;

```

**Output:**

![Output2](output.png)

**Question 3**
---
-- Paste Question 3 here

```sql
SELECT p.product_name, s.supplier_name
FROM products p
RIGHT JOIN suppliers s ON p.supplier_id = s.supplier_id;

```

**Output:**

![Output3](output.png)

**Question 4**
---
-- Paste Question 4 here

```sql
SELECT a.author_name, b.book_title
FROM authors a
FULL OUTER JOIN books b ON a.author_id = b.author_id;

```

**Output:**

![Output4](output.png)

**Question 5**
---
-- Paste Question 5 here

```sql
SELECT o.order_id, c.customer_name
FROM orders o
INNER JOIN customers c ON o.customer_id = c.customer_id;

```

**Output:**

![Output5](output.png)

**Question 6**
---
-- Paste Question 6 here

```sql
SELECT t.teacher_name, c.class_name
FROM teachers t
LEFT JOIN classes c ON t.teacher_id = c.class_teacher_id;

```

**Output:**

![Output6](output.png)

**Question 7**
---
-- Paste Question 7 here

```sql
SELECT c.course_name, s.name
FROM courses c
RIGHT JOIN students s ON c.course_id = s.course_id;

```

**Output:**

![Output7](output.png)

**Question 8**
---
-- Paste Question 8 here

```sql
SELECT p.project_title, t.team_name
FROM projects p
INNER JOIN teams t ON p.team_id = t.team_id;

```

**Output:**

![Output8](output.png)

**Question 9**
---
-- Paste Question 9 here

```sql
SELECT p.patient_name, pr.medicine
FROM patients p
LEFT JOIN prescriptions pr ON p.patient_id = pr.patient_id;

```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
SELECT p.product_name, c.category_name
FROM products p
RIGHT JOIN categories c ON p.category_id = c.category_id;
```

**Output:**

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
