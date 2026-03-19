# Experiment 4: Aggregate Functions, Group By and Having Clause
### NAME:K.HASINI REG NO:212224240074
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
What is the average dosage prescribed for each medication?
#### Sample tablePrescriptions Table

```Medication     AvgDosage
-------------  ----------
Ciprofloxacin  500.0
Doxorubicin    60.0
Ibuprofen      400.0
Levothyroxine  50.0
Lisinopril     10.0
MMR            0.5
Pending        0.0
Prenatal vita  1.0
Sertraline     50.0
Topiramate     25.0
```

**Output:**
<img width="695" height="742" alt="image" src="https://github.com/user-attachments/assets/82edc37c-ed72-42a4-b88c-475480591edc" />


**Question 2**
---
How many patients are there in each city?
#### Sample table: Patients Table
```sql
Address     TotalPatients
----------  -------------
Berlin      3
Chicago     4
Mexico      3
```
```
select Address,count(*)
as TotalPatients
from Patients
group by Address
```

**Output:**

<img width="658" height="392" alt="image" src="https://github.com/user-attachments/assets/1d417d8a-e3f7-4b2a-aea3-def18c287550" />

**Question 3**
---
Write a SQL Query to find how many medications are prescribed for each patient?
#### Sample table:MedicalRecords Table
```sql
PatientID   AvgMedications
----------  --------------
4           5
6           1
7           1
8           3
```
```
SELECT PatientID,COUNT(*) AS 
AvgMedications
FROM MedicalRecords
GROUP BY PatientID;
```

**Output:**

<img width="677" height="612" alt="image" src="https://github.com/user-attachments/assets/75a382b4-19b2-4915-b6d4-d9a73dc3f398" />

**Question 4**
---
Write a SQL query to find the maximum purchase amount.
#### Sample table: orders
```sql
ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001
```
```
SELECT
  MAX(purch_amt) AS MAXIMUM
FROM
  orders;
```
**Output:**
<img width="403" height="297" alt="image" src="https://github.com/user-attachments/assets/8f481fe9-4b04-4001-8c63-39d56c5de332" />


**Question 5**
---
Write a SQL query to find the total income of employees aged 40 or above. 
#### Table: employee
```
name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER
```
```
SELECT
  SUM(income) AS total_income
FROM
  employee
WHERE
  age >= 40;
```
**Output:**

<img width="437" height="311" alt="image" src="https://github.com/user-attachments/assets/daa8d204-9781-4511-80a4-a0e74f477bfe" />

**Question 6**
---
Write a SQL query to find the number of employees whose age is greater than 32.

```sql
SELECT
  COUNT(*) AS COUNT
FROM
  employee
WHERE
  age > 32;
```

**Output:**
<img width="435" height="316" alt="image" src="https://github.com/user-attachments/assets/d4caf1b7-b358-4027-a4bf-64fdcf279aab" />


**Question 7**
---
Write a SQL query to find the average length of names for people living in Chennai?

```sql
name        type
----------  ----------
id          INTEGER
name        TEXT   
city        TEXT
email       TEXT
phone       INTEGER
```
```
SELECT
  AVG(LENGTH(name)) AS avg_name_length
FROM
  customer
WHERE
  city = 'Chennai';
```
**Output:**

<img width="438" height="295" alt="image" src="https://github.com/user-attachments/assets/b1114cb9-41df-4862-af91-c47db2c25717" />


**Question 8**
---
Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the maximum work hours for each date, and excludes dates where the maximum work hour is not greater than 12.
#### Sample table: employee1
```sql
jdate       MAX(workhour)
----------  -------------
2004.0      15
2006.0      15
```
```
SELECT
  jdate,
  MAX(workhour) AS "MAX(workhour)"
FROM
  employee1
GROUP BY
  jdate
HAVING
  MAX(workhour) > 12;
```
**Output:**
<img width="670" height="377" alt="image" src="https://github.com/user-attachments/assets/b27aa376-88ac-4b8b-b771-13f9674678d8" />


**Question 9**
---
Write the SQL query that achieves the grouping of data by occupation, calculates the total work hours for each occupation, and excludes occupations where the total work hour sum is not greater than 20.

#### Sample table: employee1
```sql
occupation  SUM(workhour)
----------  -------------
Business    30
Doctor      30
Engineer    24
Teacher     27
```
```
SELECT
  occupation,
  SUM(workhour) AS "SUM(workhour)"
FROM
  employee1
GROUP BY
  occupation
HAVING
  SUM(workhour) > 20;
```

**Output:**

<img width="616" height="437" alt="image" src="https://github.com/user-attachments/assets/feef3794-a98f-4e42-af59-9f02c7e37276" />


**Question 10**
---
Write the SQL query that achieves the grouping of data by occupation, calculates the average work hours for each occupation, and includes only those occupations where the average work hour falls between 10 and 12.
#### Sample table: employee1
```sql
Result
occupation  AVG(workhour)
----------  -------------
Business    10.0
Engineer    12.0
```
```
SELECT
  occupation,
  AVG(workhour) AS "AVG(workhour)"
FROM
  employee1
GROUP BY
  occupation
HAVING
  AVG(workhour) BETWEEN 10 AND 12;
```
**Output:**

<img width="753" height="387" alt="image" src="https://github.com/user-attachments/assets/a8a3f14c-c03d-4f74-961c-8739b3e83f01" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
