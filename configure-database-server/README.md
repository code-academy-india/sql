Configure Database Server

Hope the MySQL server and client tools are installed and in working condition.

Extract db-scripts.7z zip file. It consists of two sql scripts.
Open sql client and connect to your database.Open new sql query dialog.

Run mysql-database-git.sql script file. It creates mysql_tutorial database and various
tables.

Now run musql-data-git.sql to populate these tables with some sample data.

Verify from sql client that the Database, tables and sample data is present.

SELECT * FROM customer;
