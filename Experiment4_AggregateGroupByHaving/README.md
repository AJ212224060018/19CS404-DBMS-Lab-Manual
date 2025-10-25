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
What is the average dosage prescribed for each medication?

Sample tablePrescriptions Table

```sql
SELECT 
Medication,
AVG(Dosage) AS AvgDosage
FROM Prescriptions
GROUP BY Medication;

```

**Output:**

<img width="643" height="749" alt="image" src="https://github.com/user-attachments/assets/0a823554-98db-49ce-a503-f1563ed5e28e" />

**Question 2**
---
What is the count of male and female patients?

Sample table: Patients Table

```sql
SELECT Gender,
COUNT(PatientID) AS TotalPatients
FROM Patients
GROUP BY Gender;
```

**Output:**

<img width="786" height="355" alt="image" src="https://github.com/user-attachments/assets/9a8be54b-0983-40d6-8036-f6a136331085" />

**Question 3**
---
How many male and female doctors are there in each medical specialty?

Sample table:Doctors Table
```sql
SELECT Specialty,
Gender,
COUNT(*) AS TotalDoctors
FROM Doctors
GROUP BY Specialty,Gender;
```

**Output:**

<img width="925" height="631" alt="image" src="https://github.com/user-attachments/assets/46596a0c-56e7-4361-b79c-b771852c96ae" />

**Question 4**
---
Write a SQL query to calculate the total number of working hours of all employees

Sample table: employee1

```sql
SELECT SUM(workhour) AS 'Total working hours'
FROM employee1;
```

**Output:**

<img width="718" height="304" alt="image" src="https://github.com/user-attachments/assets/0ea27b2f-8147-4556-b7c4-00dbfd3781a6" />

**Question 5**
---
Write a SQL query to find the minimum purchase amount.

Sample table: orders

```sql
SELECT MIN(purch_amt) AS 'MINIMUM'
FROM orders;
```

**Output:**

<img width="511" height="279" alt="image" src="https://github.com/user-attachments/assets/a534cff7-28ae-4194-ba3b-7ec3e7d9b890" />

**Question 6**
---
Write a SQL query to calculate total available amount of fruits that has a price greater than 0.5 . Return total Count. 

Note: Inventory attribute contains amount of fruits

```sql
SELECT SUM(inventory) AS 'total_available_amount'
FROM fruits
WHERE price>0.5;
```

**Output:**

<img width="584" height="292" alt="image" src="https://github.com/user-attachments/assets/46e026ea-04f8-41f8-910e-92d5abd813a0" />


**Question 7**
---
Write a SQL query to find the total income of employees aged 40 or above.

Table: employee

```sql
SELECT SUM(income) AS 'total_income'
FROM employee
WHERE age>=40;
```

**Output:**

<img width="390" height="293" alt="image" src="https://github.com/user-attachments/assets/b489c2bf-cc0c-448e-a9a1-92a4ec46ba91" />

**Question 8**
---
Write the SQL query that achieves the grouping of data by city, calculates the total income for each city, and includes only those cities where the total income sum is greater than 200,000.

Sample table: employee

```sql
SELECT 
    city,
    SUM(income) AS 'Income'
FROM employee
GROUP BY city
HAVING SUM(income)>200000;
```

**Output:**

<img width="654" height="511" alt="image" src="https://github.com/user-attachments/assets/a0f77b91-d5e0-42b9-b76f-58d07ce6a78e" />

**Question 9**
---
Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the average work hours for each date, and excludes dates where the average work hour is not less than 10.

Sample table: employee1

```sql
SELECT 
    jdate,
    AVG(workhour) AS 'AVG(workhour)'
FROM employee1
GROUP BY jdate
HAVING AVG(workhour)<10;
```

**Output:**

<img width="688" height="323" alt="image" src="https://github.com/user-attachments/assets/18aa8b87-2baf-418b-95a2-22efee2bd10f" />

**Question 10**
---
Write SQL query to extract the email domain from each patient's email address and count the number of patients with the same email domain.

Sample table: Patients Table

```sql
SELECT 
    SUBSTR(email, INSTR(email, '@') + 1) AS EmailDomain,
    COUNT(*) AS TotalPatients
FROM Patients
GROUP BY EmailDomain;
```

**Output:**

<img width="732" height="340" alt="image" src="https://github.com/user-attachments/assets/5341855f-6fa4-43cb-bbf1-6967a4e6ddd4" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

<img width="1426" height="404" alt="image" src="https://github.com/user-attachments/assets/df9675cc-de4b-483a-935a-7e8104573c8e" />

