<center><h2>Experiment 4</h2></center>

Q1 . Display the list of employees who have joined the company before 30th June 80 or after 31st Dec 81.
## <h4>Queries:</h4>
~~~sql
SELECT * FROM EMPLOYEE
WHERE HIREDATE < '1980-06-30'
OR HIREDATE > '1981-12-31';
~~~
## <h4>Output:</h4>
```sql
+--------+------------+
| ENAME  | HIREDATE   |
+--------+------------+
| SCOTT  | 1982-12-09 |
| ADAMS  | 1983-01-12 |
| MILLER | 1982-01-23 |
+--------+------------+
3 rows in set (0.001 sec)
```

Q2 . Display the names of employees whose names have second alphabet A in their names.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE '_A%';
~~~
## <h4>Output:</h4>
```sql
+--------+
| ENAME  |
+--------+
| WARD   |
| MARTIN |
| JAMES  |
+--------+
3 rows in set (0.001 sec)
```

Q3 . Display the names of employees whose name is exactly five characters in length.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME
FROM EMPLOYEE
WHERE LENGTH(ENAME)=5;
~~~
## <h4>Output:</h4>
```sql
+--------+
| ENAME  |
+--------+
| SMITH  |
| ALLEN  |
| JONES  |
| BLAKE  |
| CLARK  |
| SCOTT  |
| ADAMS  |
| JAMES  |
+--------+
8 rows in set (0.001 sec)
```

Q4 . Display the names of employees whose names have second alphabet A in their names.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE '_A%';
~~~
## <h4>Output:</h4>
```sql
Empty set (0.001 sec)
```

Q5 . Display the names of employees who are not working as salesman or clerk or analyst.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB NOT IN ('SALESMAN','CLERK','ANALYST');
~~~
## <h4>Output:</h4>
```sql
+--------+-----------+
| ENAME  | JOB       |
+--------+-----------+
| JONES  | MANAGER   |
| BLAKE  | MANAGER   |
| CLARK  | MANAGER   |
| KING   | PRESIDENT |
+--------+-----------+
4 rows in set (0.001 sec)
```

Q6 . Display the name of the employee along with their annual salary (sal*12). The name of the employee earning highest salary should appear first.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME,
(SAL * 12) AS ANNUAL_SALARY
FROM EMPLOYEE
ORDER BY ANNUAL_SALARY DESC;
~~~
## <h4>Output:</h4>
```sql
+--------+------------+
| ENAME  | ANNUAL_SAL |
+--------+------------+
| KING   | 60000.00   |
| SCOTT  | 36000.00   |
| FORD   | 36000.00   |
| JONES  | 35700.00   |
| BLAKE  | 34200.00   |
| CLARK  | 29400.00   |
| ALLEN  | 19200.00   |
| TURNER | 18000.00   |
| MILLER | 15600.00   |
| MARTIN | 15000.00   |
| WARD   | 15000.00   |
| ADAMS  | 13200.00   |
| JAMES  | 11400.00   |
| SMITH  | 9600.00    |
+--------+------------+
14 rows in set (0.001 sec)
```

Q7 . Display name, sal, hra, pf, da, totalsal for each employee. The output should be in the order of total sal, hra 15% of sal, da 10% of sal, pf 5% of sal. Total salary will be (sal+hra+da)-pf.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME, SAL,
(SAL * 0.15) AS HRA,
(SAL * 0.05) AS PF,
(SAL * 0.10) AS DA,
((SAL + (SAL*0.15) + (SAL*0.10)) - (SAL*0.05)) AS TOTALSAL
FROM EMPLOYEE;
~~~
## <h4>Output:</h4>
```sql
+--------+------------------+
| ENAME  | SAL_INC_BY_20PER |
+--------+------------------+
| JONES  | 3570.0000       |
| BLAKE  | 3420.0000       |
| SCOTT  | 3600.0000       |
| KING   | 6000.0000       |
| FORD   | 3600.0000       |
+--------+------------------+
5 rows in set (0.001 sec)
```

Q8 . Update the salary of each employee by 10% increment who are not eligible for commission.
## <h4>Queries:</h4>
~~~sql
UPDATE EMPLOYEE
SET SAL = (SAL + IFNULL(COMM,0)) * 1.10
WHERE COMM IS NULL;
~~~
## <h4>Output:</h4>
```sql
+--------+--------+--------+--------+--------+-----------+
| ENAME  | SAL    | HRA    | DA     | PF     | TOTAL_SAL |
+--------+--------+--------+--------+--------+-----------+
| SMITH  | 800.00 | 120.00 | 80.00  | 40.00  | 960.00    |
| JAMES  | 950.00 | 142.50 | 95.00  | 47.50  | 1130.00   |
| ADAMS  | 1100.00| 165.00 |110.00  | 55.00  | 1320.00   |
| WARD   | 1250.00| 187.50 |125.00  | 62.50  | 1500.00   |
| MARTIN | 1250.00| 187.50 |125.00  | 62.50  | 1500.00   |
| MILLER | 1300.00| 195.00 |130.00  | 65.00  | 1560.00   |
| TURNER | 1500.00| 225.00 |150.00  | 75.00  | 1800.00   |
| ALLEN  | 1600.00| 240.00 |160.00  | 80.00  | 1920.00   |
| CLARK  | 2450.00| 367.50 |245.00  |122.50  | 2940.00   |
| BLAKE  | 2850.00| 427.50 |285.00  |142.50  | 3420.00   |
| JONES  | 2975.00| 446.25 |297.50  |148.75  | 3570.00   |
| FORD   | 3000.00| 450.00 |300.00  |150.00  | 3600.00   |
| SCOTT  | 3000.00| 450.00 |300.00  |150.00  | 3600.00   |
| KING   | 5000.00| 750.00 |500.00  |250.00  | 6000.00   |
+--------+--------+--------+--------+--------+-----------+
14 rows in set (0.002 sec)
```

Q9 . Display those employees whose salary is more than 3000 after giving 20% increment.
## <h4>Queries:</h4>
```sql
SELECT ENAME, SAL,
(SAL * 1.20) AS INCREMENTED_SALARY
FROM EMPLOYEE
WHERE (SAL * 1.20) > 3000;
```
## <h4>Output:</h4>
```sql
Query OK, 10 rows affected (0.002 sec)
Rows matched: 10  Changed: 10  Warnings: 0
```

Q10 . Display those employees whose salary contains atleast 3 digits.
## <h4>Queries:</h4>
```sql
SELECT ENAME, SAL
FROM EMPLOYEE
WHERE SAL >= 100;
```
## <h4>Output:</h4>
```sql
+--------+---------+
| ENAME  | SAL     |
+--------+---------+
| SMITH  | 800.00  |
| ALLEN  | 1600.00 |
| WARD   | 1250.00 |
| JONES  | 2975.00 |
| MARTIN | 1250.00 |
| BLAKE  | 2850.00 |
| CLARK  | 2450.00 |
| SCOTT  | 3000.00 |
| KING   | 5000.00 |
| TURNER | 1500.00 |
| ADAMS  | 1100.00 |
| JAMES  | 950.00  |
| FORD   | 3000.00 |
| MILLER | 1300.00 |
+--------+---------+
14 rows in set (0.001 sec)
```
