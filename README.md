# Introduction on MySQL
MySQL is one of the most popular open-source relational database management systems (RDBMS). It was originally developed by MySQL AB, a Swedish company, and is now owned by Oracle Corporation. MySQL is widely used for web applications and is a core component of the LAMP (Linux, Apache, MySQL, PHP/Python/Perl) stack.

## Installation Process
- Visit MySQL Website:
  - Go to the official MySQL download page: MySQL Downloads.
- Choose MySQL Installer:
  - Select "MySQL Installer for Windows" from the list of available downloads.
- Download Installer:
  - Choose the web installer (small size) or the full installer (larger file with all features included).
  - Click "Download" and then select "No thanks, just start my download" on the next page.
- Run the Installer:
  - Open the downloaded .msi file to launch the installer.
- Choose Installation Type:
  - Select "Custom" to install specific components, or "Developer Default" to install the full MySQL package, including the command line tools.
- Select MySQL Server and Command Line Tools:
  - Ensure that "MySQL Server" and "MySQL Command Line Tools" are selected in the components to be installed.
- Complete Installation:
  - Follow the on-screen instructions to complete the installation process.
- Configure MySQL:
  - After installation, the MySQL Installer will guide you through the configuration process. Set up the server, root password, and other options as needed.
- Access MySQL Command Line:
  - Once installed, you can access the MySQL Command Line by searching for "MySQL" in the Start Menu or running mysql from the Command Prompt.

## Queries on Database
1. Creating a Database
   - Query:
     ```sql
     CREATE DATABASE database_name;
     ```
   - Description:
     This command creates a new database with the specified name. Replace `database_name` with your desired name. If a database with that name already exists, an error will occur unless you use the `IF NOT EXISTS` clause.
   - Example:
     ```sql
     CREATE DATABASE my_database;
     ```
     This will create a database named `my_database`.

2. Showing Databases
   - Query:
     ```sql
     SHOW DATABASES;
     ```
   - Description:
     This command lists all the databases currently available on the MySQL server. It’s useful for verifying whether a particular database exists or for seeing all databases you can access.
   - Example:
     ```sql
     SHOW DATABASES;
     ```
     This will display a list of all databases on the server.

3. Selecting a Database to Use
   - Query:
     ```sql
     USE database_name;
     ``` 
   - Description:
     This command selects a specific database to work with. After running this command, all subsequent queries will be executed on the selected database until you change it or disconnect.
   - Example:
     ```sql
     USE my_database;
     ```
     This command selects `my_database` for use.

4. Showing the Current Database
   - Query:
     ```sql
     SELECT DATABASE();
     ```
   - Description:
     This command returns the name of the currently selected database. It’s useful when you want to confirm which database is active in your session.
   - Example:
     ```sql
     SELECT DATABASE();
     ```
     This will show the name of the database you are currently using.

5. Dropping a Database
   - Query:
     ```sql
     DROP DATABASE database_name;
     ```
   - Description:
     This command deletes a database and all its associated data permanently. Use with caution, as this action cannot be undone.
   - Example:
     ```sql
     DROP DATABASE my_database;
     ```
     This will delete the `my_database` database from the server.

## Data Types in MySQL

1. Numeric Data Types
   - INT (INTEGER):
     - Stores whole numbers, both positive and negative.
     - Example:
       ```sql
       INT(11);
       ```

   - TINYINT:
     - A very small integer. Typically used for boolean values (0 or 1).
     - Example:
       ```sql
       TINYINT(1);
       ```

   - SMALLINT:
     - A small integer.
     - Example:
       ```sql
       SMALLINT(5);
       ```

   - MEDIUMINT:
     - A medium-sized integer.
     - Example:
       ```sql
       MEDIUMINT(8);
       ```

   - BIGINT:
     - A large integer, useful for storing very large numbers.
     - Example:
       ```sql
       BIGINT(20);
       ```

   - FLOAT:
     - A floating-point number with single precision.
     - Example:
       ```sql
       FLOAT(7,4);  -- 7 digits total, 4 after the decimal
       ```

   - DOUBLE:
     - A double-precision floating-point number.
     - Example:
       ```sql
       DOUBLE(15,8);
       ```

   - DECIMAL:
     - A fixed-point number, where you can specify the total number of digits and the number of digits after the decimal.
     - Example:
       ```sql
       DECIMAL(10,2);  -- 10 digits total, 2 after the decimal
       ```

2. String Data Types
   - CHAR:
     - A fixed-length string. If the string is shorter than the defined length, it is padded with spaces.
     - Example:
       ```sql
       CHAR(10);
       ```

   - VARCHAR:
     - A variable-length string. More flexible than CHAR as it only uses as much space as needed.
     - Example:
       ```sql
       VARCHAR(255);
       ```

   - TEXT:
     - Used for large text data, like paragraphs. Variants include TINYTEXT, TEXT, MEDIUMTEXT, and LONGTEXT.
     - Example:
       ```sql
       TEXT;
       ```

   - BLOB:
     - Binary Large Object, used to store binary data like images or multimedia files. Variants include TINYBLOB, BLOB, MEDIUMBLOB, and LONGBLOB.
     - Example:
       ```sql
       BLOB;
       ```

   - ENUM:
     - A string object that can have one of the predefined values.
     - Example:
       ```sql
       ENUM('small', 'medium', 'large');
       ```

   - SET:
     - Similar to ENUM, but allows multiple values from the predefined list.
     - Example:
       ```sql
       SET('a', 'b', 'c');
       ```

3. Date and Time Data Types
   - DATE:
     - Stores a date value in the format YYYY-MM-DD.
     - Example:
       ```sql
       DATE;
       ```

   - TIME:
     - Stores a time value in the format HH:MM:SS.
     - Example:
       ```sql
       TIME;
       ```

   - DATETIME:
     - Stores both date and time in the format YYYY-MM-DD HH:MM:SS.
     - Example:
       ```sql
       DATETIME;
       ```

   - TIMESTAMP:
     - Stores the number of seconds since the Unix epoch (1970-01-01 00:00:00). Automatically updates to the current date and time on record update.
     - Example:
       ```sql
       TIMESTAMP;
       ```

   - YEAR:
     - Stores a year in a 4-digit format.
     - Example:
       ```sql
       YEAR(4);
       ```

## Queries on Table

1. Show All Tables
   - Query:
     ```sql
     SHOW TABLES;
     ```
   - Description:
     This command lists all the tables in the currently selected database.
   - Example:
     ```sql
     SHOW TABLES;
     ```
     This will display all the tables in the current database.

2. Show Table Structure (Schema)
   - Query:
     ```sql
     DESCRIBE table_name;
     ```
   - Description:
     This command shows the structure of a specified table, including column names, data types, and other attributes.
   - Example:
     ```sql
     DESCRIBE employees;
     ```
     This will show the structure of the `employees` table.

   - Alternate Query:
     ```sql
     SHOW COLUMNS FROM table_name;
     ```
     This also provides the same information as `DESCRIBE`.

3. Create a Table
   - Query:
     ```sql
     CREATE TABLE table_name (
         column1_name data_type constraints,
         column2_name data_type constraints,
         ...
     );
     ```
   - Description:
     This command creates a new table with specified columns and data types. You can also include constraints such as `PRIMARY KEY`, `NOT NULL`, `UNIQUE`, etc.
   - Example:
     ```sql
     CREATE TABLE employees (
         employee_id INT AUTO_INCREMENT PRIMARY KEY,
         first_name VARCHAR(50) NOT NULL,
         last_name VARCHAR(50) NOT NULL,
         hire_date DATE,
         salary DECIMAL(10,2)
     );
     ```
     This will create an `employees` table with columns for `employee_id`, `first_name`, `last_name`, `hire_date`, and `salary`.

4. Show Table Creation Statement
   - Query:
     ```sql
     SHOW CREATE TABLE table_name;
     ```
   - Description:
     This command displays the `CREATE TABLE` statement that was used to create the specified table. It is helpful when you need to understand how a table was originally defined.
   - Example:
     ```sql
     SHOW CREATE TABLE employees;
     ```
     This will show the exact SQL statement used to create the `employees` table.

5. Drop a Table
   - Query:
     ```sql
     DROP TABLE table_name;
     ```
   - Description:
     This command deletes a table and all its data permanently. Use it carefully, as this action cannot be undone.
   - Example:
     ```sql
     DROP TABLE employees;
     ```
     This will delete the `employees` table from the database.
5. Drop a Table
   - Query:
     ```sql
     DROP TABLE table_name;
     ```
   - Description:
     This command deletes a table and all its data permanently from the database.

   - Example:
     ```sql
     DROP TABLE employees;
     ```
     This will delete the `employees` table from the database.

6. Alter a Table

   1. Add a New Column
      ```sql
      ALTER TABLE table_name ADD column_name data_type;
      ```

      Example:
      ```sql
      ALTER TABLE employees ADD email VARCHAR(100);
      ```
      This adds a new column `email` to the `employees` table.

   2. Modify an Existing Column
      ```sql
      ALTER TABLE table_name MODIFY COLUMN column_name new_data_type;
      ```

      Example:
      ```sql
      ALTER TABLE employees MODIFY COLUMN salary DECIMAL(12,2);
      ```
      This changes the data type of the `salary` column in the `employees` table.

   3. Change a Column Name
      ```sql
      ALTER TABLE table_name CHANGE old_column_name new_column_name data_type;
      ```

      Example:
      ```sql
      ALTER TABLE employees CHANGE first_name first VARCHAR(50);
      ```
      This renames the `first_name` column to `first` and keeps the data type as `VARCHAR(50)`.

   4. Drop (Delete) a Column
      ```sql
      ALTER TABLE table_name DROP COLUMN column_name;
      ```

      Example:
      ```sql
      ALTER TABLE employees DROP COLUMN email;
      ```
      This deletes the `email` column from the `employees` table.

7. Rename a Table
   - Query:
     ```sql
     RENAME TABLE old_table_name TO new_table_name;
     ```
   - Description:
     This command renames an existing table.

   - Example:
     ```sql
     RENAME TABLE employees TO staff;
     ```
     This will rename the `employees` table to `staff`.

8. Copy a Table
   - Query:
     ```sql
     CREATE TABLE new_table_name AS SELECT * FROM existing_table_name;
     ```
   - Description:
     This command creates a new table by copying the structure and data from an existing table.

   - Example:
     ```sql
     CREATE TABLE employees_backup AS SELECT * FROM employees;
     ```
     This will create a new table `employees_backup` with the same structure and data as the `employees` table.

## CRUD Operation on Table

1. Inserting Data into the `employees` Table

   Assume the `employees` table has the following columns:
   - `employee_id` (INT, AUTO_INCREMENT, PRIMARY KEY)
   - `first_name` (VARCHAR(50))
   - `last_name` (VARCHAR(50))
   - `email` (VARCHAR(100))
   - `hire_date` (DATE)
   - `salary` (DECIMAL(10,2))

   SQL Insert Statements:
   ```sql
   INSERT INTO employees (first_name, last_name, email, hire_date, salary)
   VALUES
   ('John', 'Doe', 'john.doe@example.com', '2023-01-15', 60000.00),
   ('Jane', 'Smith', 'jane.smith@example.com', '2022-11-22', 65000.00),
   ('Alice', 'Johnson', 'alice.johnson@example.com', '2021-08-10', 72000.00),
   ('Bob', 'Brown', 'bob.brown@example.com', '2020-05-18', 50000.00),
   ('Charlie', 'Williams', 'charlie.williams@example.com', '2019-02-25', 80000.00),
   ('David', 'Miller', 'david.miller@example.com', '2021-09-14', 56000.00),
   ('Emma', 'Davis', 'emma.davis@example.com', '2023-03-30', 74000.00),
   ('Frank', 'Garcia', 'frank.garcia@example.com', '2022-12-05', 67000.00),
   ('Grace', 'Martinez', 'grace.martinez@example.com', '2020-07-19', 62000.00),
   ('Henry', 'Lopez', 'henry.lopez@example.com', '2018-04-23', 78000.00);
    ```
2. Selecting Data from the `employees` Table

### SQL Select Statement:
```sql
SELECT * FROM employees;
```
1. **Update Specific Columns**
   - **Query:**
     ```sql
     UPDATE table_name SET column_name = new_value WHERE condition;
     ```
   - **Example:**
     ```sql
     UPDATE employees SET salary = 65000.00 WHERE employee_id = 1;
     ```
     This updates the `salary` of the employee with `employee_id` 1.

2. **Update Multiple Columns**
   - **Query:**
     ```sql
     UPDATE table_name SET column1_name = new_value1, column2_name = new_value2 WHERE condition;
     ```
   - **Example:**
     ```sql
     UPDATE employees SET salary = 70000.00, email = 'john.new@example.com' WHERE employee_id = 1;
     ```
     This updates the `salary` and `email` of the employee with `employee_id` 1.

3. **Update All Records**
   - **Query:**
     ```sql
     UPDATE table_name SET column_name = new_value;
     ```
   - **Example:**
     ```sql
     UPDATE employees SET salary = 60000.00;
     ```
     This sets the `salary` to `60000.00` for all employees in the table.

### Delete Query on Table

1. **Delete Specific Records**
   - **Query:**
     ```sql
     DELETE FROM table_name WHERE condition;
     ```
   - **Example:**
     ```sql
     DELETE FROM employees WHERE employee_id = 1;
     ```
     This deletes the record with `employee_id` 1 from the `employees` table.

2. **Delete Multiple Records Based on a Condition**
   - **Query:**
     ```sql
     DELETE FROM table_name WHERE condition;
     ```
   - **Example:**
     ```sql
     DELETE FROM employees WHERE hire_date < '2022-01-01';
     ```
     This deletes all records where the `hire_date` is before January 1, 2022.

3. **Delete All Records from a Table**
   - **Query:**
     ```sql
     DELETE FROM table_name;
     ```
   - **Example:**
     ```sql
     DELETE FROM employees;
     ```
     This deletes all records from the `employees` table but keeps the table structure intact.

### Summary of `DELETE` Operations

- **Delete Specific Record:** Removes a single record based on a unique identifier or condition.
- **Delete Multiple Records:** Removes all records that meet a specific condition.
- **Delete All Records:** Clears all records from a table, leaving the table empty but intact.

### Built-in Functions

1. **String Functions**

   - `CONCAT(str1, str2, ...)`
     - **Description:** Concatenates two or more strings.
     - **Example:**
       ```sql
       SELECT CONCAT('Hello', ' ', 'World!');
       -- Output: 'Hello World!'
       ```

   - `SUBSTRING(str, start, length)`
     - **Description:** Extracts a substring from a string.
     - **Example:**
       ```sql
       SELECT SUBSTRING('Hello World', 1, 5);
       -- Output: 'Hello'
       ```

   - `LENGTH(str)`
     - **Description:** Returns the length of a string.
     - **Example:**
       ```sql
       SELECT LENGTH('Hello World');
       -- Output: 11
       ```

   - `UPPER(str)`
     - **Description:** Converts a string to uppercase.
     - **Example:**
       ```sql
       SELECT UPPER('Hello World');
       -- Output: 'HELLO WORLD'
       ```

   - `LOWER(str)`
     - **Description:** Converts a string to lowercase.
     - **Example:**
       ```sql
       SELECT LOWER('Hello World');
       -- Output: 'hello world'
       ```

   - `TRIM(str)`
     - **Description:** Removes leading and trailing spaces from a string.
     - **Example:**
       ```sql
       SELECT TRIM('   Hello World   ');
       -- Output: 'Hello World'
       ```

2. **Numeric Functions**

   - `ROUND(number, decimals)`
     - **Description:** Rounds a number to a specified number of decimal places.
     - **Example:**
       ```sql
       SELECT ROUND(123.4567, 2);
       -- Output: 123.46
       ```

   - `FLOOR(number)`
     - **Description:** Returns the largest integer less than or equal to a number.
     - **Example:**
       ```sql
       SELECT FLOOR(123.456);
       -- Output: 123
       ```

   - `CEIL(number)` or `CEILING(number)`
     - **Description:** Returns the smallest integer greater than or equal to a number.
     - **Example:**
       ```sql
       SELECT CEIL(123.456);
       -- Output: 124
       ```

   - `ABS(number)`
     - **Description:** Returns the absolute value of a number.
     - **Example:**
       ```sql
       SELECT ABS(-123.456);
       -- Output: 123.456
       ```

3. **Date and Time Functions**

   - `NOW()`
     - **Description:** Returns the current date and time.
     - **Example:**
       ```sql
       SELECT NOW();
       -- Output: '2024-08-20 12:34:56' (current date and time)
       ```

   - `CURDATE()`
     - **Description:** Returns the current date.
     - **Example:**
       ```sql
       SELECT CURDATE();
       -- Output: '2024-08-20'
       ```

   - `CURTIME()`
     - **Description:** Returns the current time.
     - **Example:**
       ```sql
       SELECT CURTIME();
       -- Output: '12:34:56' (current time)
       ```

   - `DATE_FORMAT(date, format)`
     - **Description:** Formats a date according to the specified format.
     - **Example:**
       ```sql
       SELECT DATE_FORMAT(NOW(), '%Y-%m-%d');
       -- Output: '2024-08-20'
       ```

   - `DATEDIFF(date1, date2)`
     - **Description:** Returns the number of days between two dates.
     - **Example:**
       ```sql
       SELECT DATEDIFF('2024-08-20', '2024-08-15');
       -- Output: 5
       ```

4. **Aggregate Functions**

   - `COUNT(expression)`
     - **Description:** Returns the number of rows that match a specified condition.
     - **Example:**
       ```sql
       SELECT COUNT(*) FROM employees;
       -- Output: (number of rows in employees table)
       ```

   - `SUM(expression)`
     - **Description:** Returns the sum of the values in a specified column.
     - **Example:**
       ```sql
       SELECT SUM(salary) FROM employees;
       -- Output: (total salary of all employees)
       ```

   - `AVG(expression)`
     - **Description:** Returns the average value of a specified column.
     - **Example:**
       ```sql
       SELECT AVG(salary) FROM employees;
       -- Output: (average salary of all employees)
       ```

   - `MAX(expression)`
     - **Description:** Returns the maximum value of a specified column.
     - **Example:**
       ```sql
       SELECT MAX(salary) FROM employees;
       -- Output: (highest salary of all employees)
       ```

   - `MIN(expression)`
     - **Description:** Returns the minimum value of a specified column.
     - **Example:**
       ```sql
       SELECT MIN(salary) FROM employees;
       -- Output: (lowest salary of all employees)
       ```

5. **Control Flow Functions**

   - `IF(condition, true_value, false_value)`
     - **Description:** Returns `true_value` if the condition is true, otherwise `false_value`.
     - **Example:**
       ```sql
       SELECT IF(salary > 60000, 'High', 'Low') FROM employees;
       -- Output: 'High' or 'Low' based on the salary value
       ```

   - `CASE WHEN`
     - **Description:** Provides conditional logic similar to if-else.
     - **Example:**
       ```sql
       SELECT CASE
                WHEN salary > 70000 THEN 'High'
                WHEN salary > 50000 THEN 'Medium'
                ELSE 'Low'
              END AS salary_category
       FROM employees;
       ```
### Foreign Key

1. **Understanding Foreign Key**

   **Foreign Key Concept:**
   - A foreign key is a column or a set of columns in one table that uniquely identifies rows in another table. It is used to enforce referential integrity between tables.
   - The foreign key in the child table references the primary key in the parent table, ensuring that the relationship between records in the two tables remains consistent.
   - When a record in the parent table is updated or deleted, the changes can be propagated to the child table based on the specified actions (`ON DELETE`, `ON UPDATE`).

2. **Create the `departments` Table**

   Create a `departments` table that will be referenced by the `employees` table through a foreign key.

   ```sql
   CREATE TABLE departments (
       department_id INT AUTO_INCREMENT PRIMARY KEY,
       department_name VARCHAR(100) NOT NULL
   );

3. Alter the `employees` Table to Add Foreign Key

Assuming the `employees` table already exists, add a `department_id` column and define it as a foreign key that references the `departments` table.

```sql
ALTER TABLE employees
ADD COLUMN department_id INT;

ALTER TABLE employees
ADD FOREIGN KEY (department_id) REFERENCES departments(department_id)
    ON DELETE SET NULL
    ON UPDATE CASCADE;
```
4. Insert Data into the `departments` Table

Insert 10 records into the `departments` table with 5 unique department types.

```sql
-- Insert unique department names
INSERT INTO departments (department_name) 
VALUES 
    ('Sales'), 
    ('Marketing'), 
    ('Human Resources'), 
    ('Finance'), 
    ('IT');
5. Update the employees Table with Department Information
Update the employees table to include department information.

sql
Copy code
-- Update employees with department information
UPDATE employees SET department_id = 1 WHERE employee_id IN (1, 2, 3);
UPDATE employees SET department_id = 2 WHERE employee_id = 4;
UPDATE employees SET department_id = 3 WHERE employee_id IN (5, 6);
UPDATE employees SET department_id = 4 WHERE employee_id IN (7, 8);
UPDATE employees SET department_id = 5 WHERE employee_id IN (9, 10);
```
### Group By

#### 1. `GROUP BY`

**Description:**
The `GROUP BY` clause is used to group rows that have the same values in specified columns into summary rows. It is often used with aggregate functions like `SUM()`, `COUNT()`, `AVG()`, `MAX()`, and `MIN()` to produce a single value for each group.

**Example:**
Find the total salary for each department.

```sql
SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id;
```
### `LIKE` Operator

#### Wildcard Characters

- `%`: Represents zero or more characters.
- `_`: Represents a single character.

#### 1. Basic `LIKE` Usage

**Description:**
Use `LIKE` to find records that match a specific pattern.

**Example:**
Find employees whose last name starts with 'S'.

```sql
SELECT first_name, last_name
FROM employees
WHERE last_name LIKE 'S%';
```
#### 2. `LIKE` with `%` Wildcard

**Description:**
Use `%` to match any sequence of characters.

**Example:**
Find employees whose first name contains 'ann'.

```sql
SELECT first_name, last_name
FROM employees
WHERE first_name LIKE '%ann%';
```
#### 3. `LIKE` with `_` Wildcard

**Description:**
Use `_` to match a single character.

**Example:**
Find employees whose last name is exactly 5 characters long and starts with 'J'.

```sql
SELECT first_name, last_name
FROM employees
WHERE last_name LIKE 'J____';
```
#### 4. `LIKE` for Exact Match

**Description:**
Match an exact string using `LIKE` with no wildcards.

**Example:**
Find employees whose email address ends with '@example.com'.

```sql
SELECT first_name, last_name, email
FROM employees
WHERE email LIKE '%@example.com';
```
#### 5. `LIKE` for Multiple Patterns

**Description:**
Use `LIKE` with multiple patterns combined using `OR`.

**Example:**
Find employees whose department is either 'Sales' or 'Marketing'.

```sql
SELECT first_name, last_name, department_id
FROM employees
WHERE department_id IN (SELECT department_id FROM departments WHERE department_name LIKE 'Sales' OR department_name LIKE 'Marketing');
```
#### 6. Case Sensitivity with `LIKE`

**Description:**
The case sensitivity of `LIKE` depends on the collation of the column. In some databases, `LIKE` is case-insensitive by default.

**Example:**
Find employees whose last name contains 'smith', regardless of case.

```sql
SELECT first_name, last_name
FROM employees
WHERE last_name LIKE '%smith%';
```
### Summary

- `LIKE 'S%'`: Matches any string starting with 'S'.
- `LIKE '%ann%'`: Matches any string containing 'ann'.
- `LIKE 'J____'`: Matches any string starting with 'J' and followed by exactly 4 characters.
- `LIKE '%@example.com'`: Matches email addresses ending with '@example.com'.
- `LIKE '%smith%'`: Matches any string containing 'smith', regardless of case.

The `LIKE` operator is a flexible way to search for patterns within text columns in SQL.

### ORDER BY

**Syntax:**

```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC|DESC], column2 [ASC|DESC], ...;
```
### `ORDER BY : `

- `ASC`: Sorts in ascending order (default).
- `DESC`: Sorts in descending order.

#### 1. Single Column Sort

**Description:**
Sort the result set by a single column.

**Example:**
Retrieve employees sorted by their last name in ascending order.

```sql
SELECT first_name, last_name
FROM employees
ORDER BY last_name ASC;
#### 2. Multiple Columns Sort

**Description:**
Sort the result set by multiple columns. The sorting is done first by the first column, then by the second column, and so on.

**Example:**
Retrieve employees sorted by department first (ascending) and then by salary within each department (descending).

```sql
SELECT first_name, last_name, department_id, salary
FROM employees
ORDER BY department_id ASC, salary DESC;
```
### 3. Sort with NULL Values

**Description:**
Control the position of `NULL` values in the result set. By default, `NULL` values are sorted at the end when sorting in ascending order and at the beginning when sorting in descending order. This behavior can sometimes be overridden by specific SQL database systems.

**Example:**
Retrieve employees sorted by salary with `NULL` values appearing first.

```sql
SELECT first_name, last_name, salary
FROM employees
ORDER BY salary ASC NULLS FIRST;
```
Note: The NULLS FIRST and NULLS LAST options are supported in some SQL databases like PostgreSQL, but might not be available in others like MySQL.
### 4. Using `ORDER BY` with Aggregate Functions

**Description:**
Sort the result set based on aggregated values.

**Example:**
Find the total salary for each department and sort the results by the total salary in descending order.

```sql
SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id
ORDER BY total_salary DESC;
### Subqueries and Nested Subqueries
```
The `ORDER BY` clause is essential for organizing query results in a meaningful and readable way.

## Subqueries and Nested Subqueries

### 1. Subquery in the `WHERE` Clause

**Description:**
Filter results based on values from a nested query.

**Example:**
Find employees who earn more than the average salary in their department.

```sql
SELECT first_name, last_name, salary
FROM employees e
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
    WHERE department_id = e.department_id
);
```
### 2. Subquery in the `FROM` Clause

**Description:**
Create a temporary result set that can be queried by the outer query.

**Example:**
Find the total number of employees per department and select departments with more than 5 employees.

```sql
SELECT department_id, employee_count
FROM (
    SELECT department_id, COUNT(*) AS employee_count
    FROM employees
    GROUP BY department_id
) AS dept_counts
WHERE employee_count > 5;
```
### 3. Subquery in the `SELECT` Clause

**Description:**
Include additional columns in the result set based on a subquery.

**Example:**
List all employees with the number of employees in their department.

```sql
SELECT first_name, last_name, department_id,
       (SELECT COUNT(*)
        FROM employees e2
        WHERE e2.department_id = e1.department_id) AS total_in_department
FROM employees e1;
```
### 4. Correlated Subquery

**Description:**
A subquery that references columns from the outer query.

**Example:**
Find departments where there are employees earning more than $70,000.

```sql
SELECT department_id
FROM employees e
WHERE EXISTS (
    SELECT 1
    FROM employees e2
    WHERE e2.department_id = e.department_id
    AND e2.salary > 70000
);
```
### 5. Subquery with `IN` Operator

**Description:**
Use a subquery to filter results based on a set of values.

**Example:**
Find employees who work in departments with names 'Sales' or 'Marketing'.

```sql
SELECT first_name, last_name
FROM employees
WHERE department_id IN (
    SELECT department_id
    FROM departments
    WHERE department_name IN ('Sales', 'Marketing')
);
```
### 6. Subquery with `ANY` Operator

**Description:**
Compare a value to any value returned by the subquery.

**Example:**
Find employees whose salary is greater than any salary in the 'Finance' department.

```sql
SELECT first_name, last_name, salary
FROM employees
WHERE salary > ANY (
    SELECT salary
    FROM employees
    WHERE department_id = (
        SELECT department_id
        FROM departments
        WHERE department_name = 'Finance'
    )
);
```
#### 7. Subquery with `ALL` Operator

**Description:**
Compare a value to all values returned by the subquery.

**Example:**
Find employees whose salary is greater than all salaries in the 'Human Resources' department.

```sql
SELECT first_name, last_name, salary
FROM employees
WHERE salary > ALL (
    SELECT salary
    FROM employees
    WHERE department_id = (
        SELECT department_id
        FROM departments
        WHERE department_name = 'Human Resources'
    )
);
```
### Joins

#### 1. INNER JOIN

**Description:**
Returns records that have matching values in both tables.

**Example:**
Find employees along with their department names.

```sql
SELECT e.first_name, e.last_name, d.department_name
FROM employees e
INNER JOIN departments d ON e.department_id = d.department_id;
```
#### 2. LEFT JOIN (or LEFT OUTER JOIN)

**Description:**
Returns all records from the left table and the matched records from the right table. Non-matching records from the right table will be `NULL`.

**Example:**
Find all employees and their department names, including employees who do not belong to any department.

```sql
SELECT e.first_name, e.last_name, d.department_name
FROM employees e
LEFT JOIN departments d ON e.department_id = d.department_id;
```
#### 3. RIGHT JOIN (or RIGHT OUTER JOIN)

**Description:**
Returns all records from the right table and the matched records from the left table. Non-matching records from the left table will be `NULL`.

**Example:**
Find all departments and their employees, including departments with no employees.

```sql
SELECT d.department_name, e.first_name, e.last_name
FROM departments d
RIGHT JOIN employees e ON d.department_id = e.department_id;
```
#### 4. FULL JOIN (or FULL OUTER JOIN)

**Description:**
Returns all records when there is a match in either left or right table. Non-matching records from both tables will be `NULL`.

**Example:**
Find all employees and all departments, showing all possible combinations including those that do not match.

```sql
SELECT e.first_name, e.last_name, d.department_name
FROM employees e
FULL OUTER JOIN departments d ON e.department_id = d.department_id;
```
 **Note:** Not all SQL databases support `FULL OUTER JOIN` directly. If it's not supported, you might need to use a combination of `LEFT JOIN` and `RIGHT JOIN` with `UNION`.

#### 5. CROSS JOIN

**Description:**
Returns the Cartesian product of both tables, meaning all possible combinations of rows between the tables.

**Example:**
Find all possible combinations of employees and departments.

```sql
SELECT e.first_name, d.department_name
FROM employees e
CROSS JOIN departments d;
```
#### 6. SELF JOIN

**Description:**
A self join is used to join a table with itself. This is useful for hierarchical or recursive data.

**Example:**
Find employees and their managers (assuming the `employees` table has a `manager_id` column that references the `employee_id`).

```sql
SELECT e1.first_name AS employee_name, e2.first_name AS manager_name
FROM employees e1
LEFT JOIN employees e2 ON e1.manager_id = e2.employee_id;
```