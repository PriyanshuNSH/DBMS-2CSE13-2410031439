## <center><h2>Experiment 6</h2></center>

Q1 . Display empno, ename, deptno from employee table. Instead of displaying department numbers, display the related department name (Use decode function).
## <h4>Queries:</h4>
```sql
 SELECT empno, ename,
CASE deptno
    WHEN 10 THEN 'ACCOUNTING'
    WHEN 20 THEN 'RESEARCH'
    WHEN 30 THEN 'SALES'
    WHEN 40 THEN 'OPERATIONS'
END AS department_name
FROM employee;
```
## <h4>Output:</h4>
```sql
 +-------+--------+-----------------+
| empno | ename  | department_name |
+-------+--------+-----------------+
|  7369 | SMITH  | RESEARCH        |
|  7499 | ALLEN  | SALES           |
|  7521 | WARD   | SALES           |
|  7566 | JONES  | RESEARCH        |
|  7654 | MARTIN | SALES           |
|  7698 | BLAKE  | SALES           |
|  7782 | CLARK  | RESEARCH        |
|  7788 | SCOTT  | OPERATIONS      |
|  7839 | KING   | RESEARCH        |
|  7844 | TURNER | SALES           |
|  7876 | ADAMS  | RESEARCH        |
|  7900 | JAMES  | SALES           |
|  7902 | FORD   | RESEARCH        |
|  7934 | MILLER | ACCOUNTING      |
+-------+--------+-----------------+
14 rows in set (0.025 sec)
 ```

Q2 . Display your age in days.
## <h4>Queries:</h4>
```sql
 SELECT DATEDIFF(CURDATE(), '2005-01-01') AS age_in_days;
 ```
 ## <h4>Output:</h4>
 ```sql
 +-------------+
| age_in_days |
+-------------+
|        7719 |
+-------------+
1 row in set (0.004 sec)
 ```

Q3 . Display your age in months.
## <h4>Queries:</h4>
```sql
 SELECT TIMESTAMPDIFF(MONTH, '2005-01-01', CURDATE()) AS age_in_months;
 ```
 ## <h4>Output:</h4>
 ```sql
 +---------------+
| age_in_months |
+---------------+
|           253 |
+---------------+
1 row in set (0.002 sec)
 ```

Q4 . Display the current date as 15th August Friday Nineteen Ninety-Seven.
## <h4>Queries:</h4>
```sql
 SELECT DATE_FORMAT(CURDATE(), '%D %M %W %Y');
 ```
 ## <h4>Output:</h4>
 ```sql
 +---------------------------------------+
| DATE_FORMAT(CURDATE(), '%D %M %W %Y') |
+---------------------------------------+
| 19th February Thursday 2026           |
+---------------------------------------+
1 row in set (0.004 sec)
 ```

Q5 . Display the following output for each row from employee table.
## <h4>Queries:</h4>
```sql
 SELECT CONCAT(ename, ' joined on ', 
DATE_FORMAT(hiredate, '%W %D %M %Y')) 
FROM employee;
```
## <h4>Output:</h4>
```sql
 +---------------------------------------------------------------------+
| CONCAT(ename, ' joined on ',
DATE_FORMAT(hiredate, '%W %D %M %Y')) |
+---------------------------------------------------------------------+
| SMITH joined on Wednesday 17th December 1980                        |
| ALLEN joined on Friday 20th February 1981                           |
| WARD joined on Sunday 22nd February 1981                            |
| JONES joined on Thursday 2nd April 1981                             |
| MARTIN joined on Monday 28th September 1981                         |
| BLAKE joined on Friday 1st May 1981                                 |
| CLARK joined on Tuesday 9th June 1981                               |
| SCOTT joined on Thursday 9th December 1982                          |
| KING joined on Tuesday 17th November 1981                           |
| TURNER joined on Tuesday 8th September 1981                         |
| ADAMS joined on Wednesday 12th January 1983                         |
| JAMES joined on Thursday 3rd December 1981                          |
| FORD joined on Thursday 3rd December 1981                           |
| MILLER joined on Saturday 23rd January 1982                         |
+---------------------------------------------------------------------+
14 rows in set (0.001 sec)
 ```

Q6 . Scott has joined the company on Wednesday 13th August Nineteen Ninety.
## <h4>Queries:</h4>
```sql
 SELECT CONCAT('Scott has joined the company on ',
DATE_FORMAT(hiredate, '%W %D %M %Y'))
FROM employee
WHERE ename = 'SCOTT';
```
## <h4>Output:</h4>
```sql
 +----------------------------------------------------------------------------------+
| CONCAT('Scott has joined the company on ',
DATE_FORMAT(hiredate, '%W %D %M %Y')) |
+----------------------------------------------------------------------------------+
| Scott has joined the company on Thursday 9th December 1982                       |
+----------------------------------------------------------------------------------+
1 row in set (0.001 sec)
 ```

Q7 . Find the date for nearest Saturday after current date.
## <h4>Queries:</h4>
```sql
 SELECT DATE_ADD(CURDATE(), 
INTERVAL (7 - WEEKDAY(CURDATE())) DAY) AS next_saturday;
```
## <h4>Output:</h4>
```sql
 +---------------+
| next_saturday |
+---------------+
| 2026-02-23    |
+---------------+
1 row in set (0.001 sec)
 ```

Q8 . Display current time.
## <h4>Queries:</h4>
```sql
 SELECT CURTIME();
```
## <h4>Output:</h4>
```sql
 +-----------+
| CURTIME() |
+-----------+
| 15:06:20  |
+-----------+
1 row in set (0.001 sec)
 ```

Q9 . Display the date three months before the current date.
## <h4>Queries:</h4>
```sql
 SELECT DATE_SUB(CURDATE(), INTERVAL 3 MONTH);
 ```
 ## <h4>Output:</h4>
 ```sql
 +---------------------------------------+
| DATE_SUB(CURDATE(), INTERVAL 3 MONTH) |
+---------------------------------------+
| 2025-11-19                            |
+---------------------------------------+
1 row in set (0.000 sec)
 ```

Q10 . Display those employees who joined in the company in the month of December.
## <h4>Queries:</h4>
```sql
 SELECT * FROM employee
WHERE MONTH(hiredate) = 12;
```
## <h4>Output:</h4>
```sql
 +-------+-------+---------+------+------------+---------+------+--------+
| empno | ename | job     | mgr  | hiredate   | sal     | comm | deptno |
+-------+-------+---------+------+------------+---------+------+--------+
|  7369 | SMITH | CLERK   | 7902 | 1980-12-17 |  880.00 | NULL |     20 |
|  7788 | SCOTT | ANALYST | 7566 | 1982-12-09 | 3300.00 | NULL |     40 |
|  7900 | JAMES | CLERK   | 7698 | 1981-12-03 | 1045.00 | NULL |     30 |
|  7902 | FORD  | ANALYST | 7566 | 1981-12-03 | 3300.00 | NULL |     20 |
+-------+-------+---------+------+------------+---------+------+--------+
4 rows in set (0.001 sec)
 ```

Q11 . Display those employees whose first 2 characters from hiredate match the last 2 characters of salary.
## <h4>Queries:</h4>
```sql
 SELECT * FROM employee
WHERE LEFT(DATE_FORMAT(hiredate,'%d'),2) =
RIGHT(sal,2);
```
## <h4>Output:</h4>
```sql
 Empty set (0.002 sec)
 ```

Q12 . Display those employees whose 10% of salary is equal to the year of joining.
## <h4>Queries:</h4>
```sql
 SELECT * FROM employee
WHERE sal * 0.10 = YEAR(hiredate);
```
## <h4>Output:</h4>
```sql
 Empty set (0.003 sec)
 ```

Q13 . Display those employees who joined the company before 15th of the month.
## <h4>Queries:</h4>
```sql
 SELECT * FROM employee
WHERE DAY(hiredate) < 15;
```
## <h4>Output:</h4>
```sql
 +-------+--------+----------+------+------------+---------+------+--------+
| empno | ename  | job      | mgr  | hiredate   | sal     | comm | deptno |
+-------+--------+----------+------+------------+---------+------+--------+
|  7566 | JONES  | MANAGER  | 7839 | 1981-04-02 | 3272.50 | NULL |     20 |
|  7698 | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 3135.00 | NULL |     30 |
|  7782 | CLARK  | MANAGER  | 7839 | 1981-06-09 | 2695.00 | NULL |     20 |
|  7788 | SCOTT  | ANALYST  | 7566 | 1982-12-09 | 3300.00 | NULL |     40 |
|  7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500.00 | 0.00 |     30 |
|  7876 | ADAMS  | CLERK    | 7788 | 1983-01-12 | 1210.00 | NULL |     20 |
|  7900 | JAMES  | CLERK    | 7698 | 1981-12-03 | 1045.00 | NULL |     30 |
|  7902 | FORD   | ANALYST  | 7566 | 1981-12-03 | 3300.00 | NULL |     20 |
+-------+--------+----------+------+------------+---------+------+--------+
8 rows in set (0.002 sec)
 ```

Q14 . Display those employees who have joined before 15th of the month.
## <h4>Queries:</h4>
```sql
 SELECT * FROM employee
WHERE DAY(hiredate) < 15;
```
## <h4>Output:</h4>
```sql
 +-------+--------+----------+------+------------+---------+------+--------+
| empno | ename  | job      | mgr  | hiredate   | sal     | comm | deptno |
+-------+--------+----------+------+------------+---------+------+--------+
|  7566 | JONES  | MANAGER  | 7839 | 1981-04-02 | 3272.50 | NULL |     20 |
|  7698 | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 3135.00 | NULL |     30 |
|  7782 | CLARK  | MANAGER  | 7839 | 1981-06-09 | 2695.00 | NULL |     20 |
|  7788 | SCOTT  | ANALYST  | 7566 | 1982-12-09 | 3300.00 | NULL |     40 |
|  7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500.00 | 0.00 |     30 |
|  7876 | ADAMS  | CLERK    | 7788 | 1983-01-12 | 1210.00 | NULL |     20 |
|  7900 | JAMES  | CLERK    | 7698 | 1981-12-03 | 1045.00 | NULL |     30 |
|  7902 | FORD   | ANALYST  | 7566 | 1981-12-03 | 3300.00 | NULL |     20 |
+-------+--------+----------+------+------------+---------+------+--------+
8 rows in set (0.001 sec)
 ```

Q15 . Display those employees whose joining date is available in deptno.
## <h4>Queries:</h4>
```sql
 SELECT * FROM employee
WHERE hiredate IS NOT NULL
AND deptno IS NOT NULL;
```
## <h4>Output:</h4>
```sql
 +-------+--------+-----------+------+------------+---------+---------+--------+
| empno | ename  | job       | mgr  | hiredate   | sal     | comm    | deptno |
+-------+--------+-----------+------+------------+---------+---------+--------+
|  7369 | SMITH  | CLERK     | 7902 | 1980-12-17 |  880.00 |    NULL |     20 |
|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600.00 |  300.00 |     30 |
|  7521 | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250.00 |  300.00 |     30 |
|  7566 | JONES  | MANAGER   | 7839 | 1981-04-02 | 3272.50 |    NULL |     20 |
|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250.00 | 1400.00 |     30 |
|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 3135.00 |    NULL |     30 |
|  7782 | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2695.00 |    NULL |     20 |
|  7788 | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3300.00 |    NULL |     40 |
|  7839 | KING   | PRESIDENT | NULL | 1981-11-17 | 5500.00 |    NULL |     20 |
|  7844 | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500.00 |    0.00 |     30 |
|  7876 | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1210.00 |    NULL |     20 |
|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 | 1045.00 |    NULL |     30 |
|  7902 | FORD   | ANALYST   | 7566 | 1981-12-03 | 3300.00 |    NULL |     20 |
|  7934 | MILLER | CLERK     | 7782 | 1982-01-23 | 1430.00 |    NULL |     10 |
+-------+--------+-----------+------+------------+---------+---------+--------+
14 rows in set (0.003 sec)
 ```
