DML Data Manipulation Language

For syntax highlight, uuper case is used for all sql Key Words or Reserved Words
The database table and column names case is dependent on database server configuration.
Some servers ignore case for all table and column names.
Column values are case sensitive.

INSERT statement

Add row with all column values
	INSERT INTO customer
	VALUES( 100, 'Ramu P', '2018-04-01',126.50);

Add row with only speific column values

	INSERT INTO customer ( cust_id, cust_name )
	VALUES( 102, 'Pradeep Kumar');
		
	INSERT INTO customer ( cust_id, cust_name,member_fees )
	VALUES( 103, 'Pradeep Kumar',100.50);
		

Add multiple rows	

	INSERT INTO customer 
	VALUES( 104, 'K Suheer', '2018-04-01',0.00),
		( 106, 'S Yadav', '2018-04-26',626.50);
		
	
UPDATE statement	

Modify single column value
	
	UPDATE customer
	SET cust_name='Srinivas Yadav'
	WHERE cust_id = 106;

Modify multiple column values
	
	UPDATE customer
	SET cust_name='Pradeep K',
			member_fees = 420.00
	WHERE cust_id = 103;
	
	
DELETE statement

	DELETE FROM customer
	WHERE cust_id = 105;