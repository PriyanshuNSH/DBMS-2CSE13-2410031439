<<<<<<< HEAD
=======
## Experiment 1

Q1. SHOWING DATABASES.
# Queries
```sql
 SHOW DATABASES;
 ```
 # Output
 ```sql
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
5 rows in set (0.006 sec)
```
Q2 . CREATE DATABASE WITH YOUR NAME. 
# Queries
```sql
 CREATE DATABASE Priyanshuj; 
```
 # Output
 ```sql
 Query OK
 ```

Q3 . SHOW THE DATABSE THAT YOU HAVE CREATED. 
# Queries
```sql
SHOW DATABASES;
```
 # Output
 ```sql
+--------------------+
| Database           |
+--------------------+
| company            |
| hackers            |
| iilm               |
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| priyanshuj         |
| test               |
+--------------------+
9 rows in set (0.056 sec)
 ```

Q4 . USE THE DATABASE THAT YOU HAVE CREATED.
# Queries
```sql
USE Priyanshuj;
```
 # Output
 ```sql
 Database changed
 ```

Q5 . CREATE TABLE WITH NAME DEPARTMENT.
# Queries
```sql
 CREATE TABLE DEPARTMENT (
      Deptno INT(2) PRIMARY KEY,
      Dname VARCHAR2(15) NOT NULL
    );
```
 # Output
 ```sql
 +--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| deptno | int(2)      | NO   | PRI | NULL    |       |
| dname  | varchar(15) | NO   |     | NULL    |       |
+--------+-------------+------+-----+---------+-------+
2 rows in set (0.041 sec)
 ```

Q6 . CREATE TABLE WITH NAME EMPLOYEE.
# Queries
```sql
CREATE TABLE EMPLOYEE (
    EMPNO INT PRIMARY KEY,
    ENAME VARCHAR2(20) NOT NULL,
    JOB VARCHAR2(20),
    MGR INT,
    HIREDATE DATE,
    SAL DECIMAL(10,2),
    COMM DECIMAL(10,2),
    DEPTNO INT,
    FOREIGN KEY (DEPTNO) REFERENCES DEPARTMENT(Deptno)
    );
```
 # Output
 ```sql
 +----------+---------------+------+-----+---------+-------+
| Field    | Type          | Null | Key | Default | Extra |
+----------+---------------+------+-----+---------+-------+
| empno    | int(4)        | NO   | PRI | NULL    |       |
| ename    | varchar(20)   | NO   |     | NULL    |       |
| job      | varchar(20)   | YES  |     | NULL    |       |
| mgr      | int(4)        | YES  |     | NULL    |       |
| hiredate | date          | YES  |     | NULL    |       |
| sal      | decimal(10,2) | YES  |     | NULL    |       |
| comm     | decimal(7,2)  | YES  |     | NULL    |       |
| deptno   | int(2)        | YES  | MUL | NULL    |       |
+----------+---------------+------+-----+---------+-------+
8 rows in set (0.018 sec)
 ```

Q7 . INSERTING VALUES IN DEPARTMENT TABLE.
# Queries
```sql
INSERT INTO DEPARTMENT VALUES
    (10, 'RESEARCH'),
    (20, 'ACCOUNTING'),
    (30, 'SALES'),
    (40, 'OPERATIONS');
```
 # Output
 ```sql
+--------+------------+ 
| Deptno | Dname      |
+--------+------------+
| 10     | RESEARCH   |
| 20     | ACCOUNTING |
| 30     | SALES      |
| 40     | OPERATIONS |
+--------+------------+
 ```

Q8 . INSERTING VALUES IN EMPLOYEE TABLE.
# Queries
```sql
 INSERT INTO EMPLOYEE VALUES
     (7369,'SMITH','CLERK',7902,'1980-12-17',800,NULL,20),
     (7499,'ALLEN','SALESMAN',7698,'1981-02-20',1600,300,30),
     (7521,'WARD','SALESMAN',7698,'1981-02-22',1250,300,30),
     (7566,'JONES','MANAGER',7839,'1981-04-02',2975,NULL,20),
     (7654,'MARTIN','SALESMAN',7698,'1981-09-28',1250,1400,30),
     (7698,'BLAKE','MANAGER',7839,'1981-05-01',2850,NULL,30),
     (7782,'CLARK','MANAGER',7839,'1981-06-09',2450,NULL,10),
     (7788,'SCOTT','ANALYST',7566,'1982-12-09',3000,NULL,40),
     (7839,'KING','PRESIDENT',NULL,'1981-11-17',5000,NULL,20),
     (7844,'TURNER','SALESMAN',7698,'1981-09-08',1500,0,30),
     (7876,'ADAMS','CLERK',7788,'1983-01-12',1100,NULL,20),
     (7900,'JAMES','CLERK',7698,'1981-12-03',950,NULL,30),
     (7902,'FORD','ANALYST',7566,'1981-12-03',3000,NULL,20),
     (7934,'MILLER','CLERK',7782,'1982-01-23',1300,NULL,10);
```
 # Output
 ```sql
+-------+--------+-----------+------+------------+------+------+--------+ 
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
| ----- | ------ | --------- | ---- | ---------- | ---- | ---- | ------ |
| 7369  | SMITH  | CLERK     | 7902 | 1980-12-17 | 800  | NULL | 20     |
| 7499  | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600 | 300  | 30     |
| 7521  | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250 | 300  | 30     |
| 7566  | JONES  | MANAGER   | 7839 | 1981-04-02 | 2975 | NULL | 20     |
| 7654  | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250 | 1400 | 30     |
| 7698  | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850 | NULL | 30     |
| 7782  | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2450 | NULL | 10     |
| 7788  | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000 | NULL | 40     |
| 7839  | KING   | PRESIDENT | NULL | 1981-11-17 | 5000 | NULL | 20     |
| 7844  | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500 | 0    | 30     |
| 7876  | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1100 | NULL | 20     |
| 7900  | JAMES  | CLERK     | 7698 | 1981-12-03 | 950  | NULL | 30     |
| 7902  | FORD   | ANALYST   | 7566 | 1981-12-03 | 3000 | NULL | 20     |
| 7934  | MILLER | CLERK     | 7782 | 1982-01-23 | 1300 | NULL | 10     |
+-------+--------+-----------+------+------------+------+------+--------+
 ```

Q9 . Create Employee_master table with data using EMPLOYEE table.
# Queries
```sql
CREATE TABLE Employee_master AS
SELECT * FROM Employee;
```
 # Output
 ```sql
+-------+--------+-----------+------+------------+------+------+--------+ 
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
| ----- | ------ | --------- | ---- | ---------- | ---- | ---- | ------ |
| 7369  | SMITH  | CLERK     | 7902 | 1980-12-17 | 800  | NULL | 20     |
| 7499  | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600 | 300  | 30     |
| 7521  | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250 | 300  | 30     |
| 7566  | JONES  | MANAGER   | 7839 | 1981-04-02 | 2975 | NULL | 20     |
| 7654  | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250 | 1400 | 30     |
| 7698  | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850 | NULL | 30     |
| 7782  | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2450 | NULL | 10     |
| 7788  | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000 | NULL | 40     |
| 7839  | KING   | PRESIDENT | NULL | 1981-11-17 | 5000 | NULL | 20     |
| 7844  | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500 | 0    | 30     |
| 7876  | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1100 | NULL | 20     |
| 7900  | JAMES  | CLERK     | 7698 | 1981-12-03 | 950  | NULL | 30     |
| 7902  | FORD   | ANALYST   | 7566 | 1981-12-03 | 3000 | NULL | 20     |
| 7934  | MILLER | CLERK     | 7782 | 1982-01-23 | 1300 | NULL | 10     |
+-------+--------+-----------+------+------------+------+------+--------+
 ```

Q10 . Delete all records from Employee_master where DeptNo is 10.
# Queries
```sql
DELETE FROM Employee_master
WHERE DEPTNO = 10;
```
 # Output
 ```sql
 Query OK, 1 row affected (0.008 sec)
 ```

Q11 . Update 10% hike in salary of DEPTNO 20 in Employee_master.
# Queries
```sql
UPDATE Employee_master
SET SAL = SAL + (SAL * 0.10)
WHERE DEPTNO = 20;
```
 # Output
 ```sql
 Query OK, 6 rows affected (0.011 sec)
Rows matched: 6  Changed: 6  Warnings: 0
 ```

Q12 . Alter SAL with size (12,2) in Employee_master.
# Queries
```sql
 ALTER TABLE Employee_master
MODIFY SAL DECIMAL(12,2);
```
 # Output
 ```sql
 Query OK, 13 rows affected (0.140 sec)
Records: 13  Duplicates: 0  Warnings: 0
 ```

Q13 . Drop Employee_master table.
# Queries
```sql
DROP TABLE Employee_master;
```
# Output
```sql
 Query OK, 0 rows affected (0.019 sec) 
 ```
>>>>>>> 91ac9a4e50a5f5c004fd0f0017ddcb44e7524d40
