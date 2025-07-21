# THE ALL IN ONE SQL GUIDE


## Overview
### There is data definition language (DDL)

```sql

CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
);

CREATE INDEX index_name ON table_name (column_name); /*for performance */
CREATE VIEW view_name 
CREATE TRIGGER trigger_name
CREATE PROCEDURE procedure_name
CREATE FUNCTION function_name
CREATE SCHEMA schema_name;
CREATE DATABASE database_name;
CREATE USER user_name IDENTIFIED BY password;
CREATE ROLE role_name;
CREATE SEQUENCE sequence_name
CREATE SYNONYM synonym_name FOR object_name;
CREATE MATERIALIZED VIEW materialized_view_name;



ALTER TABLE table_name ADD column_name datatype;
AlTER TABLE table_name DROP COLUMN column_name;
AlTER TABLE table_name RENAME TO new_table_name;
ALTER TABLE table_name MODIFY COLUMN column_name datatype; 


DROP TABLE table_name;
DROP INDEX index_name;
DROP VIEW view_name;
DROP TRIGGER trigger_name;
DROP PROCEDURE procedure_name;
DROP FUNCTION function_name;
DROP SCHEMA schema_name;
DROP DATABASE database_name;

```


### data manipulation language (DML)

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

DELETE FROM table_name
WHERE condition;

SELECT column1, column2, ...
FROM table_name
WHERE condition;

SELECT * FROM table_name;

SELECT column1, column2, ...
FROM table_name
WHERE condition

ORDER BY column1, column2, ... ASC|DESC;
```

### data control language (DCL).

```sql
GRANT privilege ON object TO user_name;
REVOKE privilege ON object FROM user_name;
COMMIT; /*save changes */
ROLLBACK; /*undo changes */
SAVEPOINT savepoint_name; /*set a point to rollback to */
SET TRANSACTION ISOLATION LEVEL isolation_level; /*set isolation level */
SET ROLE role_name; /*set the current role */
SET USER user_name; /*set the current user */
SET SESSION CHARACTERISTICS AS TRANSACTION ISOLATION LEVEL isolation_level; /*set session isolation level */
```




## RESOURSES
### COURSES
[SQL Full Course for Beginners 30h youtube](https://youtu.be/SSKVgrwhzus)
[Original REPO](https://github.com/DataWithBaraa/sql-ultimate-course)


### MOST USED POSTGRESQL COMMANDS

| Command         | Description                                         |
|-----------------|----------------------------------------------------|
| \q              | Quit psql                                          |
| \l              | List databases                                     |
| \c dbname       | Connect to a database                              |
| \dt             | List all tables in current database                |
| \d table_name   | Show structure/schema of a table                   |
| \du             | List all users/roles                               |
| \x              | Toggle expanded output (very useful for wide tables)|
| \?              | Help on psql commands                              |
| \h              | Help on SQL commands (e.g. \h SELECT)              |
| \i filename.sql | Execute SQL from a file                            |
| \timing         | Toggle query execution time display                |
| \conninfo       | Show current connection info                       |
| \password       | Change user password                               |
| \encoding       | Show or set client encoding                        |
| \set var value  | Set psql variable                                  |
| \echo string    | Print string to standard output                    |
| \g              | Execute query (send to server)                     |
| \watch 2        | Re-run last query every 2 seconds                  |
| \i filename.sql | Execute SQL from a file                            |
| \copy table_name FROM 'filename.csv' CSV HEADER | Import CSV data into a specific table           |
| \copy table_name TO 'filename.csv' CSV HEADER   | Export table data to CSV file                   |

## Migration Tools

Yes, there are tools that automate database migrations and track their status:

- **Flyway**: Simple, widely used migration tool for SQL files.
- **Sqitch**: Flexible database change management system.
- **Liquibase**: Powerful migration tool supporting SQL and XML/JSON/YAML formats.
- **Alembic**: For Python projects using SQLAlchemy.

These tools automatically apply migrations in order and record which migrations have been run.

```sh
psql -d your_database -f 001_create_users_table.sql
psql -d your_database -f 001_create_posts_table.sql
psql -d your_database -f 002_add_email_to_users_table.sql

```

