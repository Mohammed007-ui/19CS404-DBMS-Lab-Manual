# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));

```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
-- Paste Question 1 here
Used to create a new relation (table).
```sql
CREATE TABLE Student (
  StudentID INT PRIMARY KEY,
  Name VARCHAR(50) NOT NULL,
  Age INT CHECK (Age >= 17),
  Email VARCHAR(100) UNIQUE
);

```

**Output:**

![image](https://github.com/user-attachments/assets/7bd944c2-ec7c-449e-86ea-5fde4b651562)


**Question 2**
---
--- Paste Question 2 here


```sql
ALTER TABLE Student ADD Department VARCHAR(50);
```

**Output:**
![image](https://github.com/user-attachments/assets/92f8ec70-a003-4d42-829d-d85b13070523)


**Question 3**
---
-- Paste Question 3 here
Question 3: Modify the Name column to increase its size
```sql
ALTER TABLE Student MODIFY Name VARCHAR(100);
```

**Output:**
![image](https://github.com/user-attachments/assets/8cfcdbb0-1d40-49fc-bed4-d0d6bce3a40e)

**Question 4**
---
-- Paste Question 4 here
Question 4: Drop the Department Column
```sql
ALTER TABLE Student DROP COLUMN Department;
```

**Output:**
![image](https://github.com/user-attachments/assets/ac569ddc-55d0-4628-94c4-73e91f6232e3)

**Question 5**
---
-- Paste Question 5 here
Question 5: Rename the Student Table to Students
```sql
ALTER TABLE Student RENAME TO Students;
```

**Output:**
![image](https://github.com/user-attachments/assets/e91473d8-d3b8-4ffd-bcc8-66a5553b9a12)

**Question 6**
---
Question 6: Add a Primary Key Constraint

```sql
DROP TABLE IF EXISTS Students;

CREATE TABLE Students (
  StudentID INTEGER PRIMARY KEY,
  Name TEXT NOT NULL,
  Age INTEGER CHECK (Age >= 17),
  Email TEXT UNIQUE
);
```

**Output:**
![image](https://github.com/user-attachments/assets/af7ca25d-3957-4de8-815e-02bd711d382d)

**Question 7**
---
-- Paste Question 7 here
Question 7: Add a Foreign Key Constraint
```sql
-- Step 1: Rename the old table
ALTER TABLE Students RENAME TO Students_old;

-- Step 2: Create new table with constraints
CREATE TABLE Students (
  StudentID INTEGER PRIMARY KEY,
  Name TEXT NOT NULL,
  Age INTEGER CHECK (Age >= 18),
  Email TEXT UNIQUE
);

-- Step 3: Copy data from old table (ensure compatibility)
INSERT INTO Students (StudentID, Name, Age, Email)
SELECT StudentID, Name, Age, Email FROM Students_old;

-- Step 4: Drop the old table
DROP TABLE Students_old;

```

**Output:**

![image](https://github.com/user-attachments/assets/a5d17a40-1985-4d3f-a1e8-0858e97c0723)


**Question 8**
---
-- Paste Question 8 here
Question 8: Add a CHECK Constraint
```sql
-- Step 1: Rename the old table
ALTER TABLE Students RENAME TO Students_old;

-- Step 2: Create the new table with constraints (including CHECK constraint)
CREATE TABLE Students (
  StudentID INTEGER PRIMARY KEY,
  Name TEXT NOT NULL,
  Age INTEGER CHECK (Age >= 18),  -- Adding the CHECK constraint to Age
  Email TEXT UNIQUE
);

-- Step 3: Copy data from the old table to the new table (ensure data is valid)
INSERT INTO Students (StudentID, Name, Age, Email)
SELECT StudentID, Name, Age, Email FROM Students_old
WHERE Age >= 18;  -- Only copy valid data (Age >= 18)

-- Step 4: Drop the old table
DROP TABLE Students_old;
```

**Output:**



**Question 9**
---
-- Paste Question 9 here

```sql
Question 9: Add a UNIQUE Constraint
```

**Output:**

![image](https://github.com/user-attachments/assets/65b710a3-1d5c-4285-a3de-d93806a349fb)

**Question 10**
---
-- Paste Question 10 here
Question 10: Add a DEFAULT Constraint
```sql
ALTER TABLE Students ADD CONSTRAINT DF_Age DEFAULT 18 FOR Age;
```

**Output:**

![image](https://github.com/user-attachments/assets/f377e008-fc70-45e5-b115-5d0d87f59929)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
