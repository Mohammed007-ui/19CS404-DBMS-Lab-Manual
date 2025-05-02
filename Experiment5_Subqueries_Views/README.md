# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
-- Paste Question 1 here

```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

**Output:**

![Output1](output.png)

**Question 2**
---
-- Paste Question 2 here

```sql
CREATE VIEW sales_employees AS
SELECT employee_id, first_name, last_name, department
FROM employees
WHERE department = 'Sales';

```

**Output:**

![Output2](output.png)

**Question 3**
---
-- Paste Question 3 here

```sql
SELECT department, COUNT(*) AS num_employees
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;

```

**Output:**

![Output3](output.png)

**Question 4**
---
-- Paste Question 4 here

```sql
SELECT first_name, last_name, department
FROM employees
WHERE department = (SELECT department FROM employees WHERE first_name = 'John' AND last_name = 'Doe');

```

**Output:**

![Output4](output.png)

**Question 5**
---
-- Paste Question 5 here

```sql
CREATE VIEW high_salary_employees AS
SELECT employee_id, first_name, last_name, salary
FROM employees
WHERE salary > 5000;
```

**Output:**

![Output5](output.png)

**Question 6**
---
-- Paste Question 6 here

```sql
SELECT employee_id, first_name, last_name, job_title
FROM employees
WHERE job_title = 'Manager';

```

**Output:**

![Output6](output.png)

**Question 7**
---
-- Paste Question 7 here

```sql
SELECT e.first_name, e.last_name, e.salary, e.department
FROM employees e
WHERE e.salary > (SELECT AVG(salary) FROM employees WHERE department = e.department);

```

**Output:**

![Output7](output.png)

**Question 8**
---
-- Paste Question 8 here

```sql
CREATE VIEW moderate_salary_employees AS
SELECT employee_id, first_name, last_name, salary
FROM employees
WHERE salary BETWEEN 4000 AND 6000;

```

**Output:**

![Output8](output.png)

**Question 9**
---
-- Paste Question 9 here

```sql
SELECT first_name, last_name, department
FROM employees
WHERE department != 'HR';

```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
SELECT first_name, last_name
FROM employees
WHERE first_name LIKE 'A%';

```

**Output:**

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
