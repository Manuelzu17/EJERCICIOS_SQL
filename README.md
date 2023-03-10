# EJERCICIOS_SQL

![](Aspose.Words.bf8e74df-2899-4811-8dcd-1fec9c06faa9.001.png)

1. SELECT

A SQL SELECT statement is used to query a database and retrieve specific data from one or more tables. Here's a simple example of a SQL SELECT statement:

```
SELECT column1, column2, column3
FROM table_name;

```
In this example, column1, column2, and column3 are the names of the columns you want to retrieve, and table_name is the name of the table you're retrieving data from. The statement retrieves all data from these columns for every row in the table.

2. WHERE

In this example, column1, column2, and column3 are the names of the columns you want to retrieve, and table_name is the name of the table you're retrieving data from. The WHERE clause specifies that only rows where the value in column4 is equal to 'some value' will be returned.

```
SELECT column1, column2, column3
FROM table_name
WHERE column4 = 'some value';
```

3. AND, OR, NOT

In this example, the AND operator is used to retrieve only customers that are located in the USA and either in New York or Los Angeles, while the OR operator is used to retrieve customers that are located in either New York or Los Angeles. The NOT operator is used to exclude customers with a status of "inactive".

```
SELECT *
FROM customers
WHERE country = 'USA' AND (city = 'New York' OR city = 'Los Angeles')
AND NOT status = 'inactive';
```

4. ORDER BY

In this example, the ORDER BY clause is used to sort the result set based on the salary column in descending order. The DESC keyword is used to specify the sort order as descending. If you wanted to sort the result set in ascending order, you could omit the DESC keyword.

```
SELECT first_name, last_name, salary
FROM employees
ORDER BY salary DESC;

```

5. INSERT INTO

In this example, the INSERT INTO statement is used to insert a new row into the employees table. The first_name, last_name, hire_date, and salary columns are specified in the INSERT INTO clause, and the values for those columns are specified in the VALUES clause. This statement will add a new row to the employees table with the values John for first_name, Doe for last_name, 2022-01-01 for hire_date, and 65000 for salary.

```
INSERT INTO employees (first_name, last_name, hire_date, salary)
VALUES ('John', 'Doe', '2022-01-01', 65000);

```

6. NULL Values

In this example, the NULL value is used for the manager_id column. The NULL value represents missing or unknown data in SQL. By assigning a NULL value to the manager_id column, we indicate that this information is not known or not applicable for this employee.

```
INSERT INTO employees (first_name, last_name, hire_date, salary, manager_id)
VALUES ('Jane', 'Doe', '2022-05-01', 55000, NULL);
```

7. UPDATE

In this example, the UPDATE statement is used to modify the data in the employees table. The SET clause is used to specify the new value for the salary column (67000), and the WHERE clause is used to specify the condition for which rows should be updated (first_name = 'John' and last_name = 'Doe'). This statement will update the salary value for the row(s) in the employees table that match the specified condition.

```
UPDATE employees
SET salary = 67000
WHERE first_name = 'John' AND last_name = 'Doe';
```

8. DELETE

In this example, the DELETE statement is used to delete data from the employees table. The WHERE clause is used to specify the condition for which rows should be deleted (first_name = 'John' and last_name = 'Doe'). This statement will delete the row(s) in the employees table that match the specified condition.

```

DELETE FROM employees
WHERE first_name = 'John' AND last_name = 'Doe';

```

9. LIMIT

In this example, the LIMIT clause is used to limit the number of rows returned in the result set to 5. The SELECT statement retrieves all columns from the employees table and the LIMIT clause limits the number of rows returned to 5.

```

SELECT *
FROM employees
LIMIT 5;
```


10. MIN and MAX

In this example, the MIN and MAX aggregate functions are used to retrieve the minimum and maximum values of the salary column, respectively, from the employees table. The results are aliased using the AS keyword to min_salary and max_salary, respectively, for easier reference in the result set.

```


SELECT MIN(salary) AS min_salary, MAX(salary) AS max_salary
FROM employees;
```


11. COUNT, AVG, SUM

In this example, the COUNT function is used to retrieve the total number of rows in the employees table, the AVG function is used to calculate the average value of the salary column, and the SUM function is used to calculate the total value of the salary column. The results are aliased using the AS keyword to total_employees, avg_salary, and total_salary, respectively, for easier reference in the result set.

```

SELECT COUNT(*) AS total_employees, AVG(salary) AS avg_salary, SUM(salary) AS total_salary
FROM employees;
```


12. LIKE
In this example, the LIKE operator is used to match values in the first_name column that start with the letter J. The % symbol is used as a wildcard to match any sequence of characters after the letter J.

This query will return all rows from the employees table where the value in the first_name column starts with the letter J.

```

SELECT *
FROM employees
WHERE first_name LIKE 'J%';
```

13. Wildcards
In this example, the LIKE operator is used to match values in the last_name column that have exactly 4 characters and the 3rd character is i. The _ symbol is used as a wildcard to match any single character in that position.

This query will return all rows from the employees table where the value in the last_name column has exactly 4 characters and the 3rd character is i.

```

SELECT *
FROM employees
WHERE last_name LIKE 'Smi_h';
```


14. IN

In this example, the IN operator is used to match values in the department_id column that are equal to 10, 20, or 30. The values in the parentheses represent the set of values to match against.

This query will return all rows from the employees table where the value in the department_id column is equal to 10, 20, or 30.

```

SELECT *
FROM employees
WHERE department_id IN (10, 20, 30);
```


15. BETWEEN

In this example, the BETWEEN operator is used to match values in the salary column that are greater than or equal to 50000 and less than or equal to 75000.

This query will return all rows from the employees table where the value in the salary column is between 50000 and 75000, inclusive.

```

SELECT *
FROM employees
WHERE salary BETWEEN 50000 AND 75000;
```

16. Aliases
In this example, the AS keyword is used to specify a new name for the first_name and last_name columns in the query result. The new names, 'First Name' and 'Last Name', become the column headers in the query output.

This query will return all the data from the first_name and last_name columns of the employees table, but with the column headers being 'First Name' and 'Last Name' instead of first_name and last_name.

```

SELECT first_name AS 'First Name', last_name AS 'Last Name'
FROM employees;
```


17. Joins

In this example, a JOIN operation is performed between the employees and departments tables based on a common column, department_id. The ON keyword is used to specify the join condition, which says that the values in the department_id column of the employees table must match the values in the department_id column of the departments table.

```

SELECT employees.first_name, employees.last_name, departments.department_name
FROM employees
JOIN departments
ON employees.department_id = departments.department_id;
```

18. INNER JOIN

An INNER JOIN is performed, which returns only the rows where there is a match in both the employees and departments tables.

```

-- INNER JOIN
SELECT employees.first_name, employees.last_name, departments.department_name
FROM employees
JOIN departments
ON employees.department_id = departments.department_id;
```

19. LEFT JOIN

A LEFT JOIN is performed, which returns all the rows from the employees table, and the matching rows from the departments table. If there is no match, the result will contain NULL values for the columns from the departments table.

```

-- LEFT JOIN
SELECT employees.first_name, employees.last_name, departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;
```
20. RIGHT JOIN

A RIGHT JOIN is performed, which returns all the rows from the departments table, and the matching rows from the employees table. If there is no match, the result will contain NULL values for the columns from the employees table.

```

-- RIGHT JOIN
SELECT employees.first_name, employees.last_name, departments.department_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;
```
21. CROSS JOIN

A CROSS JOIN is performed, which returns all possible combinations of rows from the employees and departments tables.

```

-- CROSS JOIN
SELECT employees.first_name, departments.department_name
FROM employees
CROSS JOIN departments;
```
22. Self Join

A SELF JOIN is performed, which joins a table with itself to find relationships within the same table. In this case, the relationship between an employee and their manager is being found by joining the employees table with itself on the employee_id and manager_id columns.

```

-- Self Join
SELECT A.first_name AS employee, B.first_name AS manager
FROM employees A
JOIN employees B
ON A.manager_id = B.employee_id;
```

23. UNION

the UNION clause is used to combine the results of two separate SELECT statements into one result set. The result set will contain all the unique rows from both SELECT statements.

```

SELECT first_name, last_name
FROM employees
WHERE department_id = 1

UNION

SELECT first_name, last_name
FROM employees
WHERE department_id = 2;
```

24. GROUP BY
the GROUP BY clause is used to group the data from the employees table by department_id. The AVG function is used to calculate the average salary for each group.

```

SELECT department_id, AVG(salary)
FROM employees
GROUP BY department_id;
```

25. HAVING
the HAVING clause is used in conjunction with the GROUP BY clause to filter the result set based on a condition applied to the result of the aggregate function. In this case, only the departments with an average salary greater than 50000 will be returned.
```
SELECT department_id, AVG(salary)
FROM employees
GROUP BY department_id
HAVING AVG(salary) > 50000;
```
26. EXISTS
the EXISTS clause is used to check if any rows exist in the subquery that match the condition. In this case, the subquery is checking if any employees are in the departments.
```
SELECT *
FROM departments
WHERE EXISTS (
  SELECT 1
  FROM employees
  WHERE departments.department_id = employees.department_id
);
```
27. ANY, ALL
the ANY and ALL operators are used with subqueries to compare a value to a list of values returned by the subquery. The ANY operator returns true if the value is greater than at least one value in the list, while the ALL operator returns true if the value is greater than all the values in the list.
```
SELECT first_name, last_name
FROM employees
WHERE salary > ANY (
  SELECT salary
  FROM employees
  WHERE department_id = 1
);

SELECT first_name, last_name
FROM employees
WHERE salary > ALL (
  SELECT salary
  FROM employees
  WHERE department_id = 1
);
```
28. INSERT SELECT

The INSERT statement is used to insert data into a table. In this example, the INSERT statement is used to insert data into the products table. The VALUES clause specifies the values for each column in the table, in the order in which the columns are defined. The NOW() function is used to insert the current timestamp into the date_added column.

```
INSERT INTO products (product_name, category, price, date_added)
VALUES ('Apple', 'Fruit', 0.99, NOW())
SELECT product_name, category, price
FROM products
WHERE category = 'Fruit';

```

29. CASE

The CASE statement is used to implement conditional logic in a query. In this example, the CASE statement is used to calculate a new value for the adjusted_price column based on the value of the category column. The WHEN clause specifies the conditions to check, and the THEN clause specifies the value to return if the condition is met.

```

SELECT product_name,
       category,
       price,
       -- Use different price based on category
       CASE 
         WHEN category = 'Fruit' THEN price * 1.1
         WHEN category = 'Vegetable' THEN price * 0.9
         ELSE price
       END AS adjusted_price
FROM products;

```


30. Null Functions
Null functions are used to handle null values in a query. In this example, the COALESCE function is used to return the first non-null value from a list of values. If all values in the list are null, the COALESCE function returns the default value of 0. The ISNULL function is used to return the first argument if it is not null, otherwise it returns the second argument.
```

SELECT product_name,
       category,
       COALESCE(price, 0) AS price,
       -- Use 0 instead of NULL for price
       ISNULL(price, 0) AS price_not_null
FROM products;
```

31. Comments
Comments are used to add descriptive text to SQL code that is ignored by the database engine. In this example, a comment is used to add a description of the INSERT statement to the code. Comments in SQL start with --.
```

-- Add a product to the products table
INSERT INTO products (product_name, category, price, date_added)
VALUES ('Apple', 'Fruit', 0.99, NOW());
```

32. Operators
Operators are used to compare values or perform arithmetic operations in a query. In this example, the greater than operator (>) is used to compare the value of the price column to 1. The result of this comparison is used to calculate a new value for the is_expensive column.

```

SELECT product_name,
       category,
       price,
       -- Check if price is greater than 1
       price > 1 AS is_expensive
FROM products;
```

33. Create DB
The CREATE DATABASE statement is used to create a new database. In this example, a database named mydatabase is created. The database will be stored on the database server and can be used to store tables, views, and other database objects. Note that the exact syntax for creating a database may vary depending on the specific database management system you are using.

```

CREATE DATABASE mydatabase;
```


34. Drop DB

The DROP DATABASE statement is used to delete an existing database. In this example, the DROP DATABASE statement is used to delete a database named mydatabase. This operation will permanently remove the database and all of its contents from the database server.
```

DROP DATABASE mydatabase;
```


35. Create Table
The CREATE TABLE statement is used to create a new table. In this example, a table named products is created with five columns: product_id, product_name, category, price, and date_added. The data type for each column is specified, along with any additional constraints or properties. The AUTO_INCREMENT property is used to specify that the product_id column should be automatically incremented for each new row that is added to the table. The PRIMARY KEY constraint is used to specify that the product_id column is the primary key for the table.
```

CREATE TABLE products (
  product_id INT AUTO_INCREMENT PRIMARY KEY,
  product_name VARCHAR(255),
  category VARCHAR(255),
  price DECIMAL(10,2),
  date_added TIMESTAMP
);

```

36. Drop Table
The DROP TABLE statement is used to delete an existing table. In this example, the DROP TABLE statement is used to delete the products table. This operation will permanently remove the table and all of its contents from the database.

```

DROP TABLE products;

```

37. Alter Table
The ALTER TABLE statement is used to modify the structure of an existing table. In this example, the ALTER TABLE statement is used to add a new column named description to the products table. The data type for the new column is specified as VARCHAR(255). The ADD COLUMN clause is used to specify that a new column should be added to the table.

Note that the exact syntax for each of these statements may vary depending on the specific database management system you are using.

```

ALTER TABLE products
ADD COLUMN description VARCHAR(255);
```


38. Constraints
In this example, a table named products is created with several constraints applied to its columns. The constraints are used to enforce certain rules and limitations on the data that can be stored in the table.

    The NOT NULL constraint is applied to the product_name column, which means that the column cannot contain a NULL value.
    The CHECK constraint is applied to the price column, which means that the value in this column must always be greater than zero.
    The FOREIGN KEY constraint is applied to the category column, which means that the values in this column must match values in the category_name column of the categories table.

```

CREATE TABLE products (
  product_id INT AUTO_INCREMENT PRIMARY KEY,
  product_name VARCHAR(255) NOT NULL,
  category VARCHAR(255),
  price DECIMAL(10,2) CHECK (price > 0),
  date_added TIMESTAMP,
  FOREIGN KEY (category) REFERENCES categories(category_name)
);
```


39. Not Null

The ALTER TABLE statement is used to modify the structure of an existing table. In this example, the ALTER TABLE statement is used to add a NOT NULL constraint to the product_name column of the products table. The MODIFY clause is used to specify that an existing column should be modified, and the NOT NULL constraint is applied to the product_name column, which means that the column cannot contain a NULL value.
```

ALTER TABLE products
MODIFY product_name VARCHAR(255) NOT NULL;
```



40. Unique

The ALTER TABLE statement is used to modify the structure of an existing table. In this example, the ALTER TABLE statement is used to add a UNIQUE constraint to the product_name column of the products table. The ADD CONSTRAINT clause is used to add a constraint to the table, and the UNIQUE constraint is applied to the product_name column, which means that the values in this column must be unique. The constraint is named product_name_unique for reference purposes.

```

ALTER TABLE products
ADD CONSTRAINT product_name_unique UNIQUE (product_name);
```


41. Primary Key

Documentation: A PRIMARY KEY constraint is used to uniquely identify each record in a table. In this example, a PRIMARY KEY constraint is added to the product_id column of the products table. The PRIMARY KEY constraint is combined with the AUTO_INCREMENT keyword, which automatically generates a unique value for the product_id column every time a new record is inserted into the table.

```

CREATE TABLE products (
  product_id INT AUTO_INCREMENT PRIMARY KEY,
  product_name VARCHAR(255) NOT NULL,
  category VARCHAR(255),
  price DECIMAL(10,2),
  date_added TIMESTAMP
);

```

42. Foreign Key

Documentation: A FOREIGN KEY constraint is used to enforce referential integrity between two tables. In this example, a FOREIGN KEY constraint is added to the category column of the products table. The FOREIGN KEY constraint specifies that the values in the category column must match the values in the category_name column of the categories table.

```

CREATE TABLE products (
  product_id INT AUTO_INCREMENT PRIMARY KEY,
  product_name VARCHAR(255) NOT NULL,
  category VARCHAR(255),
  price DECIMAL(10,2),
  date_added TIMESTAMP,
  FOREIGN KEY (category) REFERENCES categories(category_name)
);
```


43. Check

Documentation: A CHECK constraint is used to enforce data integrity by limiting the values that can be stored in a column. In this example, a CHECK constraint is added to the price column of the products table. The CHECK constraint specifies that the value in the price column must always be greater than zero.

```

CREATE TABLE products (
  product_id INT AUTO_INCREMENT PRIMARY KEY,
  product_name VARCHAR(255) NOT NULL,
  category VARCHAR(255),
  price DECIMAL(10,2) CHECK (price > 0),
  date_added TIMESTAMP
);
```

44. Default

Documentation: A DEFAULT constraint is used to specify a default value for a column. In this example, a DEFAULT constraint is added to the date_added column of the products table. The DEFAULT constraint specifies that the default value for the date_added column is the current timestamp.
```

ALTER TABLE products
MODIFY date_added TIMESTAMP DEFAULT CURRENT_TIMESTAMP;
```


45. Create Index
Documentation: An INDEX is used to improve query performance by allowing the database to quickly find specific records. In this example, an INDEX named index_name is created on the table_name table for the column1, column2, etc. columns. The INDEX helps the database to search for records faster by providing a faster way to look up values in the specified columns.

```

CREATE INDEX index_name
ON table_name (column1, column2, ...);
```


46. Auto Increment

Documentation: The AUTO_INCREMENT keyword is used to automatically generate unique values for a column in a table. In this example, the product_id column of the products table is defined with the AUTO_INCREMENT keyword. This means that every time a new record is inserted into the products table, the product_id column will automatically be assigned a unique value, starting from 1 and incrementing by 1 for each subsequent record. The AUTO_INCREMENT keyword is commonly used in combination with the PRIMARY KEY constraint to create a unique identifier for each record in a table.
```

CREATE TABLE products (
  product_id INT AUTO_INCREMENT PRIMARY KEY,
  product_name VARCHAR(255) NOT NULL,
  category VARCHAR(255),
  price DECIMAL(10,2),
  date_added TIMESTAMP
);
```

47. Dates
Documentation: A VIEW is a virtual table that provides a specific perspective on data from one or more underlying tables. In this example, a VIEW named latest_products is created that provides a view of the data in the products table where the date_added column is greater than or equal to the date one month ago. The VIEW is created using a SELECT statement that specifies the columns to include in the view.

```
CREATE VIEW latest_products AS
SELECT product_id, product_name, category, price, date_added
FROM products
WHERE date_added >= DATE_SUB(NOW(), INTERVAL 1 MONTH);
```

48. Views
Documentation: A VIEW is a virtual table that provides a specific perspective on data from one or more underlying tables. In this example, a VIEW named latest_products is created that provides a view of the data in the products table where the date_added column is greater than or equal to the date one month ago. The VIEW is created using a SELECT statement that specifies the columns to include in the view.
```

CREATE VIEW latest_products AS
SELECT product_id, product_name, category, price, date_added
FROM products
WHERE date_added >= DATE_SUB(NOW(), INTERVAL 1 MONTH);
```


49. Data Types

    user_id is an INT data type and is defined as the PRIMARY KEY, which means it is a unique identifier for each record in the table.
    username is a VARCHAR data type with a maximum length of 255 characters, and is defined as NOT NULL, which means it cannot be left blank.
    email is a VARCHAR data type with a maximum length of 255 characters, is defined as NOT NULL, and is also defined as UNIQUE, which means it must have a unique value for each record in the table.
    password is a CHAR data type with a length of 60 characters, and is defined as NOT NULL.
    last_login is a DATE data type, which stores date values.
    is_admin is a BOOLEAN data type, which can store either TRUE or FALSE values.
```

CREATE TABLE users (
  user_id INT PRIMARY KEY,
  username VARCHAR(255) NOT NULL,
  email VARCHAR(255) NOT NULL UNIQUE,
  password CHAR(60) NOT NULL,
  last_login DATE,
  is_admin BOOLEAN
);
```

50. Functions
A FUNCTION in SQL is a subroutine or routine that performs a specific task and returns a value. In this example, a FUNCTION named total_sales is created that takes two DATE parameters (start_date and end_date) and returns a DECIMAL value. The function calculates the total sales in the sales table for the specified date range using a SELECT statement and the SUM aggregate function. The result is stored in the total_sales variable, which is then returned to the calling program using the RETURN statement.

```

CREATE FUNCTION total_sales(start_date DATE, end_date DATE)
RETURNS DECIMAL(10,2)
BEGIN
  DECLARE total_sales DECIMAL(10,2);
  SELECT SUM(total_price) INTO total_sales
  FROM sales
  WHERE sale_date BETWEEN start_date AND end_date;
  RETURN total_sales;
END;
```


51. ASCII
The ASCII function returns the ASCII code of the first character in the argument. In this example, the ASCII function returns the ASCII codes for the capital letter "A" and lowercase letter "a".
```

SELECT ASCII('A'), ASCII('a'), LENGTH('Hello World!'), LOWER('HELLO WORLD!'), UPPER('hello world!')
FROM products;
```


52. CHAR_LENGTH
Documentation: The CHAR_LENGTH function returns the number of characters in a string. In this example, the CHAR_LENGTH function is applied to the product_name column of the products table and the result is aliased as name_length. The query returns the product name and the length of the product name for each row in the products table.

```

SELECT product_name, CHAR_LENGTH(product_name) as name_length
FROM products;
```


53. CHARACTER_LENGTH

The CHARACTER_LENGTH function returns the number of characters in a string. In this example, the CHARACTER_LENGTH function is applied to the product_name column of the products table and the result is aliased as name_length. The query returns the product name and the length of the product name for each row in the products table.

```

SELECT product_name, CHARACTER_LENGTH(product_name) as name_length
FROM products;
```



54. CONCAT
The CONCAT function combines two or more strings into a single string. In this example, the || operator is used to concatenate the first_name and last_name columns of the employees table into a single string, separated by a space. The result is aliased as full_name. The query returns the full name of each employee in the employees table.

```

SELECT first_name || ' ' || last_name as full_name
FROM employees;
```


55. CONCAT_WS
The CONCAT_WS function is a shorthand for the CONCAT function with a separator. In this example, the CONCAT_WS function is used to concatenate the last_name, first_name, and middle_name columns of the employees table into a single string, separated by commas. The first argument to CONCAT_WS is the separator string, which is a comma followed by a space in this case. The result is aliased as full_name. The query returns the full name of each employee in the employees table.

```

SELECT CONCAT_WS(', ', last_name, first_name, middle_name) as full_name
FROM employees;
```


56. FIELD
Documentation: The FIELD function returns the index of a value in a list of values. In this example, the FIELD function is used to find the index of the product_type column in a list of product types. The first argument to FIELD is the column to search in, and the following arguments are the values to search for. The result is aliased as product_type_id. The query returns the product name and the index of the product type for each row in the products table.

```

SELECT product_name, FIELD(product_type, 'Electronics', 'Furniture', 'Clothing') as product_type_id
FROM products;
```


57. FIND_IN_SET
 The FIND_IN_SET function returns the index of a value in a comma-separated list of values. In this example, the FIND_IN_SET function is used to find the index of the product_type column in a comma-separated list of product types. The first argument to FIND_IN_SET is the value to search for, and the second argument is the list of values to search in. The result is aliased as product_type_id. The query returns the product name and the index of the product type for each row in the products table.

```

SELECT product_name, FIND_IN_SET(product_type, 'Electronics, Furniture, Clothing') as product_type_id
FROM products;
```


58. FORMAT
Documentation: The FORMAT function formats a numeric value as a string. In this example, the FORMAT function is used to format the purchase_amount column with two decimal places. The first argument to FORMAT is the numeric value to format, and the second argument is the number of decimal places to use. The result is aliased as purchase_amount. The query returns the customer name and the formatted purchase amount for each row in the purchases table.

```

SELECT customer_name, FORMAT(purchase_amount, 2) as purchase_amount
FROM purchases;
```


59. INSERT
The INSERT statement is used to insert data into a table. In this example, a new row is inserted into the customers table with the values 'John Doe', 'johndoe@example.com', and '123 Main St.' for the customer_name, customer_email, and customer_address columns, respectively.
```

INSERT INTO customers (customer_name, customer_email, customer_address)
VALUES ('John Doe', 'johndoe@example.com', '123 Main St.');
```


60. INSTR
 The INSTR function returns the index position of the first occurrence of a substring within a string. In this example, the INSTR function is used to find the first occurrence of the substring 'new' in the product_description column. The first argument to INSTR is the string to search in, and the second argument is the substring to search for. The result is aliased as new_mention. The query returns the product name and the index position of the first occurrence of the substring for each row in the products table.


```

SELECT product_name, INSTR(product_description, 'new') as new_mention
FROM products;
```


61. LCASE
The LCASE function returns a string in lowercase. In this example, the LCASE function is used to convert the customer_email column to lowercase. The argument to LCASE is the string to convert. The result is aliased as lower_email. The query returns the customer name and the lowercase email for each row in the customers table.
```

SELECT customer_name, LCASE(customer_email) as lower_email
FROM customers;
```


62. LEFT
Documentation: The LEFT function returns a specified number of characters from the beginning of a string. In this example, the LEFT function is used to retrieve the first 20 characters from the product_description column. The first argument to LEFT is the string to extract from, and the second argument is the number of characters to extract. The result is aliased as short_description. The query returns the product name and a shortened version of the product description for each row in the products table.

```

SELECT product_name, LEFT(product_description, 20) as short_description
FROM products;
```


63. LENGTH
Documentation: The LENGTH function returns the length of a string in characters. In this example, the LENGTH function is used to determine the length of the product_description column. The argument to LENGTH is the string to measure. The result is aliased as description_length. The query returns the product name and the length of the product description for each row in the products table.
```

SELECT product_name, LENGTH(product_description) as description_length
FROM products;
```


64. LOCATE

Documentation: The LOCATE function returns the position of the first occurrence of a substring within a string. In this example, the LOCATE function is used to find the first occurrence of the substring 'new' in the product_description column. The first argument to LOCATE is the substring to search for, and the second argument is the string to search in. The result is aliased as new_mention. The query returns the product name and the index position of the first occurrence of the substring for each row in the products table.
```

SELECT product_name, LOCATE('new', product_description) as new_mention
FROM products;

```

65. LOWER
Documentation: The LOWER function returns a string with all the alphabetic characters converted to lowercase. In this example, the LOWER function is used to convert the product_description column to lowercase. The argument to LOWER is the string to convert. The result is aliased as lower_description. The query returns the product name and the lowercase version of the product description for each row in the products table.

```

SELECT product_name, LOWER(product_description) as lower_description
FROM products;
```


66. LPAD
Documentation: The LPAD function returns a string that is left-padded with a specified string to a certain length. In this example, the LPAD function is used to pad the product_code column with zeros to a length of 8 characters. The first argument to LPAD is the string to pad, the second argument is the desired length of the padded string, and the third argument is the string to use for padding. The result is aliased as padded_code. The query returns the product name and the padded product code for each row in the products table.

```
SELECT product_name, LPAD(product_code, 8, '0') as padded_code
FROM products;
```


67. LTRIM
The LTRIM function returns a string with leading spaces removed. In this example, the LTRIM function is used to remove leading spaces from the product_description column. The argument to LTRIM is the string to trim. The result is aliased as trimmed_description. The query returns the product name and the trimmed product description for each row in the products table.

```

SELECT product_name, LTRIM(product_description) as trimmed_description
FROM products;
```


68. MID
The MID function returns a substring from a string, starting from a specified position and for a specified length. In this example, the MID function is used to extract the first 20 characters from the product_description column. The first argument to MID is the string to extract the substring from, the second argument is the starting position of the substring, and the third argument is the length of the substring. The result is aliased as first_20_chars. The query returns the product name and the first 20 characters of the product description for each row in the products table.
```

SELECT product_name, MID(product_description, 1, 20) as first_20_chars
FROM products;
```


69. POSITION
The POSITION function returns the position of the first occurrence of a substring within a string. In this example, the POSITION function is used to find the position of the word "price" within the product_description column. The first argument to POSITION is the substring to search for, and the second argument is the string to search within. The result is aliased as price_position. The query returns the product name and the position of the word "price" within the product description for each row in the products table.

```

SELECT product_name, POSITION('price' IN product_description) as price_position
FROM products;
```


70. REPEAT
Documentation: The REPEAT function returns a string that is repeated a specified number of times. In this example, the REPEAT function is used to repeat the product_description column two times. The first argument to REPEAT is the string to repeat, and the second argument is the number of times to repeat it. The result is aliased as repeated_description. The query returns the product name and the repeated product description for each row in the products table.

```
SELECT product_name, REPEAT(product_description, 2) as repeated_description
FROM products;
```


71. REPLACE
The REPLACE function replaces all occurrences of a specified string within another string. In this example, the REPLACE function is used to replace the word "old" with the word "new" within the product_description column. The first argument to REPLACE is the string to modify, the second argument is the string to search for, and the third argument is the string to replace with. The result is aliased as updated_description. The query returns the product name and the updated product description for each row in the products table.
```

SELECT product_name, REPLACE(product_description, 'old', 'new') as updated_description
FROM products;
```


72. REVERSE
The REVERSE function returns the reverse of a string. In this example, the REVERSE function is used to reverse the product_description column. The argument to REVERSE is the string to reverse. The result is aliased as reversed_description. The query returns the product name and the reversed product description for each row in the products table.

```
SELECT product_name, REVERSE(product_description) as reversed_description
FROM products;
```


73. RIGHT
The RIGHT function returns a specified number of characters from the end of a string. In this example, the RIGHT function is used to extract the last five characters of the product_description column. The first argument to RIGHT is the string to extract from, and the second argument is the number of characters to extract. The result is aliased as last_five_chars. The query returns the product name and the last five characters of the product description for each row in the products table.

```
SELECT product_name, RIGHT(product_description, 5) as last_five_chars
FROM products;
```


74. RPAD
 The RPAD function returns a string that is right-padded with a specified character to a specified length. In this example, the RPAD function is used to pad the product_description column with asterisks to a length of 50 characters. The first argument to RPAD is the string to pad, the second argument is the target length, and the third argument is the padding character. The result is aliased as padded_description. The query returns the product name and the padded product description for each row in the products table.

```
SELECT product_name, RPAD(product_description, 50, '*') as padded_description
FROM products;
```


75. SPACE
The SPACE function returns a string of spaces of a specified length. In this example, the SPACE function is used to create a string of 10 spaces, which is concatenated to the front of the product_description column using the || operator. The result is aliased as indented_description. The query returns the product name and the indented product description for each row in the products table.

```
SELECT product_name, SPACE(10) || product_description as indented_description
FROM products;
```


76. SUBSTR
The SUBSTR function returns a portion of a string. In this example, the SUBSTR function is used to extract the first 20 characters of the product_description column. The first argument to SUBSTR is the string to extract from, the second argument is the starting position of the extracted string, and the third argument is the length of the extracted string. The result is aliased as short_description. The query returns the product name and the shortened product description for each row in the products table.

```
SELECT product_name, SUBSTR(product_description, 1, 20) as short_description
FROM products;
```

