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
Write a SQL query to retrieve the year, month, and day from the hiredate column in the emp table.
~~~
select substr(hiredate,1,4) as Year,
substr(hiredate,6,2) as Month ,
substr (hiredate,9,2) as Day from emp;
~~~

**Output:**
<img width="837" height="356" alt="image" src="https://github.com/user-attachments/assets/b040c7b2-1af0-4fa2-bc0b-f777247a48b0" />

**Question 2**
~~~
Write a SQL query to calculate the discounted price for each product. Return product_id, original_price, discount_percentage, and discounted_price.

Sample table: Products

product_id | original_price | discount_percentage
------------+----------------+---------------------
101 | 50.00 | 0.10
102 | 75.00 | 0.15
103 | 100.00 | 0.20
~~~
~~~
select product_id,original_price,discount_percentage,original_price*(1-discount_percentage) as discounted_price from Products;
~~~

**Output:**
<img width="830" height="307" alt="image" src="https://github.com/user-attachments/assets/9500e31a-5892-48ad-a67b-a49c163e26b9" />


**Question 3**
<img width="843" height="255" alt="image" src="https://github.com/user-attachments/assets/e5a93a93-1ef4-4e68-a46c-7a3e56323d2e" />
~~~
select * from orders where not (ord_date='2012-08-17'or(customer_id>3005 and purch_amt<1000));
~~~

**Output:**
<img width="853" height="547" alt="image" src="https://github.com/user-attachments/assets/94095f97-92f3-4204-8a43-b89483e22005" />


**Question 4**
<img width="802" height="257" alt="image" src="https://github.com/user-attachments/assets/b840b23f-c623-44a8-8de7-a0993afec59e" />

~~~
select id,value1, case when cast(value1 as integer)%2=0 then 'Even' else 'Odd' end as parity from Calculations  ;
~~~

**Output:**
<img width="806" height="505" alt="image" src="https://github.com/user-attachments/assets/cc9d23db-636a-4b41-8ea3-0a299d211a80" />


**Question 5**
<img width="811" height="127" alt="image" src="https://github.com/user-attachments/assets/8b7f96d2-1920-4b60-9335-d040e9102feb" />

~~~
select * from EmployeeInfo where EmpFname not in("Sanjay","Sonia");
~~~

**Output:**
<img width="831" height="157" alt="image" src="https://github.com/user-attachments/assets/4eb27492-7fd4-4824-8a9a-76fae8e1ef49" />

**Question 6**
~~~
Write a SQL query to Delete All Doctors with a NULL Last Name

Sample table: Doctors

attributes : doctor_id, first_name, last_name, specialization
~~~
~~~
Delete from Doctors where last_name is null;
~~~

**Output:**

<img width="837" height="472" alt="image" src="https://github.com/user-attachments/assets/2bd3a32b-9a17-4367-b99e-b97ac7eb4772" />


**Question 7**
<img width="880" height="195" alt="image" src="https://github.com/user-attachments/assets/0e8f813f-8268-4f11-95c2-767310061eaf" />

~~~
delete from Customer where GRADE%2 =1;
~~~
**Output:**
<img width="878" height="251" alt="image" src="https://github.com/user-attachments/assets/b9c7219a-a349-421d-90d7-8e7334806fa6" />


**Question 8**
~~~
 Update the total selling price to quantity sold multiplied by updated selling price per unit where product id is 10 in the sales table.

SALES TABLE
name               type
-----------------  ---------------
sale_id            INT
sale_date          DATE
product_id         INT
quantity           INT
sell_price         DECIMAL(10,2)
total_sell_price   DECIMAL(10,2)
~~~
~~~
update SALES set total_sell_price=quantity*sell_price where product_id=10;
~~~

**Output:**
<img width="825" height="307" alt="image" src="https://github.com/user-attachments/assets/14159d5b-a3d7-4cd8-8792-8bb2ad4de525" />


**Question 9**
~~~
Write a SQL statement to Change the supplier name to 'A1 Suppliers' where the supplier ID is 8 in the suppliers table.

Table info

suppliers(supplier_id,supplier_name,contact_person,phone_number,email,address)
~~~
~~~
update suppliers set supplier_name='A1 Suppliers' where supplier_id=8;
~~~

**Output:**
<img width="852" height="260" alt="image" src="https://github.com/user-attachments/assets/14a255b9-5817-493b-887d-84ed0ec74f80" />


**Question 10**
~~~
Write a SQL statement to double the availability of the product with product_id 1.

products table

---------------
product_id
product_name
category_id
availability
~~~

~~~
update products set availability=availability*2 where product_id=1;
~~~

**Output:**
<img width="841" height="138" alt="image" src="https://github.com/user-attachments/assets/d20b691e-3f1a-44b5-9acf-0089720e4252" />



## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
