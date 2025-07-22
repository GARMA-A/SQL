## BUILD IN ROW LEVEL FUNCTIONS

![](./functionsImages/functions_overview.png)

### ROW LEVEL FUNCTIONS
#### STRINGS

```sql

SELECT CONCAT(first_name,' ', last_name) AS full_name;
-- this will return all columns from the actor table and add a new column full_name which is a concatenation of first_name and last_name
SELECT * , UPPER(CONCAT(first_name,' ', last_name)) AS full_name;
-- the same as the output above but the full_name will be in uppercase
SELECT * 
FROM actor
WHERE TRIM(first_name) != first_name
OR TRIM(last_name) != last_name;
-- find all actors where the first_name or last_name has leading or trailing spaces

SELECT LENGTH(first_name) ;-- returns the length of the first_name

SELECT 'report.pdf' AS old_report
, REPLACE('report.pdf', '.pdf', '_2023.pdf') AS new_report;
-- this will return the old_report and a new_report with the .pdf replaced by _2023.pdf

SELECT LEFT('report.pdf', 6) AS left_part ;-- returns the first 6 characters of the string
, RIGHT('report.pdf', 4) AS right_part; ;-- returns the last 4 characters of the string

SELECT SUBSTRING(first_name, 1, 3) AS first_three_characters;
-- returns the first 3 characters of the first_name
```


#### NUMBERS
```sql
SELECT  ROUND(8.5) AS rounded_value ;-- output:9

SELECT  ROUND(8.56362 , 3) AS rounded_value ;-- output:8.564

SELECT CEIL(8.1) AS ceil_value ;-- output:9

SELECT FLOOR(8.9) AS floor_value ;-- output:8

SELECT  ABS(-8.9) AS absolute_value ;-- output:8.9

SELECT  POWER(2, 3) AS power_value ;-- output:8 (2 raised to the power of 3)

SELECT  SQRT(16) AS square_root_value ;-- output:4 (square root of 16)

SELECT  MOD(10, 3) AS modulus_value ;-- output:1 (remainder of 10 divided by 3)

SELECT  PI() AS pi_value ;-- output:3.141592653589793

SELECT  RANDOM() AS random_value ;-- output: a random number between 0 and 1

SELECT  TRUNC(8.9) AS truncated_value ;-- output:8 (removes the decimal part)

SELECT  TRUNC(8.9, 1) AS truncated_value ;-- output:8.9 (removes the decimal part but keeps one decimal place)

SELECT  GREATEST(8, 9, 10, 7) AS greatest_value ;-- output:10 (returns the largest value)

SELECT  LEAST(8, 9, 10, 7) AS least_value ;-- output:7 (returns the smallest value)

SELECT  SIGN(-8.9) AS sign_value ;-- output:-1 (returns -1 for negative numbers, 1 for positive numbers, and 0 for zero)

SELECT CAST(CAST('8.9' AS FLOAT) AS INTEGER) AS casted_value;
-- or
SELECT CAST('8.9'::FLOAT AS INTEGER) AS casted_value;

```

#### DATES
```sql
SELECT CURRENT_DATE AS current_date; -- returns the current date

SELECT CURRENT_TIME AS current_time; -- returns the current time

SELECT CURRENT_TIMESTAMP AS current_timestamp; -- returns the current date and time

SELECT NOW() AS current_datetime; -- returns the current date and time

SELECT DATE '2023-10-01' AS specific_date; -- returns a specific date

SELECT EXTRACT(YEAR FROM CURRENT_DATE) AS current_year; -- returns the current year

SELECT DATE_PART('month', CURRENT_DATE) AS current_month_part; -- returns the current month using date_part

SELECT DATE_TRUNC('year', CURRENT_DATE) AS start_of_year; -- returns the start of the current year

SELECT DATE '2023-10-01' + INTERVAL '1 day' AS next_day; -- adds 1 day to a specific date


SELECT DATE_TRUNC('MONTH', CURRENT_DATE) + INTERVAL '1 MONTH' - INTERVAL '1 day' AS end_of_month; -- to get the end of the current month
```

![](./DatesImages/dates1.png)

![](./DatesImages/dates2.png)

![](./DatesImages/dates3.png)




