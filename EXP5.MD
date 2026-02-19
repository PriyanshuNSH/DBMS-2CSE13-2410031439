## Experiment 5

Q1 . Display the total number of employee working in the company.
## Queries
```sql
 SELECT COUNT(*) AS total_employees FROM employee;
 ```
 ## Output
 ```sql
 +-----------------+
| total_employees |
+-----------------+
|              14 |
+-----------------+
1 row in set (0.037 sec)
 ```

Q2 . Display the total salary being paid to all employees.
## Queries
```sql
 SELECT SUM(sal) AS total_salary FROM employee;
```
## Output
```sql
 +--------------+
| total_salary |
+--------------+
|     31367.50 |
+--------------+
1 row in set (0.001 sec)

MariaDB [Priyanshuj]>
 ```

Q3 . Display the maximum salary from employee table.
## Queries
```sql
 SELECT MAX(sal) AS max_salary FROM employee;
 ```
 ## Output
 ```sql
 +------------+
| max_salary |
+------------+
|    5500.00 |
+------------+
1 row in set (0.001 sec)
 ```

Q4 . Display the minimum salary from employee table.
## Queries
```sql
 SELECT MIN(sal) AS min_salary FROM employee;
 ```
 ## Output
 ```sql
 +------------+
| min_salary |
+------------+
|     880.00 |
+------------+
1 row in set (0.000 sec)
 ```

Q5 . Display the average salary from employee table.
## Queries
```sql
 SELECT AVG(sal) AS avg_salary FROM employee;
 ```
 ## Output
 ```sql
 +-------------+
| avg_salary  |
+-------------+
| 2240.535714 |
+-------------+
1 row in set (0.001 sec)
 ```

Q6 . Display the maximum salary being paid to clerk.
## Queries
```sql
 SELECT MAX(sal) AS max_clerk_salary 
FROM employee 
WHERE job = 'CLERK';
```
## Output
```sql
 +------------------+
| max_clerk_salary |
+------------------+
|          1430.00 |
+------------------+
1 row in set (0.001 sec)
 ```

Q7 . Display the maximum salary being in dept no 20.
## Queries
```sql
 SELECT MIN(sal) AS min_salary_dept20 
FROM employee 
WHERE deptno = 20;
```
## Output
```sql
 +-------------------+
| min_salary_dept20 |
+-------------------+
|            880.00 |
+-------------------+
1 row in set (0.001 sec)
 ```

Q8 . Display the minimum salary paid to any salesman.
## Queries
```sql
 SELECT MIN(sal) AS min_salesman_salary 
FROM employee 
WHERE job = 'SALESMAN';
```
## Output
```sql
 +---------------------+
| min_salesman_salary |
+---------------------+
|             1250.00 |
+---------------------+
1 row in set (0.001 sec)
 ```

Q9 . Display the average salary drawn by managers.
## Queries
```sql
 SELECT AVG(sal) AS avg_manager_salary 
FROM employee 
WHERE job = 'MANAGER';
```
## Output
```sql
 +--------------------+
| avg_manager_salary |
+--------------------+
|        3034.166667 |
+--------------------+
1 row in set (0.001 sec)
 ```

Q10 . Display the total salary drawn by analyst working in dept no 40.
## Queries
```sql
 SELECT SUM(sal) AS total_analyst_salary 
FROM employee 
WHERE job = 'ANALYST' AND deptno = 40;
```
## Output
```sql
 +----------------------+
| total_analyst_salary |
+----------------------+
|              3300.00 |
+----------------------+
1 row in set (0.001 sec)
 ```

Q11 . Display the names of the employee in Uppercase.
## Queries
```sql
 SELECT UPPER(ename) FROM employee;
```
## Output
```sql
 +--------------+
| UPPER(ename) |
+--------------+
| SMITH        |
| ALLEN        |
| WARD         |
| JONES        |
| MARTIN       |
| BLAKE        |
| CLARK        |
| SCOTT        |
| KING         |
| TURNER       |
| ADAMS        |
| JAMES        |
| FORD         |
| MILLER       |
+--------------+
14 rows in set (0.001 sec)
 ```

Q12 . Display the names of the employee in Lowercase.
## Queries
```sql
SELECT LOWER(ename) FROM employee;
```
## Output
```sql
 +--------------+
| LOWER(ename) |
+--------------+
| smith        |
| allen        |
| ward         |
| jones        |
| martin       |
| blake        |
| clark        |
| scott        |
| king         |
| turner       |
| adams        |
| james        |
| ford         |
| miller       |
+--------------+
14 rows in set (0.000 sec)
 ```

Q13 . Display the names of the employee in Propercase.
## Queries
```sql
 SELECT CONCAT(UCASE(LEFT(ename,1)), LCASE(SUBSTRING(ename,2))) 
FROM employee;
```
## Output
```sql
 +---------------------------------------------------------+
| CONCAT(UCASE(LEFT(ename,1)), LCASE(SUBSTRING(ename,2))) |
+---------------------------------------------------------+
| Smith                                                   |
| Allen                                                   |
| Ward                                                    |
| Jones                                                   |
| Martin                                                  |
| Blake                                                   |
| Clark                                                   |
| Scott                                                   |
| King                                                    |
| Turner                                                  |
| Adams                                                   |
| James                                                   |
| Ford                                                    |
| Miller                                                  |
+---------------------------------------------------------+
14 rows in set (0.001 sec)
 ```

Q14 . Display the length of our name using appropriate function.
## Queries
```sql
 SELECT LENGTH('Priyanshu');
```
## Output
```sql
 +---------------------+
| LENGTH('Priyanshu') |
+---------------------+
|                   9 |
+---------------------+
1 row in set (0.001 sec)
 ```

Q15 . Display the length of all the employee names.
## Queries
```sql
 SELECT ename, LENGTH(ename) FROM employee;
```
## Output
```sql
 +--------+---------------+
| ename  | LENGTH(ename) |
+--------+---------------+
| SMITH  |             5 |
| ALLEN  |             5 |
| WARD   |             4 |
| JONES  |             5 |
| MARTIN |             6 |
| BLAKE  |             5 |
| CLARK  |             5 |
| SCOTT  |             5 |
| KING   |             4 |
| TURNER |             6 |
| ADAMS  |             5 |
| JAMES  |             5 |
| FORD   |             4 |
| MILLER |             6 |
+--------+---------------+
14 rows in set (0.001 sec)
 ```