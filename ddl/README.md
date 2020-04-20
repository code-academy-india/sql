DDL Data Definition Language

SQL statements to create various database objects like Table, View, Trigger, Index etc.
Generally done by Database Administrator.Now a days most of GUI clients do not need these commands.But it is good and best to know syntax to work on CLI client or APIs.

CREATE Table

	CREATE TABLE atm_card_customer (
		cust_id int(3) PRIMARY KEY,
		cust_name varchar(30) NOT NULL,
		card_no varchar(16)
	);
	
	CREATE TABLE atm_customer_address (
		cust_id int(3) PRIMARY KEY,
		street varchar(40) NOT NULL,
		city varchar(40),
		FOREIGN KEY(cust_id) REFERENCES atm_card_customer( cust_id )
	);


ALTER Table

	ALTER TABLE atm_card_customer
	MODIFY cust_name VARCHAR(50) NOT NULL;

	ALTER TABLE atm_card_customer
	ADD(daily_limit double(7,2));


DROP Table

Permanently remove table definition and table data
	
	DROP TABLE atm_customer_address;
	

RENAME Table
	
	RENAME TABLE atm_card_customer
	TO atm_customer;


TRUNCATE TABLE

Permanently remove all table data. Table definition is not removed.

	TRUNCATE TABLE atm_customer;