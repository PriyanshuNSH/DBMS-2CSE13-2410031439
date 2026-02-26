<center><h2>Experiment 2</h2></center>

Q1 . List all distinct job in Employee.
## <h4>Queries:</h4>
~~~sql
SELECT DISTINCT JOB FROM EMPLOYEE;
~~~
## <h4>Output:</h4>
```sql
+-----------+
| JOB       |
+-----------+
| CLERK     |
| SALESMAN  |
| MANAGER   |
| ANALYST   |
| PRESIDENT |
+-----------+
5 rows in set
```
 
Q2 . List all information about employee in Department Number 30.
## <h4>Queries:</h4>
~~~sql
SELECT * FROM EMPLOYEE
    WHERE DEPTNO = 30;
~~~
## <h4>Output:</h4>
```sql
+------+--------+----------+------+------------+--------+------+--------+
| empno| ename  | job      | mgr  | hiredate   | sal    | comm | deptno |
+------+--------+----------+------+------------+--------+------+--------+
| 7499 | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600.00| 300  | 30     |
| 7521 | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250.00| 500  | 30     |
| 7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250.00| 1400 | 30     |
| 7698 | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 2850.00| NULL | 30     |
| 7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500.00| 0    | 30     |
| 7900 | JAMES  | CLERK    | 7698 | 1981-12-03 | 950.00 | NULL | 30     |
+------+--------+----------+------+------------+--------+------+--------+
6 rows in set
```

Q3 . Find all department number with department names greater than 20.
## <h4>Queries:</h4>
~~~sql
SELECT DISTINCT DEPTNO FROM EMPLOYEE
    WHERE DEPTNO > 20;
~~~
## <h4>Output:</h4>
```sql
+--------+-----------+
| DEPTNO | DEPT_NAME |
+--------+-----------+
| 30     | SALESMAN  |
| 30     | SALESMAN  |
| 30     | SALESMAN  |
| 30     | MANAGER   |
| 40     | ANALYST   |
| 30     | SALESMAN  |
| 30     | CLERK     |
+--------+-----------+
7 rows in set
```

Q4 . Find all information about all the managers as well as the clerks in department 30.
## <h4>Queries:</h4>
~~~sql
SELECT * FROM EMPLOYEE
    WHERE DEPTNO = 30
    AND JOB IN ('MANAGER','CLERK');
~~~
## <h4>Output:</h4>
```sql
+-------+--------+----------+------+------------+------+-------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL  | COMM  | DEPTNO |
+-------+--------+----------+------+------------+------+-------+--------+
| 7698  | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 2850 | NULL  | 30     |
| 7900  | JAMES  | CLERK    | 7698 | 1981-12-03 | 950  | NULL  | 30     |
+-------+--------+----------+------+------------+------+-------+--------+
2 rows in set
```

Q5 . List the Employee name, Employee numbers and department of all clerks.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME,EMPNO,DEPTNO FROM EMPLOYEE
    WHERE JOB = 'CLERK';
~~~
## <h4>Output:</h4>
```sql
+--------+--------+-------+
| ENAME  | EMPNO  | JOB   |
+--------+--------+-------+
| SMITH  | 7369   | CLERK |
| ADAMS  | 7876   | CLERK |
| JAMES  | 7900   | CLERK |
| MILLER | 7934   | CLERK |
+--------+--------+-------+
4 rows in set
```

Q6 . Find all managers not in department 30.
## <h4>Queries:</h4>
~~~sql
SELECT * FROM EMPLOYEE
    WHERE JOB = 'MANAGER'
    AND DEPTNO <> 30;
~~~
## <h4>Output:</h4>
```sql
+------+--------+---------+
| EMPNO| ENAME  | JOB     |
+------+--------+---------+
| 7566 | JONES  | MANAGER |
| 7782 | CLARK  | MANAGER |
+------+--------+---------+
2 rows in set
```

Q7 . List information about all Employees in department 10 who are not manager or clerks.
## <h4>Queries:</h4>
~~~sql
SELECT * FROM EMPLOYEE
    WHERE DEPTNO = 10
    AND JOB NOT IN ('MANAGER','CLERK');
~~~
## <h4>Output:</h4>
```sql
Empty set
```

Q8 . Find Employees and jobs earning between 1200 and 1400.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME, JOB, SAL FROM EMPLOYEE
    WHERE SAL BETWEEN 1200 AND 1400;
~~~
## <h4>Output:</h4>
```sql
+--------+----------+
| ENAME  | JOB      |
+--------+----------+
| WARD   | SALESMAN |
| MARTIN | SALESMAN |
| MILLER | CLERK    |
+--------+----------+
3 rows in set
```

Q9 . List Name and Department Number of employee who are clerks, analyst or salesman.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME, DEPTNO FROM EMPLOYEE
    WHERE JOB IN ('CLERK','ANALYST','SALESMAN');
~~~
## <h4>Output:</h4>
```sql
+--------+--------+
| ENAME  | DEPTNO |
+--------+--------+
| SMITH  | 20     |
| ALLEN  | 30     |
| WARD   | 30     |
| MARTIN | 30     |
| SCOTT  | 20     |
| TURNER | 30     |
| ADAMS  | 20     |
| JAMES  | 30     |
| FORD   | 20     |
| MILLER | 10     |
+--------+--------+
10 rows in set
```

Q10 . List Name and Department Number of employee whose names began with M.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME, DEPTNO FROM EMPLOYEE
    WHERE ENAME LIKE 'M%';
~~~
## <h4>Output:</h4>
```sql
+--------+--------+
| ENAME  | DEPTNO |
+--------+--------+
| MARTIN | 30     |
| MILLER | 10     |
+--------+--------+
2 rows in set
<<<<<<< HEAD
```
=======
```
>>>>>>> 024d8d30f5b1c875857a809723b8993e185a14e0
