# Experiment-7

## QUERIES
Q1 .Compute the number of days remaining this year.
```sql
 SELECT DATEDIFF(
    STR_TO_DATE(CONCAT(YEAR(CURDATE()),'-12-31'),'%Y-%m-%d'),
    CURDATE()
) AS days_remaining;
+----------------+
| days_remaining |
+----------------+
|            315 |
+----------------+
1 row in set (0.000 sec)
```
Q2 . Find the highest and lowest salaries and the difference between of them.
 ```sql
 SELECT 
MAX(sal) AS highest_salary,
MIN(sal) AS lowest_salary,
MAX(sal) - MIN(sal) AS difference
FROM employee;
+----------------+---------------+------------+
| highest_salary | lowest_salary | difference |
+----------------+---------------+------------+
|        5500.00 |        880.00 |    4620.00 |
+----------------+---------------+------------+
1 row in set (0.060 sec)

\|
```
Q3 . List employee whose commission is greater than 25% of their salaries.
 ```sql
 SELECT *
    -> FROM employee
    -> WHERE comm > (sal * 0.25);
+-------+--------+----------+------+------------+---------+---------+--------+
| empno | ename  | job      | mgr  | hiredate   | sal     | comm    | deptno |
+-------+--------+----------+------+------------+---------+---------+--------+
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250.00 | 1400.00 |     30 |
+-------+--------+----------+------+------------+---------+---------+--------+
1 row in set (0.001 sec)