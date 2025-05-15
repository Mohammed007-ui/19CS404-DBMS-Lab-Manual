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
WHERE dept_id IN (
    SELECT dept_id FROM departments WHERE location = 'Chennai'
);
```
![image](https://github.com/user-attachments/assets/6ffc4d73-50d2-44a5-b894-52aa52306597)

### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
![image](https://github.com/user-attachments/assets/90f3a24d-591e-4494-88df-84c6a32afa08)

```
SELECT emp_id, emp_name, salary, dept_id
FROM employees e1
WHERE salary > (
    SELECT AVG(salary) FROM employees e2
    WHERE e1.dept_id = e2.dept_id
);
```
![image](https://github.com/user-attachments/assets/5aeecbc4-e6f1-402d-b51f-5047f321e967)

```sql
CREATE VIEW high_salary_employees AS
SELECT emp_id, emp_name, salary FROM employees
WHERE salary > 50000;

-- View usage
SELECT * FROM high_salary_employees;

-- Drop view
DROP VIEW high_salary_employees;
```
![image](https://github.com/user-attachments/assets/3e437ed0-dc11-48b8-8a8c-88621888c52f)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
