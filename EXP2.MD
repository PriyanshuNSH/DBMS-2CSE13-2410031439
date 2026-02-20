<center><h2>Experiment 2</h2></center>

Q1 . List all distinct job in Employee.
# <h4>Queries:</h4>
~~~sql
SELECT DISTINCT JOB FROM EMPLOYEE;
~~~
 
Q2 . List all information about employee in Department Number 30.
# <h4>Queries:</h4>
~~~sql
SELECT * FROM EMPLOYEE
    WHERE DEPTNO = 30;
~~~

Q3 . Find all department number with department names greater than 20.
# <h4>Queries:</h4>
~~~sql
SELECT DISTINCT DEPTNO FROM EMPLOYEE
    WHERE DEPTNO > 20;
~~~

Q4 . Find all information about all the managers as well as the clerks in department 30.
# <h4>Queries:</h4>
~~~sql
SELECT * FROM EMPLOYEE
    WHERE DEPTNO = 30
    AND JOB IN ('MANAGER','CLERK');
~~~

Q5 . List the Employee name, Employee numbers and department of all clerks.
# <h4>Queries:</h4>
~~~sql
SELECT ENAME,EMPNO,DEPTNO FROM EMPLOYEE
    WHERE JOB = 'CLERK';
~~~

Q6 . Find all managers not in department 30.
# <h4>Queries:</h4>
~~~sql
SELECT * FROM EMPLOYEE
    WHERE JOB = 'MANAGER'
    AND DEPTNO <> 30;
~~~

Q7 . List information about all Employees in department 10 who are not manager or clerks.
# <h4>Queries:</h4>
~~~sql
SELECT * FROM EMPLOYEE
    WHERE DEPTNO = 10
    AND JOB NOT IN ('MANAGER','CLERK');
~~~

Q8 . Find Employees and jobs earning between 1200 and 1400.
# <h4>Queries:</h4>
~~~sql
SELECT ENAME, JOB, SAL FROM EMPLOYEE
    WHERE SAL BETWEEN 1200 AND 1400;
~~~

Q9 . List Name and Department Number of employee who are clerks, analyst or salesman.
# <h4>Queries:</h4>
~~~sql
SELECT ENAME, DEPTNO FROM EMPLOYEE
    WHERE JOB IN ('CLERK','ANALYST','SALESMAN');
~~~

Q10 . List Name and Department Number of employee whose names began with M.
# <h4>Queries:</h4>
~~~sql
SELECT ENAME, DEPTNO FROM EMPLOYEE
    WHERE ENAME LIKE 'M%';
~~~