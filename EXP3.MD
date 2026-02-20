<center><h2>Experiment 3</h2></center>

Q1 . List all employees and jobs in Department 30 in descending order by salary.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME, JOB, SAL
FROM EMPLOYEE
WHERE DEPTNO = 30
ORDER BY SAL DESC;
~~~

Q2 . List job and Department Number of employees whose name are five letters long begin with “A” and end with “N”.
## <h4>Queries:</h4>
~~~sql
SELECT JOB, DEPTNO
FROM EMPLOYEE
WHERE ENAME LIKE 'A___N';
~~~

Q3 . Display the name of employees whose name start with alphabet S.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE 'S%';
~~~

Q4 . Display the names of employees whose name ends with alphabet S.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE '%S';
~~~

Q5 . Display the names of employees working in department number 10 or 20 or 40 or employees working as clerks, salesman or analyst.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME
FROM EMPLOYEE
WHERE DEPTNO IN (10,20,40)
OR JOB IN ('CLERK','SALESMAN','ANALYST');
~~~

Q6 . Display employee number and names for employees who earn commission.
## <h4>Queries:</h4>
~~~sql
SELECT EMPNO, ENAME
FROM EMPLOYEE
WHERE COMM IS NOT NULL
AND COMM > 0;
~~~

Q7 . Display employee number and total salary for each employee.
## <h4>Queries:</h4>
~~~sql
SELECT EMPNO,
(SAL + IFNULL(COMM,0)) AS TOTAL_SALARY
FROM EMPLOYEE;
~~~

Q8 . Display employee number and annual salary for each employee.
## <h4>Queries:</h4>
~~~sql
SELECT EMPNO,
(SAL * 12) AS ANNUAL_SALARY
FROM EMPLOYEE;
~~~

Q9 . Display the names of all employees working as clerks and drawing a salary more than 3,000.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB = 'CLERK'
AND SAL > 3000;
~~~

Q10 . Display the names of employees who are working as clerk, salesman or analyst and drawing a salary more than 3,000.
## <h4>Queries:</h4>
~~~sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB IN ('CLERK','SALESMAN','ANALYST')
AND SAL > 3000;
~~~