**DML (Data Manipulation Language)** is a subset of SQL used to manipulate and retrieve data stored in database tables. to do CRUD operation create,retrieve, update and delete

For this we'll be using Oracle MySQL workbench DBMS
Database name: campusx

tables:
CREATE TABLE users(
	user_id INTEGER PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
    )
# INSERT
Adds new records to database tables.
```
INSERT INTO campusx.users (user_id, name,email, password)
VALUES (NULL, 'nitish', 'nitish@gmail.com', '1234')

-- This also works, you don't alwasys need to specify column name but make sure 
-- all the values are entered and in correct sequence
INSERT INTO campusx.users
VALUES (NULL, 'nitish', 'nitish@gmail.com', '1234')

-- First format can also be used to input values in specific columns, given rest have default value set or are ok with nulls
INSERT INTO campusx.users (name,email)
VALUES ('nitish', 'nitish@gmail.com')
```
 Similarly you can also include multiple values, by adding VALUES() as per your requirement.


*You can also insert a table with insert statement with subqueries, example will come in RETRIEVE>SUBQUERIES*


# ==RETRIEVE - V.IMP==
The most commonly used DML command for querying and retrieving data from tables.

We'll be using smartphone data in this example, present in Github>SQL-Projects>CRUD_DML_operations

1. [[General SELECT statements]]
2. [[SQL Joins]]
3. [[SQL SubQueries]]
4. [[SQL Common table expressions - CTEs]]
5. [[SQL Window Funtion]]
# UPDATE
Modifies existing records in database tables.

```
UPDATE campusx.smartphones
SET processor_brand = 'dimensity'
WHERE processor_brand = 'mediatek'

-- Multiple values can also be updated

UPDATE campusx.smartphones
SET brand = 'samsung korea', has_5g = 'False'
WHERE brand = 'samsung'
```


# DELETE
Removes records from database tables.

```
DELETE FROM campusx.smartphones
WHERE price>200000
```