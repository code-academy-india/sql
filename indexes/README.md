Indexes

Indexes are used to make SQL select statements work faster.Find and return rows very quickly.But they have some overhead when table is having lot of updates.

Types of Indexes

	Primary Key
	Index
	Unique


Primary Key

Primary key creates index in the background.Accepts only unique values.Duplicates and NULLs are not allowed.

Simple Primary Key
	
	Key consists of only one column.
	CREATE TABLE subscription (
		id INT(3) PRIMARY KEY,
		email_id varchar(80)
	);

Complex Primary Key

	Key consists of one or more columns.
	CREATE TABLE customer_email (
		name VARCHAR(40),
		email_id VARCHAR(80),
		PRIMARY KEY(name, email_id)
	);
	

Index

Make column part of index family.When this column is used in where clause,improves performacne of queries.
	
	CREATE TABLE page_liked (
		id INT(3) PRIMARY KEY,
		click_stream_ip VARCHAR(80),
		INDEX(click_stream_ip)
	);


Unique Index

Make column part of index family.Allow only unique values. Nulls are allowed.

	CREATE TABLE movie_name (
		id INT(3) PRIMARY KEY,
		movie_name VARCHAR(80) UNIQUE
	);