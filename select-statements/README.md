Select Statements

For syntax highlight, uuper case is used for all sql Key Words or Reserved Words
The database table and column names case is dependent on database server configuration.
Some servers ignore case for all table and column names.

Select all columns and all rows

	SELECT *
	FROM	employees;


Select specific columns for all rows

	SELECT employee_id,first_name,last_name
	FROM employees;


Arithmetic operators in select statments
	
	Add 125 to salary field. Do this for all rows in table
	
	SELECT employee_id,first_name,salary+125
	FROM employees;

	Give some name for this calculation. Call it as new_salary
	SELECT employee_id,first_name,salary+125 AS new_salary
	FROM employees;
	
Use multiple columns in Arithmetic operators

	SELECT employee_id,salary,commission_pct,salary*commission_pct AS total_commission
	FROM employees;

Restric rows using WHERE clause

	employees working in dept 60
	SELECT *
	FROM employees WHERE department_id = 60;
	
	employees getting salary more than 15000.00
	SELECT *
	FROM employees WHERE salary > 15000.00;
	
	employees without manager
	SELECT *
	FROM employees WHERE manager_id != 0;	

Restric rows using multiple conditions

	SELECT *
	FROM employees 
	WHERE department_id=60 AND salary>5000.00;

Conditional operators
	
BETWEEN operator
	SELECT *
	FROM employees 
	WHERE salary BETWEEN 5000 AND 8000;

IN operator
	SELECT *
	FROM employees 
	WHERE employee_id IN ( 111, 112 );

LIKE operator
	SELECT *
	FROM employees
	WHERE first_name LIKE 'D%';


	pattern with position matching
	all employees who has 'i' in 4 th place in their first_name
	SELECT *
	FROM employees
	WHERE first_name LIKE 'D__i%';

LIMIT rows

So far all sql select statements are returning all rows from table.This may not be possible
in scenarios like prod environment. MySQL provides facility to limit rows sent to user.
Read or get only 4 rows from employees table.
	
	SELECT *
	FROM employees LIMIT 4;


DISTINCT clause

Get all unique column values from a table, satisfying all conditions in sql query.
		
	SELECT distinct job_id
	FROM employees ;
		
	DISTINCT with multiple columns
		
	SELECT distinct department_id, job_id
	FROM employees;


ALIAS names for tables and columns

	SELECT employee_id AS empid
	FROM employees;
	
	SELECT employee_id AS empid
	FROM employees emp;
	
	
