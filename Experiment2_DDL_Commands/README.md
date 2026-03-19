# Experiment 2: DDL Commands
### NAME: K.Hasini REG NO: 212224240074
## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```
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
<img width="712" height="329" alt="image" src="https://github.com/user-attachments/assets/ad29cda3-cbb8-47e1-b7e9-f1f12b52399d" />


```
CREATE TABLE Employees
(
    EmployeeID INTEGER ,
    FirstName TEXT ,
    LastName TEXT,
    HireDate DATE
);
```

**Output:**

<img width="831" height="195" alt="image" src="https://github.com/user-attachments/assets/f7197cf0-812e-48d5-8c32-76a2726a99d0" />


**Question 2**
---
<img width="666" height="180" alt="image" src="https://github.com/user-attachments/assets/bb69c2fa-c991-42fe-8206-99a8a45b71bc" />


```
CREATE TABLE Bonuses
(
    BonusID  INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    BonusAmount REAL CHECK (BonusAmount>0),
    BonusDate DATE,
    Reason TEXT NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)

);
```

**Output:**

<img width="1321" height="287" alt="image" src="https://github.com/user-attachments/assets/81b2c063-3c22-4856-8420-e735cd21ee52" />


**Question 3**
---
<img width="558" height="287" alt="image" src="https://github.com/user-attachments/assets/409fd7b0-cbda-4927-a6d7-06ea9c6afa54" />


```
INSERT INTO Employee(EmployeeID, Name, Department, Salary)
SELECT EmployeeID, Name, Department, Salary FROM  Former_employees;
```

**Output:**

<img width="1013" height="291" alt="image" src="https://github.com/user-attachments/assets/bb7a30b5-7c2c-4526-b1c8-b40562588649" />


**Question 4**
---
<img width="1153" height="262" alt="image" src="https://github.com/user-attachments/assets/bb7e9d79-4dcc-44de-80a9-6bb0480f3dc8" />


```
CREATE TABLE Department
(
    DepartmentID INTEGER PRIMARY KEY,
    DepartmentName TEXT UNIQUE NOT NULL,
    Location TEXT
);
```

**Output:**
<img width="1290" height="278" alt="image" src="https://github.com/user-attachments/assets/67dad35a-e9ac-421a-af54-ff63d934240e" />

**Question 5**
---
<img width="1048" height="326" alt="image" src="https://github.com/user-attachments/assets/f9776cd5-8dd3-401d-aca5-553d5adb106c" />

```
CREATE TABLE Employees
(
   EmployeeID INTEGER PRIMARY KEY,
   FirstName  NOT NULL,
   LastName NOT NULL,
   Email UNIQUE,
   Salary CHECK(Salary>0),
   DepartmentID INTEGER,
   FOREIGN KEY(DepartmentID) REFERENCES Departments(DepartmentID)
   
);
```

**Output:**
<img width="1356" height="389" alt="image" src="https://github.com/user-attachments/assets/3c4c3976-ae31-4f58-aa69-274ac03fb994" />


**Question 6**
---
-<img width="1166" height="243" alt="image" src="https://github.com/user-attachments/assets/d9844ee8-4065-42a8-bf7f-54f1eeaa1e84" />


```
ALTER TABLE  Student_details ADD COLUMN email TEXT NOT NULL DEFAULT 'Invalid';

```

**Output:**
<img width="1341" height="233" alt="image" src="https://github.com/user-attachments/assets/6c3417cc-7f6c-47dc-a6dd-56542ad69912" />



**Question 7**
---
<img width="758" height="379" alt="image" src="https://github.com/user-attachments/assets/0b8f3107-e68b-4b81-b91c-086221a408e3" />

```
INSERT INTO Books(ISBN ,Title ,Author) VALUES ('978-6655443321'  , 'Big Data Analytics' ,'Karen Adams');

```

**Output:**

<img width="1102" height="304" alt="image" src="https://github.com/user-attachments/assets/0b5bd8a2-1e91-491e-8b8f-69c96f3c02bf" />


**Question 8**
---
<img width="857" height="320" alt="image" src="https://github.com/user-attachments/assets/ce2247a2-186f-4479-b608-60a35dd1fc8b" />


```
ALTER TABLE Student_details ADD COLUMN  ParentsNumber number;
ALTER TABLE Student_details ADD COLUMN  Adhar_Number number;
```

**Output:**

<img width="1284" height="339" alt="image" src="https://github.com/user-attachments/assets/02b31f76-586e-4dd8-9fee-e82bb88e39ff" />


**Question 9**
---
<img width="943" height="299" alt="image" src="https://github.com/user-attachments/assets/31ab4e61-c464-47b9-b9e1-7499ea8464ee" />

```
ALTER table Employees ADD COLUMN  Date_of_joining Date ;
ALTER table Employees RENAME Column  job_title to Designation;
```

**Output:**

<img width="1306" height="327" alt="image" src="https://github.com/user-attachments/assets/0f795f7c-572d-4190-8840-04e6a3b85690" />


**Question 10**
---
<img width="1122" height="279" alt="image" src="https://github.com/user-attachments/assets/4570bc43-2a1a-4bfa-8b09-68098a5979f6" />


```
Insert into Books( ISBN, Title, Author, Publisher, YearPublished)
select ISBN, Title, Author, Publisher, YearPublished from  Out_of_print_books;
```

**Output:**

<img width="1319" height="249" alt="image" src="https://github.com/user-attachments/assets/a156a7f3-6f97-443a-ba3e-061f319d28f5" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
