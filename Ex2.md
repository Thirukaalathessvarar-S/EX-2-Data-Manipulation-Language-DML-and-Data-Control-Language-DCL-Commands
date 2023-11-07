# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL

## Date: 10.08.2023

## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```
insert into manager values(1269,'Eswar',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(1239,'Sai',3000,400,36000,'1-Jul-82','manager',null,'Sathya');
insert into manager values(1234,'Perumal',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(1288,'Lingesh',4000,0,48000,'12-Aug-82','clerk',50,'Prem');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
![ella1](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/c089b570-a46f-4486-8f26-3a36e47a9988)

### OUTPUT:
![ella2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/0a8aff9f-62e6-4269-abd2-24ed52175960)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
![ella3](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/4082d89b-2bd8-4bf1-b949-e590adc10b40)

### OUTPUT:
![ella4](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/09980056-f8b4-4b36-9492-28e022fa6a4e)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![dbms5_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/1e8ddc37-483e-4b0c-9e74-b7e802d25990)

### Q4)	List the names of Clerks from emp table.

### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:
![dbms6_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/3da43b99-b565-49c7-821f-e1a562eebb43)

### Q5)	List the names of employee who are not Managers.

### QUERY:
```
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![dbms7_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/dfebed16-540b-42a5-98e9-5c7c75f5d974)

### Q6)	List the names of employees not eligible for commission.

### QUERY:
```
select ename from manager where commission=0;
```

### OUTPUT:
![dbms8_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/657b1323-83d0-4cfc-9e3e-d2d26ae99b12)


### Q7)	List employees whose name either start or end with ‘s’.

### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![dbms9_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/89fd69ba-a804-4a74-9499-18a41a7e8179)

### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:
![dbms10_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/0b4da519-a9ae-48a5-a807-c0a824c591ce)

### Q9) List the Details of Employees who have joined before 30 Sept 81.

### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![dbms11_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/0a68c2c2-0d85-4b45-bc69-78315dd4a3d5)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![dbms12_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/d74effd2-fdc2-4988-9f9d-5d01ea7d8768)

### Q11) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![dbms13_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/9cd09459-6942-495d-90d4-69acfe898044)

### Q12) Find number of rows in the table EMP

### QUERY:
```
select count(*) from manager;
```

### OUTPUT:
![dbms14_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/28333e4e-aea9-41fb-aa7f-6db903a72f26)

### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select max(salary) from manager;
```

### OUTPUT:
![dbms15_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/25ee0456-044f-4ae2-adf3-b6559b8655b7)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![dbms16_exp2](https://github.com/Thirukaalathessvarar-S/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121166390/f7b746a9-2ecf-4d07-b04d-bc189b256368)

## RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
