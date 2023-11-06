# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
# Date
# AIM:
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
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```sql
update manager set salary=salary+(salary*0.10);
```

### OUTPUT:
![271337267-fa2f6831-6cc7-4cdd-9980-414a35ad84d7](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/be98e0d0-ec28-4e01-be94-c2e5954ce3b2)

### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```sql
delete from manager where salary<2750;
```

### OUTPUT:
![271337402-3f38209d-fcab-4b61-a945-5c7634c0fc51](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/c26db94d-f055-4b2d-98c2-3fe5a0cb0001)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```sql
select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![271337665-39f1b7a0-3658-4469-a14e-e2243cb4e9ae](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/7ab35247-b2d5-4a3a-9bfb-6fd1c3bfc7cc)

### Q5)	List the names of Clerks from emp table.


### QUERY:
```sql
select ename from manager where designation='clerk';
```

### OUTPUT:![271337866-79cd7d39-9eac-4181-bb93-5d131fe83f96](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/da9457f1-4f9d-4422-9eae-415b6b84e1a8)



### Q6)	List the names of employee who are not Managers.


### QUERY:
```sql
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![271337956-d25606c3-81c6-4da3-b57d-b8d30245aaba](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/9c01298c-6190-4df3-804f-33456337be92)


### Q7)	List the names of employees not eligible for commission.

### QUERY:
```sql
select ename from manager where commission=0;
```

### OUTPUT:
![271338261-0ccff547-98fc-4093-8a12-acae07d2b3e3](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/ae9e9ee7-f253-4af1-8b27-4a01bc87a88d)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```sql
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![271338356-ab95a533-d384-4131-b5b4-1bec64ffe2e3](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/53321633-80a9-4821-9adf-22998050ebe4)

### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```sql
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:
![271338496-fe4706d0-e67b-45cc-9d8b-da1b8e5d7833](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/7d5e79a8-18a2-4dc5-a5b4-52aeface9f38)

### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```sql
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![271338623-e4583c5e-f5d1-4d98-9228-e93893b5498f](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/c12467c6-0219-4196-a4ef-8d2a22ec3b67)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```sql
select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![271338761-df211380-52ad-4687-b6bf-bd7531fdcf97](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/b50bdb60-5278-410a-a846-63a0047b6174)


### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```sql
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![271338866-65f92000-fd55-4270-bc58-2afd8cb05f2a](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/06c65c12-f6a4-4632-bbf0-720b81adeac2)

### Q13) Find number of rows in the table EMP

### QUERY:
```sql
select count(*) from manager;
```

### OUTPUT:
![271338938-1bbb5dd7-ca91-4889-a028-fca6c8818c26](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/003257aa-6d71-4e4f-9496-e56994a17f12)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```sql
select max(salary) from manager;
select min(salary) from manager;
```

### OUTPUT:
![271339050-60915d73-72b6-4d32-90![271339408-019a6523-f835-418f-a3d1-2f574adb84a7](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/5af8f9fa-02fe-4d26-bdad-579b28517c03)
92-8d2219f698c0](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/f36fe9e4-c050-49e1-88b2-a3751f987ce5)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```sql
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![271339932-e11d9e40-534f-4960-accb-40becd1c38e0](https://github.com/sivabalan28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497347/c61963c4-b972-45fa-8ddb-8d2c3299c839)

# RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
