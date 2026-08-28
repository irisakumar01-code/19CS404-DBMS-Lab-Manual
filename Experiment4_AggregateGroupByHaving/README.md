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
<img width="815" height="180" alt="image" src="https://github.com/user-attachments/assets/f3da6546-9ffe-4033-aad3-e8d35e0718a8" />

~~~
select PatientID, count(*)  as TotalMedications from Prescriptions group by PatientID;
~~~

**Output:**

<img width="762" height="782" alt="image" src="https://github.com/user-attachments/assets/4ed408d6-1a8e-4b28-a851-b83d6e912d11" />


**Question 2**
~~~
Write a SQL query to find the total number of unique cities in the customer table?

Table: customer

name        type
----------  ----------
id          INTEGER
name        TEXT
city        TEXT
email       TEXT
phone       INTEGER
~~~

~~~
select count(distinct city) as unique_cities from customer;
~~~

**Output:**

<img width="612" height="391" alt="image" src="https://github.com/user-attachments/assets/68f6d67b-2cb1-4761-aef3-0eff28a83d2c" />


**Question 3**
---
<img width="823" height="201" alt="image" src="https://github.com/user-attachments/assets/d57a9d21-ad63-475c-8c01-899c964dcf1b" />

~~~
select Address ,count(*) as TotalPatients from Patients group by Address;
~~~

**Output:**
<img width="732" height="448" alt="image" src="https://github.com/user-attachments/assets/9259f916-ae1b-4857-b3e1-b9b9e169c42e" />


**Question 4**
~~~
What is the average duration of insurance coverage for patients covered by each insurance company?

Sample table:Insurance Table

name               type
-----------------  ----------
InsuranceID        INTEGER
PatientID          INTEGER
InsuranceCompany   TEXT
PolicyNumber       TEXT
PolicyHolder       TEXT
StartDate          DATE
EndDate            DATE
~~~

~~~
select InsuranceCompany,avg(EndDate-StartDate) as AvgCoverageDurationDays from Insurance group by InsuranceCompany;
~~~

**Output:**

<img width="822" height="576" alt="image" src="https://github.com/user-attachments/assets/e864550b-b015-453e-aeaa-b6299301d17f" />


**Question 5**
<img width="827" height="236" alt="image" src="https://github.com/user-attachments/assets/bfffdd09-abf8-4d89-8853-b1459649b7e2" />

~~~
select count(*) as COUNT from customer where city!='Noida';
~~~

**Output:**

<img width="447" height="387" alt="image" src="https://github.com/user-attachments/assets/42a371ad-9c2b-40cb-b3bd-d251718c16e8" />


**Question 6**
---
<img width="797" height="172" alt="image" src="https://github.com/user-attachments/assets/63d5e3b9-16c7-4258-994a-48b680019341" />

~~~
select jdate,max(workhour) as "MAX(workhour)" from employee1 group by jdate having max(workhour)>12;
~~~

**Output:**
<img width="765" height="463" alt="image" src="https://github.com/user-attachments/assets/8c91ad76-5d02-40f9-803e-3e592e691718" />


**Question 7**
---
<img width="817" height="187" alt="image" src="https://github.com/user-attachments/assets/f7f9a751-aa04-460e-a507-aea8ded7d284" />

~~~
select category_id, sum(price) as Total_Cost from products group by category_id having Total_Cost>50;
~~~

**Output:**

<img width="782" height="437" alt="image" src="https://github.com/user-attachments/assets/e5375105-f15c-4d7c-94ce-65027a88b6ee" />


**Question 8**
---
<img width="823" height="172" alt="image" src="https://github.com/user-attachments/assets/2c63054d-8396-4761-9d29-424bdea81aa6" />

~~~
select (age/5)*5 as age_group, min(salary) as "MIN(salary)" from customer1 group by (age/5)*5 having min(salary)<2000;
~~~

**Output:**

<img width="770" height="435" alt="image" src="https://github.com/user-attachments/assets/34cac9a9-4d7e-4b98-a414-6818419c77f8" />


**Question 9**

~~~
Write a SQL query to find  how many employees work in California?

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER

~~~

~~~
select count(*) as employees_in_california from employee where city='California';
~~~

**Output:**

<img width="751" height="388" alt="image" src="https://github.com/user-attachments/assets/868a5999-6be8-403d-8279-cf065a99caa5" />


**Question 10**
~~~
Write a SQL query to Calculate the average income of the employees with names starting with 'A': 

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER
~~~
~~~
select avg(income) as avg_income from employee where name like 'A%';
~~~

**Output:**

<img width="541" height="418" alt="image" src="https://github.com/user-attachments/assets/28e8c5bd-d64a-4bbb-8fc2-8e2619b3a973" />

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
