## DML (DATA MANIPULATION LANGUAGE)

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...),
(value4, value5, value6, ...); /*insert multiple rows at once*/

INSERT INTO table_name (column1, column3, ...)
VALUES (value1, value3, ...); /*insert into specific columns*/

UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition; /*update rows that match the condition*/

UPDATE sales 
SET score = 0
WHERE score IS NULL;

DELETE FROM table_name
WHERE condition; /*delete rows that match the condition*/

DELETE FROM sales
WHERE score < 0; /*delete rows where score is less than 0*/


```
