# Experiment 4: Aggregate Functions, Group By and Having Clause

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
-- How many patients have expired insurance coverage for each insurance company?

```sql
--select InsuranceCompany,
    count (*) as  TotalExpiredPatients
from Insurance
group by InsuranceCompany;
```

**Output:**

![Screenshot 2025-04-29 200950](https://github.com/user-attachments/assets/fa231780-95c9-4fe6-a703-113869b83a02)


**Question 2**
---
-- Write a SQL query to calculate total available amount of fruits that has a price greater than 0.5 . Return total Count. 

Note: Inventory attribute contains amount of fruits

Table: fruits

name        type
----------  ----------
id          INTEGER
name        TEXT
unit        TEXT
inventory   INTEGER
price       REAL

```sql
-- select sum(inventory) as total_available_amount from fruits
where price>0.5;
```

**Output:**

![Screenshot 2025-04-29 201049](https://github.com/user-attachments/assets/6405cb15-1ad4-4928-9df8-53665693f5d2)


**Question 3**
---
--Write a SQL query to find the customer with longest name?

Table: customer

name        type
----------  ----------
id          INTEGER
name        TEXT
city        TEXT
email       TEXT
phone       INTEGER

```sql
-- select name,length(name) as length
from customer
order by length(name) desc
limit 1;
```

**Output:**

![Screenshot 2025-04-29 201141](https://github.com/user-attachments/assets/0b36cce1-b74d-4eb6-9bb4-9aada145b1d4)


**Question 4**
---
-- Write a SQL query to find the average length of names for people living in Chennai?

Table: customer

name        type
----------  ----------
id          INTEGER
name        TEXT   
city        TEXT
email       TEXT
phone       INTEGER

```sql
-- select avg(length(name)) as avg_name_length
from customer
where city='Chennai';
```

**Output:**

![Screenshot 2025-04-29 201227](https://github.com/user-attachments/assets/ea03556c-8719-41ee-96ad-b4d432e2106a)


**Question 5**
---
-- Write a SQL query to calculate total purchase amount of all orders. Return total purchase amount.

Sample table: orders

ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001

```sql
-- select sum(purch_amt) as TOTAL
from orders;
```

**Output:**

![Screenshot 2025-04-29 201310](https://github.com/user-attachments/assets/7ccbf643-66e9-4cb3-80d1-6ba0b5f609bc)


**Question 6**
---
-- Which cities (addresses) in the "customer1" table have an average salary lesser than Rs. 15000

```sql
-- select address,avg(salary) as 'AVG(salary)' 
from customer1
group by address
having avg(salary)<15000;
```

**Output:**

![Screenshot 2025-04-29 201402](https://github.com/user-attachments/assets/e027e3a5-0e8c-4fe9-ad0e-4bee98ec0042)


**Question 7**
---
-- Write a SQL Query to find how many medications are prescribed for each patient?

```sql
-- select PatientID,
       count(Medications) as AvgMedications
from  MedicalRecords      

group by PatientID; 
       
       
```

**Output:**

![Screenshot 2025-04-29 201511](https://github.com/user-attachments/assets/356df034-f74b-4006-801d-efa7c3318998)


**Question 8**
---
-- Write a SQL query to find the total number of unique cities in the customer table?

Table: customer

name        type
----------  ----------
id          INTEGER
name        TEXT
city        TEXT
email       TEXT
phone       INTEGER

```sql
-- select count(distinct(city)) as unique_cities from customer;
```

**Output:**

![Screenshot 2025-04-29 201604](https://github.com/user-attachments/assets/bd01ac13-b36e-4540-9b20-5289325f45ca)


**Question 9**
---
-- Write a SQL query to find the total income of employees aged 40 or above.

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER

```sql
-- select sum(income) as total_income from employee
where age>=40;
```

**Output:**

![Screenshot 2025-04-29 201705](https://github.com/user-attachments/assets/d9a7c58f-428f-4194-8809-78f6ffae9b7e)


**Question 10**
---
-- Write a SQL query to find the youngest employee in the company?

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER

```sql
-- select name as Employee_Name,age as Age from employee 
order by age asc
limit 1;
```

**Output:**

![Screenshot 2025-04-29 201753](https://github.com/user-attachments/assets/65e17ef4-00ce-4ac3-bfbd-1a8856145e13)

![Screenshot 2025-04-29 201906](https://github.com/user-attachments/assets/66b0a17d-8db6-4627-8d7b-6128b415eb75)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
