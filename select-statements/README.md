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



