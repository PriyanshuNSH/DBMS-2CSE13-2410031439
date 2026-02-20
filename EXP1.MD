## <center><h2>Experiment 1</h2></center>

Q1 . Create Employee_master table with data using EMPLOYEE table.
## <h4>Queries:</h4>
```sql
CREATE TABLE Employee_master AS
SELECT * FROM Employee;
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

Q2 . Delete all records from Employee_master where DeptNo is 10.
## <h4>Queries:</h4>
```sql
DELETE FROM Employee_master
WHERE DEPTNO = 10;
```
## <h4>Output:</h4>
 ```sql
 Query OK, 1 row affected (0.008 sec)
 ```

Q3 . Update 10% hike in salary of DEPTNO 20 in Employee_master.
## <h4>Queries:</h4>
```sql
UPDATE Employee_master
SET SAL = SAL + (SAL * 0.10)
WHERE DEPTNO = 20;
```
## <h4>Output:</h4>
 ```sql
 Query OK, 6 rows affected (0.011 sec)
Rows matched: 6  Changed: 6  Warnings: 0
 ```

Q4 . Alter SAL with size (12,2) in Employee_master.
## <h4>Queries:</h4>
```sql
 ALTER TABLE Employee_master
MODIFY SAL DECIMAL(12,2);
```
## <h4>Output:</h4>
 ```sql
 Query OK, 13 rows affected (0.140 sec)
Records: 13  Duplicates: 0  Warnings: 0
 ```

Q5 . Drop Employee_master table.
## <h4>Queries:</h4>
```sql
DROP TABLE Employee_master;
```
## <h4>Output:</h4>
```sql
 Query OK, 0 rows affected (0.019 sec) 
 ```
