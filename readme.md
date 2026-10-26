select * from emp;

     EMPNO ENAME      JOB              MGR HIREDATE         SAL       COMM     DEPTNO
---------- ---------- --------- ---------- --------- ---------- ---------- ----------
      7698 BLAKE      MANAGER         7839 01-MAY-81       2850                    30
      7566 JONES      MANAGER         7839 02-APR-81       2975                    20
      7788 SCOTT      ANALYST         7566 19-APR-87       3000                    20
      7902 FORD       ANALYST         7566 03-DEC-81       3000                    20
      7369 SMITH      CLERK           7902 17-DEC-80        800                    10
      7499 ALLEN      SALESMAN        7698 20-FEB-81       1600        300         30
      7521 WARD       SALESMAN        7698 22-FEB-81       1250        500         10
      7654 MARTIN     SALESMAN        7698 28-SEP-81       1250       1400         10
      7844 TURNER     SALESMAN        7698 08-SEP-81       1500          0         30
      7876 ADAMS      CLERK           7788 23-MAY-87       1100                    10
      7900 JAMES      CLERK           7698 03-DEC-81        950                    10
      7700 scott      ANALYST         7566 19-APR-87       3000                    20
      7840 MADDEN     SALESMAN        7698 17-OCT-81     1633.5       1500         30
      8888 KARTIK     ANALYST         7566 01-MAY-81     5512.5                    20
      1234 NANDAN     MANAGER              01-MAY-81       5000                    20



select * from dept;

    DEPTNO DNAME          LOC
---------- -------------- -------------
        10 ACCOUNTING     NEW YORK
        20 RESEARCH       DALLAS
        30 SALES          CHICAGO
        40 OPERATIONS     BOSTON




Medium–Hard SQL Practice Questions (EMP & DEPT)
Level 1: Medium
1. Display the second-highest salary from the EMP table without using MAX() twice.
        select ename,hiredate, sal, no from (
                select emp.*,dense_rank() over(order by sal desc) no from emp) where no = 2;

2. Find employees who earn more than the average salary of their department.
        select \* from (select ename, sal, avg(sal) over(partition by deptno) deptavrg, deptno from emp) where sal > deptavrg;**

3. Display each department name and the total salary paid to its employees, including departments with no employees.
        
4. Find employees who earn a higher salary than their manager.

5. Display the employee name, job, department name, and location for all employees.

6. Find the departments that have more than 3 employees.

7. Display the highest-paid employee in each department.

8. Find employees who joined before their manager.

9. Display the total salary, average salary, minimum salary, and maximum salary for each job.

10. Find employees who do not receive commission (COMM is NULL or 0).
Level 2: Medium–Hard
11. Find the third-highest distinct salary from the EMP table.

12. Display the employees who earn the highest salary in their respective jobs.

13. Find departments where the average employee salary is greater than the overall company average salary.

14. Display each employee's name, salary, department average salary, and the difference between their salary and department average.

15. Find employees who earn more than at least one manager but less than the highest-paid manager.

16. Display the top 2 highest-paid employees in each department.

17. Find employees who have the same salary as another employee in the same department.

18. Find the department with the highest total salary expenditure.

19. Display employees who joined in the same year as their manager.

20. Find employees whose salary is greater than the salary of every clerk in the company.
Level 3: Hard
21. Display the employee name, salary, and salary rank within their department without using a subquery.

22. Find the second-highest-paid employee in each department, handling duplicate salaries correctly.

23. Display the cumulative salary total for employees in each department, ordered by salary from lowest to highest.

24. Find employees whose salary is greater than the average salary of their job and whose department's average salary is greater than the company average.

25. Display each employee's name, manager's name, and manager's manager's name.

26. Find departments where every employee earns more than ₹1,000.

27. Find the employees who earn the same salary as the highest-paid employee in any other department.

28. Find the percentage contribution of each employee's salary to their department's total salary.

29. Identify departments where the highest salary is at least twice the lowest salary.

30. Find employees whose salary is among the top 3 distinct salaries in the entire company.
Bonus Challenge: Advanced SQL
31. Find the median salary of employees in each department.

32. Display each employee's salary and the difference between their salary and the salary of the next-highest-paid employee in the same department.

33. Find the department with the second-highest average salary.

34. Identify employees who earn more than their department average but less than the company average.

35. Find the longest-serving employee in each department, including departments with no employees.

36. Display a report showing department name, employee count, total salary, average salary, and salary rank by department.

37. Find employees who have the same job as their manager but earn less than their manager.

38. Find the percentage of employees in each department who earn above the company average salary.

39. Display all employees who belong to the same department as the employee earning the third-highest distinct salary.

40. Find the highest-paid employee in each department without using GROUP BY.