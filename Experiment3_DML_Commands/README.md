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
-- Write a SQL statement to Increase the selling price by 10% for all products in the 'Bakery' category in the products table.

Products table

---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id

```sql
-- update products
set sell_price=sell_price*1.10
where category ='Bakery';
```

**Output:**

![Screenshot 2025-04-29 194939](https://github.com/user-attachments/assets/404f3add-8305-439e-bb54-f8a80f22e7fd)


**Question 2**
---
--  Update the total selling price to quantity sold multiplied by updated selling price per unit where product id is 10 in the sales table.

SALES TABLE
name               type
-----------------  ---------------
sale_id            INT
sale_date          DATE
product_id         INT
quantity           INT
sell_price         DECIMAL(10,2)
total_sell_price   DECIMAL(10,2)

```sql
-- update SALES
set total_sell_price=quantity*
sell_price
where product_id=10;

```

**Output:**

![Screenshot 2025-04-29 195046](https://github.com/user-attachments/assets/7ae58d47-140a-40d0-b5bd-cc41b5ce76c2)


**Question 3**
---
--Write a SQL statement to Update the hire_date of employees in department 50 to 2024-01-24.

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id

```sql
-- update EMPLOYEES
set hire_date='2024-01-24'
where department_id=50;

```

**Output:**

![Screenshot 2025-04-29 195150](https://github.com/user-attachments/assets/7f55d94a-e537-460e-8ab8-d02cfdc66f99)


**Question 4**
---
-- Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.

Products table

---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id

```sql
-- update products 
set product_name='Premium Bread'
where product_id=5;
```

**Output:**

![Screenshot 2025-04-29 195242](https://github.com/user-attachments/assets/20a36eaf-892a-4027-865b-9a79a81af3cf)


**Question 5**
---
--For products with a profit % less than 30% of selling price, update the selling price to provide a profit margin of 35% over cost price of the product in the products table.

PRODUCTS TABLE

name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT

```sql
-- update products
set sell_price = CAST(cost_price*1.35 AS INT)
where (sell_price - cost_price) /
sell_price < 0.30;
```

**Output:**

![Screenshot 2025-04-29 195332](https://github.com/user-attachments/assets/eb84f35c-d418-4cf7-bb39-5317dd79cf09)


**Question 6**
---
-- Write a SQL query to Delete customers from 'customer' table where 'GRADE' is not equal to 3.

```sql
-- delete from customer
where grade<>3;
```

**Output:**

![Screenshot 2025-04-29 195420](https://github.com/user-attachments/assets/3b2dafc6-9153-4c91-b008-cadf15db4738)


**Question 7**
---
-- Write a SQL query to Delete a Specific Surgery whose ID is 3

Sample table: Surgeries

attributes: surgery_id, patient_id, surgeon_id, surgery_date

```sql
-- delete from surgeries
where surgery_id=3;
```

**Output:**

![Screenshot 2025-04-29 195517](https://github.com/user-attachments/assets/ddbcef13-4224-4bc5-8713-57850ad6a05a)


**Question 8**
---
-- Write a SQL query to Delete customers with 'GRADE' 3 or 'AGENT_CODE' 'A008' whose 'OUTSTANDING_AMT' is less than 5000
```sql
-- delete from customer
where (GRADE=3 or AGENT_CODE='A008')
AND OUTSTANDING_AMT<5000;
```

**Output:**

![Screenshot 2025-04-29 195612](https://github.com/user-attachments/assets/4a11a7e9-da1c-4afc-94db-8a68176307bb)


**Question 9**
---
-- Write a SQL query to remove rows from the table 'customer' with the following condition -

1. 'cust_country' must be 'India',

2. 'cus_city' must not be 'Chennai',

```sql
-- DELETE FROM customer
where cust_country='India' and 
cust_city<>'Chennai';
```

**Output:**

![Screenshot 2025-04-29 195716](https://github.com/user-attachments/assets/d990f709-be32-402a-8562-c5ba22abd03c)


**Question 10**
---
--Write a SQL query to Delete customers from 'customer' table where 'CUST_COUNTRY' is neither 'India' nor 'USA'.

```sql
-- delete from customer
where cust_country not in ('India','USA');
```

**Output:**

![Screenshot 2025-04-29 195807](https://github.com/user-attachments/assets/a495bf72-0e47-45ca-927b-9dea6457c6d3)

![Screenshot 2025-04-29 195936](https://github.com/user-attachments/assets/2c6f1206-126a-4a9e-97b2-b769ec3e086d)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
