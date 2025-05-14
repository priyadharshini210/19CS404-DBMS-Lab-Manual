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
![Question1](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/Q1.png)

```sql
ALTER TABLE Student_details
ADD COLUMN Mobilenumber number;
```

**Output:**

![Output1](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/A1.png)

**Question 2**
---
![Question2](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/Q2.png)

```sql
create table Employees(
    EmployeeID INTEGER,
    FirstName TEXT,
    LastName TEXT,
    HireDate DATE
);
```

**Output:**

![Output2](https://github.com/dharun06/files/blob/main/A2.png?raw=true)

**Question 3**
---
![Question3](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/Q3.png)

```sql
insert into Employee select * from Former_employees
```

**Output:**

![Output3](https://github.com/dharun06/files/blob/main/A3.png?raw=true)

**Question 4**
---
![Question4](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/Q4.png)

```sql
alter table Companies add column designation varchar(50);
alter table Companies add column net_salary number;
alter table Companies add column dob date;

```

**Output:**

![Output4](https://github.com/dharun06/files/blob/main/A4.png?raw=true)

**Question 5**
---
![Question5](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/Q5.png)

```sql
create table Invoices(
    InvoiceID integer primary key,
    InvoiceDate date,
    DueDate date check (DueDate > InvoiceDate),
    Amount real check (Amount > 0)
);
```

**Output:**

![Output5](https://github.com/dharun06/files/blob/main/A5.png?raw=true)

**Question 6**
---
![Question6](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/Q6.png)

```sql
insert into Student_details (RollNo, Name, Gender, Subject, MARKS) VALUES (205,'Olivia Green','F','','');
insert into Student_details (RollNo, Name, Gender, Subject, MARKS) VALUES (207,'Liam Smith','M','Mathematic',85);
insert into Student_details (RollNo, Name, Gender, Subject, MARKS) VALUES (208,'Sophia Johns','F','Science','');
```

**Output:**

![Output6](https://github.com/dharun06/files/blob/main/A6.png?raw=true)

**Question 7**
---
![Question7](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/Q7.png)

```sql
create table orders(
    ord_id not null,
    item_id text not null,
    ord_date date,
    ord_qty integer,
    cost integer,
    primary key (item_id,ord_date),
    check (length(ord_id) = 4)
);
```

**Output:**

![Output7](https://github.com/dharun06/files/blob/main/A7.png?raw=true)

**Question 8**
---
![Ques8](https://github.com/dharun06/files/blob/main/Q8.png)
```sql
insert into Employee values (1,'Sarah Parker', 'Manager', 'HR', 60000)
```

**Output:**

![Output8](https://github.com/dharun06/files/blob/main/A8.png?raw=true)

**Question 9**
---
![Question9](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/Q9.png)

```sql
create table Employees(
    EmployeeID integer primary key,
    FirstName text not null,
    LastName text not null,
    Email varchar unique,
    Salary integer,
    DepartmentID integer,
    foreign key (DepartmentID) references Departments(DepartmentID),
    check (Salary > 0)
);
```

**Output:**

![Output9](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/A9.png)

**Question 10**
---
![QuestionQ](https://raw.githubusercontent.com/dharun06/files/refs/heads/main/QQ.png)

```sql
INSERT INTO Student_details (RollNo, Name, Gender) values (204, 'Samuel Black', 'M');
```

**Output:**

![Output10](https://github.com/dharun06/files/blob/main/AA.png?raw=true)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
