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
Write a SQL statement to Update the grade of all customers in Chennai city as  5. 

```sql
UPDATE customer
    SET grade=5
WHERE city='Chennai'
```

**Output:**

<img width="1301" height="407" alt="image" src="https://github.com/user-attachments/assets/8d6bc16f-ff3c-4cec-b18e-b746cd8a6cf1" />


**Question 2**
---
Write a SQL statement to Update the per_unit_price to 25 and total_price accordingly in purchases table where purchase_date is '2022-08-15' and product_id is 12.

```sql
UPDATE purchases
SET per_unit_price= 25,
    total_price=25*quantity
WHERE purchase_date='2022-08-15'
AND product_id='12';
```

**Output:**

<img width="1345" height="252" alt="image" src="https://github.com/user-attachments/assets/8a391ef7-6ad8-4ae8-8c50-534e5d3f5efe" />


**Question 3**
---
Update the reorder level to 40 pieces for all products belonging to the 'Grocery' category in the products table.

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
UPDATE products
SET reorder_lvl=40
WHERE category='Grocery';
```

**Output:**



**Question 4**
---
Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.

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
UPDATE products
SET product_name='Premium Bread'
WHERE product_id='5';
```

**Output:**

<img width="1351" height="187" alt="image" src="https://github.com/user-attachments/assets/d8895ca1-b021-4cde-a4c4-855d3d1f66d3" />


**Question 5**
---
Write a SQL statement to change the EMAIL and COMMISSION_PCT column of the following EMPLOYEES table with 'not available' and 0.55 for those employees whose DEPARTMENT_ID is 110.

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
UPDATE Employees
SET email='not available',
    commission_pct='0.55'
WHERE department_id='110';
```

**Output:**

<img width="1295" height="240" alt="image" src="https://github.com/user-attachments/assets/7d148cc9-5bea-4cfa-bcee-d88a577eb86a" />


**Question 6**
---
Write a SQL query to Delete customers from 'customer' table where 'CUST_COUNTRY' is neither 'India' nor 'USA'.

```sql
DELETE FROM customer
WHERE CUST_COUNTRY NOT IN ('India','USA');
```

**Output:**

<img width="1031" height="150" alt="image" src="https://github.com/user-attachments/assets/322d3920-9371-411e-bcd0-d56b5740a4a3" />


**Question 7**
---
Write a SQL query to Delete a Specific Surgery whose ID is 3

```sql
DELETE FROM surgeries 
WHERE surgery_id=3;
```

**Output:**

<img width="1150" height="314" alt="image" src="https://github.com/user-attachments/assets/9dc7030e-71f5-4b89-b4cc-3c44563b31b6" />


**Question 8**
---
Write a SQL query to Delete All Doctors with a NULL Last Name

```sql
DELETE FROM doctors 
WHERE last_name IS NULL;
```

**Output:**

<img width="1217" height="623" alt="image" src="https://github.com/user-attachments/assets/c506903e-4ae7-481c-be73-d12eac707ce4" />


**Question 9**
---
Write a SQL query to Delete customers with 'GRADE' 3 or 'AGENT_CODE' 'A008' whose 'OUTSTANDING_AMT' is less than 5000
```sql
DELETE FROM customer
WHERE (GRADE=3 OR AGENT_CODE='A008')
AND OUTSTANDING_AMT<5000;
```

**Output:**

<img width="1054" height="125" alt="image" src="https://github.com/user-attachments/assets/bc15ec92-b789-46cb-b23f-b95fc2e914bc" />


**Question 10**
---
Write a SQL query to Delete customers with 'GRADE' 3 and whose 'CUST_NAME' contains the substring 'BBB', and 'PAYMENT_AMT' is greater than 2000

```sql
DELETE FROM customer
WHERE GRADE=3 
    AND CUST_NAME LIKE '%BBB%'
    AND PAYMENT_AMT>2000;
```

**Output:**
<img width="1035" height="159" alt="image" src="https://github.com/user-attachments/assets/4cbe19c4-7fc7-4476-b619-d9b0d8a62b5a" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

<img width="1427" height="543" alt="image" src="https://github.com/user-attachments/assets/52244d4c-802e-4b26-a728-9df4b5560154" />

