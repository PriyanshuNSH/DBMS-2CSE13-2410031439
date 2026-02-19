# Experiment-7

Q1 . Compute the number of days remaining this year.
## Queries
```sql
 SELECT DATEDIFF(
    STR_TO_DATE(CONCAT(YEAR(CURDATE()),'-12-31'),'%Y-%m-%d'),
    CURDATE()
) AS days_remaining;
```
## Output
 ```sql 
+----------------+
| days_remaining |
+----------------+
|            315 |
+----------------+
1 row in set (0.000 sec)
```
Q2 . Find the highest and lowest salaries and the difference between of them.
## Queries
 ```sql
 SELECT 
MAX(sal) AS highest_salary,
MIN(sal) AS lowest_salary,
MAX(sal) - MIN(sal) AS difference
FROM employee;
```
## Output
 ```sql
+----------------+---------------+------------+
| highest_salary | lowest_salary | difference |
+----------------+---------------+------------+
|        5500.00 |        880.00 |    4620.00 |
+----------------+---------------+------------+
1 row in set (0.060 sec)
```
Q3 . List employee whose commission is greater than 25% of their salaries.
## Queries
 ```sql
 SELECT *
    -> FROM employee
    -> WHERE comm > (sal * 0.25);
```
 ## Output
 ```sql    
+-------+--------+----------+------+------------+---------+---------+--------+
| empno | ename  | job      | mgr  | hiredate   | sal     | comm    | deptno |
+-------+--------+----------+------+------------+---------+---------+--------+
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250.00 | 1400.00 |     30 |
+-------+--------+----------+------+------------+---------+---------+--------+
1 row in set (0.001 sec)
```
Q4 . Make a query that displays salary in doller formet.
## Queries
 ```sql
 SELECT ename,
CONCAT('$', FORMAT(sal,2)) AS salary_in_dollar
FROM employee;
```
## Output
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

Q6 . Write a query to display the total number of employees, and out of that total the number who were hired in 1980, 1981, 1982 and 1983. Give appropriate column heading.

Q7 . Write a query to get the last Sunday of any month.

Q8 . Display department numbers and total number of employees working in each eavh department.
## Queries
 ```sql
 SELECT deptno,
COUNT(*) AS total_employees
FROM employee
GROUP BY deptno;
```
## Output
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
## Queries
 ```sql
 SELECT job,
COUNT(*) AS total_employees
FROM employee
GROUP BY job;
```
## Output
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
## Queries
 ```sql
 SELECT deptno,
SUM(sal) AS total_salary
FROM employee
GROUP BY deptno;
```
## Output
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