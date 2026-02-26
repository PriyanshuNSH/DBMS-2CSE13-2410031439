<center><h2>Experiment 7</h2></center>

Q1 . Compute the number of days remaining this year.
## <h4>Queries:</h4>
```sql
 SELECT DATEDIFF(
    STR_TO_DATE(CONCAT(YEAR(CURDATE()),'-12-31'),'%Y-%m-%d'),
    CURDATE()
) AS days_remaining;
```
## <h4>Output:</h4>
 ```sql 
+----------------+
| days_remaining |
+----------------+
|            315 |
+----------------+
1 row in set (0.000 sec)
```
Q2 . Find the highest and lowest salaries and the difference between of them.
## <h4>Queries:</h4>
 ```sql
 SELECT 
MAX(sal) AS highest_salary,
MIN(sal) AS lowest_salary,
MAX(sal) - MIN(sal) AS difference
FROM employee;
```
## <h4>Output:</h4>
 ```sql
+----------------+---------------+------------+
| highest_salary | lowest_salary | difference |
+----------------+---------------+------------+
|        5500.00 |        880.00 |    4620.00 |
+----------------+---------------+------------+
1 row in set (0.060 sec)
```
Q3 . List employee whose commission is greater than 25% of their salaries.
## <h4>Queries:</h4>
 ```sql
 SELECT *
    -> FROM employee
    -> WHERE comm > (sal * 0.25);
```
## <h4>Output:</h4>
 ```sql    
+-------+--------+----------+------+------------+---------+---------+--------+
| empno | ename  | job      | mgr  | hiredate   | sal     | comm    | deptno |
+-------+--------+----------+------+------------+---------+---------+--------+
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250.00 | 1400.00 |     30 |
+-------+--------+----------+------+------------+---------+---------+--------+
1 row in set (0.001 sec)
```
Q4 . Make a query that displays salary in doller formet.
## <h4>Queries:</h4>
 ```sql
 SELECT ename,
CONCAT('$', FORMAT(sal,2)) AS salary_in_dollar
FROM employee;
```
## <h4>Output:</h4>
 ```sql
 +--------+------------------+
| ename  | salary_in_dollar |
+--------+------------------+
| SMITH  | $880.00          |
| ALLEN  | $1,600.00        |
| WARD   | $1,250.00        |
| JONES  | $3,272.50        |
| MARTIN | $1,250.00        |
| BLAKE  | $3,135.00        |
| CLARK  | $2,695.00        |
| SCOTT  | $3,300.00        |
| KING   | $5,500.00        |
| TURNER | $1,500.00        |
| ADAMS  | $1,210.00        |
| JAMES  | $1,045.00        |
| FORD   | $3,300.00        |
| MILLER | $1,430.00        |
+--------+------------------+
14 rows in set (0.073 sec)
0
```

Q5 . Create a matrix query to display the job, the salary for that job based on department number, and the total salary for that job for all departments, giving each column an appropriate heading.
## <h4>Queries:</h4>
 ```sql
 SELECT JOB,
       SUM(CASE WHEN DEPTNO = 10 THEN SAL END) AS "DEPT_10",
       SUM(CASE WHEN DEPTNO = 20 THEN SAL END) AS "DEPT_20",
       SUM(CASE WHEN DEPTNO = 30 THEN SAL END) AS "DEPT_30",
       SUM(SAL) AS "TOTAL_SALARY"
FROM EMPLOYEE
GROUP BY JOB;
 ```
 ## <h4>Output:</h4>
 ```sql
 +-----------+---------+---------+---------+--------------+
| JOB       | DEPT_10 | DEPT_20 | DEPT_30 | TOTAL_SALARY |
+-----------+---------+---------+---------+--------------+
| ANALYST   |    NULL | 3300.00 |    NULL |      6600.00 |
| CLERK     | 1430.00 | 2090.00 | 1045.00 |      4565.00 |
| MANAGER   |    NULL | 5967.50 | 3135.00 |      9102.50 |
| PRESIDENT |    NULL | 5500.00 |    NULL |      5500.00 |
| SALESMAN  |    NULL |    NULL | 5600.00 |      5600.00 |
+-----------+---------+---------+---------+--------------+

 ```

Q6 . Write a query to display the total number of employees, and out of that total the number who were hired in 1980, 1981, 1982 and 1983. Give appropriate column heading.
## <h4>Queries:</h4>
 ```sql
 SELECT COUNT(*) AS "TOTAL_EMPLOYEES",
       SUM(CASE WHEN EXTRACT(YEAR FROM HIREDATE) = 1980 THEN 1 END) AS "HIRED_1980",
       SUM(CASE WHEN EXTRACT(YEAR FROM HIREDATE) = 1981 THEN 1 END) AS "HIRED_1981",
       SUM(CASE WHEN EXTRACT(YEAR FROM HIREDATE) = 1982 THEN 1 END) AS "HIRED_1982",
       SUM(CASE WHEN EXTRACT(YEAR FROM HIREDATE) = 1983 THEN 1 END) AS "HIRED_1983"
FROM EMPLOYEE;
 ```
 ## <h4>Output:</h4>
 ```sql
 +-----------------+------------+------------+------------+------------+
| TOTAL_EMPLOYEES | HIRED_1980 | HIRED_1981 | HIRED_1982 | HIRED_1983 |
+-----------------+------------+------------+------------+------------+
|              14 |          1 |         10 |          2 |          1 |
+-----------------+------------+------------+------------+------------+
1 row in set (0.005 sec)
 ```

Q7 . Write a query to get the last Sunday of any month.
## <h4>Queries:</h4>
 ```sql
 SELECT LAST_DAY('2026-02-01') -
       INTERVAL (WEEKDAY(LAST_DAY('2026-02-01')) + 1) DAY
       AS LAST_SUNDAY;
 ```
 ## <h4>Output:</h4>
 ```sql
 +-------------+
| LAST_SUNDAY |
+-------------+
| 2026-02-22  |
+-------------+
1 row in set (0.001 sec)
 ```

Q8 . Display department numbers and total number of employees working in each eavh department.
## <h4>Queries:</h4>
 ```sql
 SELECT deptno,
COUNT(*) AS total_employees
FROM employee
GROUP BY deptno;
```
## <h4>Output:</h4>
 ```sql
 +--------+-----------------+
| deptno | total_employees |
+--------+-----------------+
|     10 |               1 |
|     20 |               6 |
|     30 |               6 |
|     40 |               1 |
+--------+-----------------+
4 rows in set (0.129 sec)
```

Q9 . Display the various jobs and total number of employees within each job group.
## <h4>Queries:</h4>
 ```sql
 SELECT job,
COUNT(*) AS total_employees
FROM employee
GROUP BY job;
```
## <h4>Output:</h4>
 ```sql
 +-----------+-----------------+
| job       | total_employees |
+-----------+-----------------+
| ANALYST   |               2 |
| CLERK     |               4 |
| MANAGER   |               3 |
| PRESIDENT |               1 |
| SALESMAN  |               4 |
+-----------+-----------------+
5 rows in set (0.003 sec)
```

Q10 . Display the depart numbers and total salary for each department. 
## <h4>Queries:</h4>
 ```sql
 SELECT deptno,
SUM(sal) AS total_salary
FROM employee
GROUP BY deptno;
```
## <h4>Output:</h4>
 ```sql
 +--------+--------------+
| deptno | total_salary |
+--------+--------------+
|     10 |      1430.00 |
|     20 |     16857.50 |
|     30 |      9780.00 |
|     40 |      3300.00 |
+--------+--------------+
4 rows in set (0.001 sec)
```
