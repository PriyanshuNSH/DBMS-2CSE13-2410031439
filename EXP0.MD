## <center><h2>Experiment 0</h2></center>

Q1. SHOWING DATABASES.
## <h4>Queries:</h4>
```sql
 SHOW DATABASES;
 ```
## <h4>Output:</h4>
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
## <h4>Queries:</h4>
```sql
 CREATE DATABASE Priyanshuj; 
```
## <h4>Output:</h4>
 ```sql
 Query OK
 ```

Q3 . SHOW THE DATABSE THAT YOU HAVE CREATED. 
## <h4>Queries:</h4>
```sql
SHOW DATABASES;
```
## <h4>Output:</h4>
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
## <h4>Queries:</h4>
```sql
USE Priyanshuj;
```
## <h4>Output:</h4>
 ```sql
 Database changed
 ```

Q5 . CREATE TABLE WITH NAME DEPARTMENT.
## <h4>Queries:</h4>
```sql
 CREATE TABLE DEPARTMENT (
      Deptno INT(2) PRIMARY KEY,
      Dname VARCHAR2(15) NOT NULL
    );
```
## <h4>Output:</h4>
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
## <h4>Queries:</h4>
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
## <h4>Output:</h4>
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
## <h4>Queries:</h4>
```sql
INSERT INTO DEPARTMENT VALUES
    (10, 'RESEARCH'),
    (20, 'ACCOUNTING'),
    (30, 'SALES'),
    (40, 'OPERATIONS');
```
## <h4>Output:</h4>
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
## <h4>Queries:</h4>
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
## <h4>Output:</h4>
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
