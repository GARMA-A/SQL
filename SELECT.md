## SELECT

```sql
SELECT 
  country,
  COUNT(*) AS user_count,
  AVG(revenue) AS avg_revenue
FROM filtered_data
JOIN purchases ON filtered_data.user_id = purchases.user_id
GROUP BY country
HAVING AVG(revenue) > 50
ORDER BY user_count DESC
LIMIT 5 OFFSET 0;

```

```sql
/*
SELECT is used to select the columns and print them from the table.
FROM is used to specify the table from which to select the columns.
WHERE is used to filter the rows based on a condition.
*/
SELECT * 
FROM table_name; /*select all columns from the table */

SELECT customer_id, 
    first_name, 
    last_name 
FROM customers; /*select specific columns from the table */

/*
WHERE is used to filter the rows based on a condition.
For example, to select all customers with a last name of 'Smith':
*/
SELECT * 
FROM customers 
WHERE last_name = 'Smith'; 
-- also can use LIKE for pattern matching
SELECT *
FROM customers 
WHERE last_name LIKE 'Smi%'; 
/*select all customers with a last name starting with 'Smi' */

-- you can use AND, OR, and NOT to combine conditions and >,<,>=,<=, !=,=
SELECT *
FROM customers 
WHERE last_name = 'Smith'
AND first_name = 'John';

SELECT *
FROM customers 
WHERE last_name != 'Smith';


-- you can use IN to specify a list of values
SELECT *
FROM customers 
WHERE last_name IN ('Smith', 'Johnson', 'Williams');

-- you can use BETWEEN to specify a range of values
SELECT *
FROM customers 
WHERE age BETWEEN 18 AND 30; /*select all customers with an age between 18 and 30 */

-- there is also GROUPBY, HAVING, ORDER BY, and LIMIT

-- you can use LIMIT to limit the number of rows returned
SELECT *
FROM customers
LIMIT 10; /*select the first 10 rows from the table */

-- you can use HAVING to filter the results of a GROUP BY clause
SELECT last_name, COUNT(*) AS count
FROM customers
GROUP BY last_name
HAVING COUNT(*) > 1; /*select last names that appear more than once */


-- you can use ORDER BY to sort the results
SELECT *
FROM customers
ORDER BY last_name ASC, first_name DESC; 
/*sort by last name ascending and first name descending */

-- you can use GROUP BY to group the results by a column
SELECT last_name, COUNT(*) AS count
FROM customers
GROUP BY last_name;

-- Selecting with aggregate functions
SELECT gender,SUM(age)
FROM students
GROUP BY gender;



```
