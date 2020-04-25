Joins

In RDBMS data is maintained in more than one table.Tables are designed using Normalization rules.
Sometimes it is required to pull data from more than one table.Joins support to get data from many tables in single query.


Cross Join

Return rows in table1 multiplied by rows in table2

	SELECT *
	FROM employees,departments;


Inner Join

Inner join clause joins two tables based on a condition.
Only specified columns are selected from both tables, provided the matching condition is met.

	SELECT  e.employee_id, e.first_name,d.department_name
	FROM  Employees  e
	INNER JOIN  Departments d
	ON  e.department_id  =   d.department_id
	WHERE d.department_id  >= 60;



Left Outer Join

Left join selects all data from left table whether there are matching rows in right table or not.
For non matching columns from right table, NULLs are returned.

	SELECT  e.employee_id,  e.first_name, d.department_name
	FROM  Employees  e
	LEFT OUTER JOIN  Departments d
	ON  e.department_id  =   d.department_id;



Right Outer Join

Right join selects all data from right table whether there are matching rows in left table or not.
For non matching columns from left table, NULLs are returned.


	SELECT  e.employee_id,  e.first_name, d.department_name
	FROM  Employees  e
	RIGHT OUTER JOIN  Departments d
	ON  e.department_id  =   d.department_id;
