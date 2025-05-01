# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
-- Paste Question 1 here

```sql
INSERT INTO employees (id, name, salary) VALUES (1, 'Alice', 50000);

```

**Output:**

![image](https://github.com/user-attachments/assets/f5e445b2-9245-4d07-a9c8-62d32a067bc4)


**Question 2**
---
-- Paste Question 2 here

```sql
INSERT INTO employees (id, name, salary) VALUES (2, 'Bob', 55000);
```

**Output:**

![image](https://github.com/user-attachments/assets/36c7ff8f-8518-493a-a139-997b591f0433)

**Question 3**
---
-- Paste Question 3 here

```sql
INSERT INTO employees (id, name, salary) VALUES (3, 'Charlie', 60000);
```

**Output:**

![image](https://github.com/user-attachments/assets/af695b8b-7056-488b-a03a-998d9ce88375)

**Question 4**
---
-- Paste Question 4 here

```sql
UPDATE employees SET salary = 58000 WHERE name = 'Bob';

```

**Output:**
![image](https://github.com/user-attachments/assets/cdbd129b-b1cb-4f65-901d-f74a76b415a7)


**Question 5**
---
-- Paste Question 5 here

```sql
DELETE FROM employees WHERE name = 'Alice';
```

**Output:**

![image](https://github.com/user-attachments/assets/dc369fa0-3232-43de-9120-6dd3f1f619d7)


**Question 6**
---
-- Paste Question 6 here

```sql
SELECT * FROM employees;
```

**Output:**

![image](https://github.com/user-attachments/assets/45b27903-664d-4f91-aead-7da45d9dca34)

**Question 7**
---
-- Paste Question 7 here

```sql
SELECT name, salary FROM employees WHERE salary > 55000;
```

**Output:**

![image](https://github.com/user-attachments/assets/1a739cc8-521f-4a44-b0b7-88927c4a2157)


**Question 8**
---
-- Paste Question 8 here

```sql
INSERT INTO employees SELECT * FROM temp_employees WHERE salary > 50000;

```

**Output:**
![image](https://github.com/user-attachments/assets/5c55cfc9-f22d-4fc9-a499-8b47a482e03d)


![Output8](output.png)

**Question 9**
---
-- Paste Question 9 here

```sql
UPDATE employees SET name = 'David' WHERE id = 3;
```

**Output:**

![image](https://github.com/user-attachments/assets/b7fbc5dd-d5e9-43cf-9c51-b0f05343bb3d)


**Question 10**
---
-- Paste Question 10 here

```sql
DELETE FROM employees WHERE salary < 55000;
```

**Output:**
![image](https://github.com/user-attachments/assets/fde0d92e-df57-4695-b690-9da5b063b917)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
