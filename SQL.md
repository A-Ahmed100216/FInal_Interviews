# SQL
## What is SQL
* Structured Query Langauge
* Allows you to manage data in relational databases (each row is a record with a unique id called the key, columns hold attributes )

# What is a foreign key?
A foreign key is used to link two tables together via referring to the primary key of one table. The purpose of this is to ensure consistency throughout the related tables. It is all too common to make simple spelling errors which would prevent the link from being formed. Using a foreign key ensures the data in the linking columns matches exactly.

# What is DML and DDL?
Operations which can be performed on a database are typically categorised into 4 categories relating to the type of action being performed:

DDL - Data Definition Language - Actions includeCREATE, ALTER, DROP, TRUNCATE, RENAME
DML- Data Manipulation Language - INSERT, UPDATE, DELETE, MERGE, CALL
DQL - Data Query Language - SELECT
DCL - Data Control Language - GRANT, REVOKE I have experience in using these actions to create tables and query within the northwind database which is the default database within Microsoft Azure. One task I was asked to complete was CRUD a database within Python and then import data from a csv file. This task entailed creating a table within the database, importing data and allowing users to query via a specific search criterion, in this case, movie name. Users, could also implement DML and update the table with their own inputs. The result of this task was a functioning movie table which users could access within python. I also have experince in using SQL with Python in a project wherein i created an airline booking system.

# Normal Forms
* Don’t want to duplicate data.
* Rules or best practices for designing databases.
* 3 main types:
1. First Normal Form
  * Make everything atomic- data must be presented as small as it can be- first and last, don’t need full
  * No repeating groups i.e. author 1, author 2, etc.
2. 2nd Normal Form (2NF)
  * Satisfies 1NF
  * All non-key attributes are fully functional dependent and the primary key.
3. 3rd Normal Form (3NF)
  * Satisfies in 2NF
  * There is NO Transitive Functional Dependency:
  * A Transitive Functional Dependency is when a non-key column is functionally dependent on another non-key column, which is functionally dependent on the primary key.


# Syntax

## Data Types
* VARCHAR – Adaptable to different lengths of characters. Records MAX size. Equivalent to strings in python.
* CHARACTER or CHAR- data at fixed length, fixed amount of space used.
* INT – Hold a whole number/integer value (variations include BIGINT, SMALLINT, TINYINT). Can be positive or negatives.
* DATE or TIME or DATETIME – stores date, time or both date and time.
* DECIMAL or NUMERIC- fixed precision and scale (digits to right of decimal point) numbers.
* BINARY – stores binary data such as images or files.
* FLOAT – scientific use (very large numbers).
BIT – equivalent to binary (0,1 or NULL).

### Database Manipulation
1. Create a database or table
```SQL
Create DATABASE database_name
USE Booksaurus_Aminah --Can also select database from drop down
CREATE TABLE table_name (
    Column_1 INT NOT NULL IDENTITY(1,1) PRIMARY KEY, -- Primary key
    Column_2 VARCHAR(100) NOT NULL, --VARCHAR - Any characters, with limit of 100 characters
    Column_3 VARCHAR(MAX) NOT NULL, --VARCHAR - Any characters, with no limit
    Column_4 VARCHAR(15) NOT NULL
);
```
2. Delete an entity
```SQL
DROP TABLE <table_name>
```
3. Insert values into a table
```SQL
INSERT INTO table_name(Column_2, Column_3, Column_4) --primary key column populated automatically
VALUES ('Value 1', 'Value 2','Value 3')
```
4. Alter an entry
```SQL
ALTER TABLE <table_name>
ADD/RENAME/MODIFY/DROP column_name DATATYPE;
```
5. Update table
```SQL
UPDATE <table_name>
	SET column_name = ‘new value’
WHERE entry you want to change = 'value'
```
6. Delete an entry
```SQL
DELETE FROM <table_name?
	WHERE entry you want to change = 'value'
```
### Database Querying
*Examples query Northwind database*    
1. Basic Querying
```SQL
SELECT * FROM table_name -- Select all columns
SELECT column_name FROM table_name -- Select specific column name
--Example
SELECT CustomerID, city FROM Customers
```
2. WHERE - Limit to a specified criterion
```sql
SELECT column_name FROM database WHERE column_name='value'
-- Example
SELECT ProductName,UnitPrice, CategoryID FROM Products WHERE CategoryID=1;
```
3. COUNT - Counts the number of times the query is satisfied
```SQL
SELECT COUNT(*) FROM column_name WHERE column_name='value'
-- Example
SELECT COUNT(*) FROM Customers WHERE Country='France'
```
4. BETWEEN - Query a specified range
```sql
SELECT column_name FROM table_name WHERE column_name BETWEEN value1 AND value2;
-- Example
SELECT * from EmployeeTerritories where TerritoryID BETWEEN 06800 and 09999;
```
5. AS - Create an alias of an existing column
```sql
SELECT column_name AS 'new_name' FROM table_name
-- Example
SELECT CompanyName AS 'CompanyName',
    City +', ' + Country AS 'City'
FROM Customers;
```
6. DISTINCT - Eliminate duplicate entries
```sql
SELECT Distinct column_name FROM table_name WHERE column_name IS 'value'
SELECT Distinct Country FROM Customers WHERE Region IS NOT NULL
```
7. LIKE - Used with wildcards
  * % = multiple unknown characters
  ```SQL
  SELECT ProductName FROM Products WHERE ProductName LIKE 'Ch%'
  ```
  * _ = single unknown character, each underscore represents a character
  ```SQL
  SELECT ProductName FROM Products WHERE ProductName LIKE 'Cha__'
  SELECT ProductName FROM Products WHERE ProductName LIKE '__ai'
  ```
  * [CHARLIST] - Sets and ranges of characters to match.
  ```SQL
  -- Returns all records which start with B or S.
  SELECT * From Products where ProductName LIKE '[BS]%'
  ```
  * ^[CHARLIST] - Opposite of CHARLIST, does not match range of characters.
  ```sql
  -- Returns all records which DO NOT start with A, B or C.
  SELECT * From Products where ProductName LIKE '^[ABC]%'
  ```
8. IN – Looks for collections. Can be used if you have multiple queries and do not want to keep using OR.
```SQL
SELECT COUNT(*) FROM table_name WHERE column_name IN ('value1','value2','value3')

-- Example
SELECT COUNT(*) FROM Orders WHERE ShipCity IN ('Lyon','Reims','Graz')
```
9. TOP - Identifies specified number or percent of values from the top of the table
```SQL
SELECT TOP num column_name FROM table_name
--Examples
SELECT TOP 5 * FROM Employees
SELECT TOP 75 PERCENT * FROM Employees
```
10. ORDER BY - Sort a table based on a column. ASCending or DESCending.
```SQL
SELECT column_name, column_name, FROM table_name ORDER BY column_you_want_to_order DESC/ASC

--Example
SELECT UnitPrice, Quantity, Discount, UnitPrice*Quantity AS 'Gross Total'
FROM [Order Details] ORDER BY 'Gross Total' DESC
```
11. Aggregate Functions - Performs a calculation on a set of values and returns a single value
```SQL
SELECT
    SUM(column_name) AS 'new_name',
    AVG(column_name) AS 'new_name',
    MIN(column_name) AS 'new_name',
    MAX(column_name) AS 'new_name'
FROM table_name;

--Example
SELECT
    SUM(UnitsOnOrder) AS 'Total on Order',
    AVG(UnitsOnOrder) AS 'Avg on order',
    MIN(UnitsOnOrder) AS 'Min on order',
    MAX(UnitsOnOrder) AS 'MAX on order'
FROM Products;
```
12. GROUP BY - Groups according to a specified category
```sql
SELECT <grouping_column>,
    SUM(<column>) AS <new_name>,
    AVG(<column>) AS <new_name>
FROM table_name
GROUP BY <grouping_column>

--Example – Groups according to the SupplierID category and
--outputs results of the aggregate functions SUM, AVG and MAX.
SELECT SupplierID,
    SUM(UnitsOnOrder) AS 'Total on Order',
    AVG(UnitsOnOrder) AS 'Avg on order',
    MAX(UnitsOnOrder) AS 'Max on order'
FROM Products
GROUP BY SupplierID
```
13. HAVING - Used instead of WHERE when filtering on subgroups. Essentially when we try to call an alias using WHERE, it will throw an error as it has not yet been created. HAVING allows us to call this alias.
```SQL
SELECT <grouping_column>,
    SUM(<column>) AS <new_name>,
    AVG(<column>) AS <new_name>
FROM table_name
GROUP BY <grouping_column>
HAVING AVG(<column>) > value

--Example – Groups by Supplier ID and only shows order which have more than 5 units on order.
SELECT SupplierID,
    SUM(UnitsOnOrder) AS 'Total on Order',
    AVG(UnitsOnOrder) AS 'Avg on order'
FROM Products
GROUP BY SupplierID
HAVING AVG(UnitsOnOrder)>5
```
14. JOIN - combine matched rows from two or more tables. Various types of joins, these include:
  * (INNER) JOIN = Select records that have matching values in both tables.
  * FULL (OUTER) JOIN = Selects all records that match either left or right table records
  * LEFT (OUTER) JOIN = Select records from the first (left) table with matching right table records  
  * RIGHT (OUTER) JOIN = Select records from the second (right) table with matching left table records.
```SQL
SELECT *
FROM table_a
JOIN table_b
ON table_a.matchingid = table_b.matchingid

--Example 1
SELECT Orders.OrderID, Customers.CompanyName, Customers.ContactName, Customers.Country, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID
WHERE Customers.Country='Brazil' or Orders.ShipCountry='Brazil'

--Example 2- Using Aliases
SELECT o.OrderID, c.CustomerID, c.CompanyName, c.ContactName
FROM Orders o
INNER JOIN Customers c
ON o.CustomerID=c.CustomerID
WHERE c.Country='Brazil' or o.ShipCountry='Brazil'
ORDER BY c.CompanyName

```
