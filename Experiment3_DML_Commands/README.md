# Experiment 3: DML Commands
### NAME: K.HASINI REG NO:212224240074
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
-- Write a SQL statement to Update the reorder level to 20 where the quantity in stock is less than 10 and product category is 'Snacks' in the products table.
### Products table
```
-- update Products
set reorder_lvl=20
where quantity<10 and category ='Snacks';
```
**Output:**
<img width="1215" height="638" alt="image" src="https://github.com/user-attachments/assets/68abf9b2-dd84-435e-b90c-45c20df99cf2" />


**Question 2**
---
-- Write a SQL statement to Increase the selling price by 15% in the products table where quantity in stock is less than 50 and supplier ID is 10.

```sql
-- update Products 
set sell_price=sell_price*1.15
where quantity <50 and supplier_id =10;
```

**Output:**
<img width="1201" height="557" alt="image" src="https://github.com/user-attachments/assets/88e3ef08-bfb0-4d96-b31c-311cf530a9b5" />


**Question 3**
---
-- Write a SQL statement to change the EMAIL and COMMISSION_PCT column of the following EMPLOYEES table with 'not available' and 0.55 for those employees whose DEPARTMENT_ID is 110.

```sql
-- UPDATE Employees
set EMAIL='not available',commission_pct=0.55
where DEPARTMENT_ID =110;
```

**Output:**

<img width="1220" height="446" alt="image" src="https://github.com/user-attachments/assets/253b7a3a-7945-4e6f-acce-2b958b144150" />


**Question 4**
---
--  Write a SQL statement to Update the hire_date of employees in department 50 to 2024-01-24.

```sql
-- update Employees
set hire_date='2024-01-24';
```

**Output:**

<img width="1212" height="345" alt="image" src="https://github.com/user-attachments/assets/aafb5621-17e5-4b31-b410-2cf85d642588" />


**Question 5**
---
--  Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.

```sql
-- update Products
set product_name='Premium Bread'
where product_id=5;
```

**Output:**
<img width="1205" height="461" alt="image" src="https://github.com/user-attachments/assets/ab54ab4b-297d-4604-b325-1d0751272caf" />


**Question 6**
---
-- Write a SQL query to Delete customers from 'customer' table where 'GRADE' is exactly 2.

```sql
-- delete from customer
where grade =2;
```

**Output:**
<img width="1210" height="652" alt="image" src="https://github.com/user-attachments/assets/3752fc5a-7231-4929-bf26-afb6cabbffad" />


**Question 7**
---
-- Write a SQL query to Delete customers with 'GRADE' 3 and whose 'CUST_NAME' contains the substring 'BBB', and 'PAYMENT_AMT' is greater than 2000

```sql
-- delete from customer
where grade= 3 
and cust_name like '%BBB%' 
and payment_amt>2000;
```

**Output:**

<img width="1208" height="572" alt="image" src="https://github.com/user-attachments/assets/f7a944ae-9f7d-46d0-ab9a-654ad0af75d1" />


**Question 8**
---
-- Write a SQL query to Delete customers from 'customer' table where 'AGENT_CODE' is either 'A003' or 'A008'.

```sql
-- delete from customer
where agent_code IN('A003','A008');
```

**Output:**

<img width="783" height="947" alt="image" src="https://github.com/user-attachments/assets/f79dad0c-8d70-46bc-b83f-2e0c7f163e43" />


**Question 9**
---
Write a SQL query to Delete customers from 'customer' table where 'CUST_CITY' is not 'New York' and 'OUTSTANDING_AMT' is greater than 5000.

```sql
-- DELETE FROM CUSTOMER
WHERE CUST_CITY != 'New York'
and outstanding_AMT >5000;
```

**Output:**
<img width="1211" height="666" alt="image" src="https://github.com/user-attachments/assets/7b8d3930-fa97-4c0f-a6b9-9462d842dd3c" />


**Question 10**
---
-- Write a SQL query to delete a doctor from Doctors table whose Specialization is 'Pediatrics' and First name is 'Michael'.

```sql
-- delete from Doctors
where specialization like '%Pediatric%'
and first_name ='Michael';
```

**Output:**

<img width="1218" height="451" alt="image" src="https://github.com/user-attachments/assets/e6913ff0-904d-402e-9dd7-e930a19a4034" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
