SQL Functions

MySQL server provides many inbuilt sql functions to work with various data present in tables.
These functions are categorized based on data types and usage scenarios.

Aggegate Functions

Aggegate functions work on multiple values of column and returns a single result.Most of them are delf exploratory.

COUNT
	Count all rows from a table.
	
	SELECT COUNT(*)
	FROM customer;
	
	Count all rows from a table, if only the column is having value init.In customer table some people do not have join_date.
	
	SELECT COUNT(join_date)
	FROM customer;
	
SUM
	
	SELECT SUM(member_fees)
	FROM customer;
	
MIN MAX AVG

	SELECT MIN(member_fees) AS MIN_FEES,
		MAX(member_fees) AS MAX_FEES,
		AVG(member_fees) AS AVG_FEES,
	FROM customer;


GROUP BY clause

All the aggregate functions can be combined with GROUP BY clause. This feature allows performing function on each distinct column value.Column value with NULL are not considered.
	
	SELECT department_id,SUM(salary)
	FROM employees
	GROUP BY department_id;
		
		
	Group on multiple columns
		
	SELECT department_id,job_id,SUM(salary)
	FROM employees
	GROUP BY department_id,job_id;

HAVING clause

Filter group by results based some condition.
	
	SELECT department_id,job_id,SUM(salary)
	FROM employees
	GROUP BY department_id,job_id
	HAVING SUM(salary) > 12000.00;


String Functions

	SELECT first_name,
		UPPER(first_name),
		LOWER(first_name) 
	FROM employees;

	SELECT first_name,
		LENGTH(first_name),
		CONCAT('Hi .. ',first_name) 
	FROM employees;


Math Functions

In these examples we are not using any tables. You can run again on any table column. Take care of column data type.

	SELECT MOD(3,2);
	SELECT SQRT(4);
	SELECT ROUND(10.656);
	SELECT FLOOR(10.456);
	SELECT TRUNCATE(10.656,1);


Date Functions

Work with curent date and time.
	SELECT CURRENT_DATE();
	SELECT CURRENT_TIME();
	SELECT CURRENT_TIMESTAMP();

Apply on user data
	
	SELECT ADDDATE(join_date, INTERVAL 2 MONTH)
	FROM customer;	

Custom Functions

Apart from MySQL supplied functions, customer can create his own functions.But this needs sql programming using stored functions.
Assume that you created a stored function calculateTax(order_amt) based on orderAmt column from order table,
you can invoke this custom built function as
	
	SELECT calculateTax(order_amt)
	FROM order
	WHERE order_id=1029;