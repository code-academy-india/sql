Transactions

A transaction consists of one or more insert/update/delete statements.Core support for ACID features.
All statements must be accepted or all are discarded.

By default, MySQL runs in autocimmit mode.When working with SQL clients, take care of auto commit feature.Transaction support can be enabled at run time.
Only DML statements are part of Transactions.

Add new Customer

	SET AUTOCOMMIT=0;
	INSERT INTO customer ( cust_id, cust_name,member_fees )
	VALUES( 107, 'Vasantha K',777.15);	
	
	At this point the row is visible to current user session. But not to other users. This is the
	beauty of ACID feature.
	
	Now the client make changes permanent or disard them. Let us make changes permanent.
	
	COMMIT;
	
	Everybody can now see the new row.

Discarding transactions
	
	SET AUTOCOMMIT=0;
	
	// all your insert/update/delete statements
	
	ROLLBACK;
	

Explicit Locking Tables
-----------------------

WRITE LOCK
	
	If user session obtains WRITE lock on a table, only that user session can READ or WRITE to that table
	LOCK TABLES customer WRITE;
		
		// sql statements
		// after work, realse lock
		// without releasing, all users can not use this table
		
	UNLOCK TABLES;

READ LOCK
	If user session obtains READ lock on a table, everybody can read from that table, but no one can write.
	LOCK TABLES customer READ;
		// only SELECT statements
		//
	UNLICK TABLES;


SAVEPOINT
---------
Temporary mark in a transaction.Provides facility to rollback some part 
and commit some part of transaction.

	SET AUTOCOMMIT=0;
	INSERT INTO customer ( cust_id, cust_name,member_fees )	VALUES( 307, 'Vasanth',277.15);
	SAVEPOINT SECOND_CUST;
	INSERT INTO customer ( cust_id, cust_name,member_fees )	VALUES( 308, 'Ram Kishore',7.76);
	ROLLBACK TO SECOND_CUST;
	COMMIT;
	SELECT *	FROM customer;