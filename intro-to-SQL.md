#### WHAT IS A DATABASE ?
* Any collection of related information

     * Phone Book
     * To Do List
     * Our 5 best friends
     * Facebook's User base

* Databases can be stored in different ways
     * On Paper
     * In our mind
     * On a computer


#### DATABASE MANAGEMENT SYSTEM(DBMS)
--------------------------------------------------------------
 A special software program that helps users create & maintain a database
* Makes it easy to manage large amounts of information
* Handles security
* Backups
* Importing/exporting data
* Concurrency
* Interacts with software applications using programming 
languages

#### CRUD OPERATIONS
-------------------------------------------------------------
CRUD stands for "Create Read[Retrieve] Update Delete"

#### TWO TYPES OF Databases
-------------------------------------------------------------

RELATIONAL (SQL)       | NON-RELATIONAL (noSQL/ not just SQL)
-----------------------|------------------------------------
Organize data into one or more tables |   Organize data into anything that is not traditional table
Each table has columns & rows   |     Key-value pairs, Documents(JSON, XML, etc), Graphs,  Flexible tables
 A unique key identifies each row |


#### EXAMPLE OF RELATIONAL DATABASE
-------------------------------------------------------------

__Student Table__
 
ID  | Name |    Major
---- | ------ | --------
1   | Jack   | Biology
2   | Kate   | Sociology
3   | Claire | English
4   | John   | Chemistry


__Users Table__

 Username | Password | Email
----------|----------|----- 
  jsmith   |  jsss   |  ...
  katewins |  sagj   |  ...
  ...      |  ...    |  ... 
  ...      |  ...    |  ... 


#### RELATIONAL DATABASES(SQL)
------------------------------------------------------------

**RDBMS(Relational Database Management System)**
* Helps users create and manage Relational database 
* EXAMPLES: mySQL, Oracle, postgreSQL, mariaDB, etc 


**SQL(Structured Query Language)**
* Standardized language for interacting with RDBMS
* Used to perform CRUD operations as well as other
  administrative tasks(User Management, Security,
  Backup, etc) 

* Used to define tables & structures
* SQL code used on one RDBMS is not always portable 
   without modification


#### EXAMPLES OF NON-RELATIONAL DATABASE 
-------------------------------------------------------------

**Example - 1**
```json
[
    {
        fName: 'Santosh',
        lName: 'Swansi',
        roll: 732
    },
    {
        fName: 'Subhash',
        lName: 'Swansi',
        roll: 9893
    },
    {
        fName: 'Sangeeta',
        lName: 'Swansi',
        roll: 3178
    }
]
```

**Example - 2**

key    |    value
-------|------------
fName  |    'Santosh'
lName  |    'Swansi',
roll   |      732



#### NON-RELATIONAL DATABASES(noSQL/ not just SQL)
-------------------------------------------------------------

**NRDBMS (Non Relational Database Management System)**

* Helps user create non-relational databases 
* EXAMPLES: mongoDB, dynamoDB, apache cassandra, firebase, etc


**They are Implementation Specific**

* Most NRDBMS will implement their own language for    performing CRUD and administrative operations on the 
   database 


#### Database Queries
---------------------------------------------------------------
 Queries are request made to the DBMS for specific information




#### DBMS KEYS
----------------------------------------------------------------
* KEYS in DBMS is an attribute or set of attributes which helps us to identify a row(tuple) in relation(table) 
* They allows us to find the relation between two tables 
* Keys help us to identify a row with one or more columns of the table   



#### TYPES OF KEYS IN DBMS 
----------------------------------------------------------------   


##### 1. SUPER KEY
----------------------------------------------------------------
* It is a attribute or group of attributes which uniquely identifies the record
* It is the superset of all keys
* It may contain additional attribute that are not needed for 
unique identification 


**Example** 

 SID |     REG_ID   |  NAME  |  BRANCH |   EMAIL 
-----|--------------|--------|---------|-------------
 1   |   CS-2019-32 | John   |   CS    |  john@gmail.com 
 2   |   CS-2018-12 | Kate   |   CS    |  kate@gmail.com 
 3   |   IT-2019-09 | Lil    |   IT    |  lil@gmail.com 
 4   |   PH-2019-32 | Kokila |   PH    |  kokila@gmai.com 

   
   **Super keys**:  SID, REG_ID, EMAIL, (SID + REG_ID),
                   (REG_ID + EMAIL) + (EMAIL + SID) 
                   {Can have more combinations}


##### 2. CANDIDATE KEY
--------------------------------------------------------------
* It is the minimal subset of super key
* In above table any of the following can be candidate key
   * SID
   * REG_ID
   * EMAIL

**NOTES:** 
* Since they are **minimal subset** of super key that 
      can uniquely identify a record(or row)

* If any **proper subset** of a super key is a super key then that key cannot be a candidate key

##### 3. PRIMARY KEY
----------------------------------------------------------------
* It is the candidate key chosen to uniquely identify each row of data in a table 
* Database administrator have the option to chose any one of the "candidate key" as the "primary key"  


**Rules for defining Primary Key**
* Two rows cannot have the same primary key value 
* It cannot be NULL
* The value of primary key can never be updated if any foreign key refers to that primary key 


##### 4. ALTERNATE KEY 
--------------------------------------------------------------
* All the candidate keys which are not chosen as the "primary key" are known as alternate keys



##### 5. FOREIGN KEY 
----------------------------------------------------------------
* It is a column that creates a relationship between two tables
* The purpose of Foreign keys is to maintain data integrity and allow navigation between two different instances of
an entity 
* It acts as a cross-reference between two tables as it
references the primary key of another table


**Example**

DeptCode| DeptName
--------|-----------
 001	  |  Science
 002	  |  English
 005	  |  Computer


Teacher_ID	|  DeptCode|	Fname| Lname
-----------|-----------|--------|-------
B002	      |    002	  |  David |Warner
B017	      |    002	  |  Sara  |Joseph
B009	      |    001	  |  Mike  |Brunton

_Here DeptCode is the "foreign key" & it stores "Primary key" of the first table to creates a relationship between both tables_ 


##### 6. COMPOSITE KEY 
--------------------------------------------------------------
* Any key with more than one attribute is called "composite key"  
* In the topmost table (SID, REG_ID), (REG_ID, EMAIL), (EMAIL, SID), (SID, REG_ID, EMAIL), etc are composite keys  

##### 7. COMPOUND KEY 
--------------------------------------------------------------
* If a "compound key" has at-least one attribute which is a
"foreign key", then it is called "compound key"  
* In previous table, if we have a "composite key"
(Teacher_ID, DeptCode) then it will be known as "compound key" because "DeptCode" is a "foreign key"        


##### 8. SURROGATE KEY 
-----------------------------------------------------------------
* If a table(relation) has no attribute which can be used to uniquely identify the data stored in it, then we create an attribute for this purpose known as "surrogate key" 
* It adds no meaning to the data but serves the sole purpose of identifying rows uniquely in a table  


> **The following syntax has been written in context of mySQL RDBMS**


##### CREATE A DATABASE 

```sql
CREATE DATABASE database_name;
```


##### DELETE A DATABASE
```sql
DROP DATABASE database_name; 
```

##### SHOW DATABASES
```sql
SHOW DATABASES;
```

##### COMMON DATA TYPES 


DATA TYPES         |      DESCRIPTION
--------| ------------
INT             |  Whole numbers 
DECIMAL(M, N)   |  Decimal Numbers - Exact value (M digits, N digits after decimal)
VARCHAR(1)      |  String of length 1
BLOB            |  Binary Large Object, stores large data(for Images & files) 
DATE            |  'YYYY-MM-DD'
TIMESTAMP       |  'YYYY-MM-DD HH:MM:SS' (Used for recording)


**NOTES:** 
* Use back quotes(``) to use reserved words as column name,record's value, etc
* Use (--, \\*  */) for comments




### C.R.U.D OPERATIONS 
---------------------------------------------------------------


#### I) CREATE OPERATION
------------------------------------------------------------------



##### 1.  CREATE TABLE 
   --------------------------------------------------------
###### SYNTAX 

```sql
 CREATE TABLE table_name(
                  col_1 data_type constraints,
                  col_2 data_type ...
                  ...
               );
```

```sql
CREATE TABLE table_name(
                  col_1 data_type,
                  col_2 data_type,
                  constraints(col_name),
                  ...
               ); 
```  


##### 2. ADD COLUMN TO A TABLE 
   --------------------------------------------------------
###### SYNTAX

```sql
   ALTER TABLE table_name
   ADD COLUMN column_name; 
```

##### 3. CREATE A RECORD 
   -------------------------------------------------------------
###### SYNTAX: 
```sql
INSERT INTO table_name(col_1_val, col_2_val, ...);
```


##### 4. CREATE A RECORD CONTAINING SPECIFIED ATTRIBUTES
--------------------------------------------------------------------- 

```sql
INSERT INTO table_name(col_name_1, ...) 
                  VALUES(col_name_1_val, ...);
```




#### II) READ(RETRIEVE) OPERATION 
---------------------------------------------------------------


##### 1. SHOW TABLE SCHEME
--------------------------------------------------------
###### SYNTAX

```sql
DESCRIBE TABLE table_name;
```

```sql
DESC TABLE table_name;
```
   
##### 2. SHOW TABLE CONTENTS 
---------------------------------------------------------

###### SYNTAX

```sql
SELECT col_1, col2, ...
FROM table_name;
```

###### Show all columns
```sql
SELECT *
FROM table_name;
```

###### Show distinct entries of a column
```sql
SELECT DISTINCT col_name
FROM table_name;
```


###### Show count of distinct entries of a column
```sql
SELECT COUNT(DISTINCT col_name)
FROM table_name;
```

##### FILTERING RECORDS
--------------------------------------------
* Use WHERE clause to filter records

###### **SYNTAX**
```sql  
      SELECT col1, col2, ...
      FROM table_name
      WHERE condition(s);
```

###### OPERATORS in the WHERE clause
-----------------------------------------------------

 Operator    |   Description
 ------------ | ----------------
=            |   Equal
\>            |   Greater than
<            |   Less than
\>=           |   Greater than equal
<=           |   Less than or equal
<>           |   Not equal  (In some versions !=)
BETWEEN      |   Between a certain range
LIKE         |   Search for a pattern
IN           |   To specify multiple possible values for a column


###### EXAMPLES OF USING WHERE & OPERATORS 
--------------------------------------------------
Students between 20 & 23
```sql
SELECT * FROM students 
WHERE Age BETWEEN 20 AND 23;
```

Student names starts with S

```sql
SELECT * FROM students 
WHERE Name LIKE 'S%';  
```

Name starts with 's' & ends with 'a' & have two characters in between  

```sql
SELECT * FROM students
WHERE Name LIKE 's__a';
```

Age = 19 or 21 or 23
```sql
SELECT * FROM students 
WHERE Age IN (19, 21, 23); 
```



##### AND, OR, NOT 
WHERE clause can be combined with AND, OR, NOT

###### EXAMPLES
```sql
SELECT * FROM Customers
WHERE NOT Country='Germany' 
AND NOT Country='USA'; 
```

```sql
SELECT * FROM Customers
WHERE Country='Germany'
AND 
(City='Berlin' OR City='München');  
```

##### IS NULL, IS NOT NULL operators 
-----------------------------------------------
```sql
SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NULL;  
```
```sql
SELECT name
FROM Customers
WHERE name IS NOT NULL;
```


##### **ORDERING RECORDS** 
---------------------------------------------------------    
###### EXAMPLES

Default ordering (Ascending)
```sql     
SELECT * FROM students 
ORDER BY name;    -
```

Descending ordering 
```sql
SELECT * FROM students
ORDER BY name DESC;  
```  


##### LIMIT THE TOTAL NUMBER OF RECORDS RETRIEVED 
--------------------------------------------   

```sql
SELECT * FROM students 
WHERE age IN (19, 23, 24)
LIMIT 5;   
```

##### FUNCTIONS 
--------------------------------------------------------
###### 1. MIN()

```sql  
SELECT MIN(price) AS minPrice 
FROM products; 
```

###### 2. MAX()
```sql 
SELECT MAX(price) AS maxPrice 
FROM products;
```

###### 3. COUNT()
```sql
SELECT COUNT(DISTINCT name)
FROM products;
```

###### 4. AVG()
```sql
SELECT AVG(price) AS avgPrice
FROM products;
```

###### 5. SUM()
```sql
SELECT SUM(price) AS sumPrice
FROM products;
```


##### PATTERN HUNTING   
-------------------------------------------------------------
* The LIKE operator is used in a WHERE clause to search
  for a specified pattern in a column

* Wildcards often used with LIKE:-
  
s|h
-------|-------------
%  | Represents _zero, one, or multiple characters_
_  | Represents a _single character_
[]	| Represents _any single character within the brackets_ **Example:**  h[oa]t finds hot and hat, but not hit
^  | Represents any character not in the brackets **Example:** h[^oa]t finds hit, but not hot and hat
-	|  Represents a range of characters 	 **Example:** c[a-b]t finds cat and cbt

###### EXAMPLES
 
```sql 
SELECT * FROM products
WHERE name LIKE '%or%';  
```
```sql
SELECT * FROM products
WHERE name LIKE '_r%';   
```
```sql
SELECT * FROM products
WHERE name LIKE '[^a-z]r%';
``` 

##### ALIAS 
------------------------------------------------------------
* SQL aliases are used to give a table, or a column in a table, a temporary name
* Aliases are often used to make column names more readable
* An alias only exists for the duration of the query


###### SYNTAX
--------------------------------------
```sql
SELECT col_name AS alias_name
FROM table_name;
```


```sql
SELECT col_name AS alias_name
FROM table_name;
```


##### JOINS 
-------------------------------------------------------------
JOIN clause is used to join rows of different tables

###### **DIFFERENT TYPES OF JOIN** 
----------------------------------------------------------
* (INNER) JOIN 
   * Returns records that have matching values in both tables 

* LEFT (OUTER) JOIN 
   * Returns all records from the left table, & matched records from the right table 

* RIGHT (OUTER) JOIN
   * Returns all records from the right table, & matched records from the left table 

* FULL (OUTER) JOIN 
  * Returns all records when there is a match in either left or right table 


##### INNER JOIN 
-------------------------------------------------------
###### SYNTAX:
```sql
SELECT col_1, col2, ... 
FROM table_1
INNER JOIN table_2 
ON table_1.col_name = table_2.col_name
```

###### EXAMPLE:
```sql
SELECT * 
FROM students
INNER JOIN products
ON students.student_id = products.student_id;
```

##### LEFT JOIN 
-------------------------------------------------------

###### SYNTAX:
```sql
SELECT col_1, col2, ... 
FROM table_1
LEFT JOIN table_2 
ON table_1.col_name = table_2.col_name
```
###### EXAMPLE:
```sql
   SELECT * 
   FROM students
   LEFT JOIN products
   ON students.student_id = products.student_id;
```

##### RIGHT JOIN 
-------------------------------------------------------

###### SYNTAX:

```sql
      SELECT col_1, col2, ... 
      FROM table_1
      RIGHT JOIN table_2 
      ON table_1.col_name = table_2.col_name
```
###### EXAMPLE:
```sql
      SELECT * 
      FROM students
      RIGHT JOIN products
      ON students.student_id = products.student_id;
```

##### FULL OUTER JOIN 
-------------------------------------------------------

###### SYNTAX:
```sql
      SELECT col_1, col2, ... 
      FROM table_1
      FULL OUTER JOIN table_2 
      ON table_1.col_name = table_2.col_name
      WHERE condition;
```
###### EXAMPLE:
```sql
      SELECT * 
      FROM students
      FULL OUTER JOIN products
      ON students.student_id = products.student_id
      ORDER BY students.name ASC;    
```

##### SELF JOIN 
-----------------------------------------------------------                    
* A self JOIN is a regular join, but the table is joined  by itself 

###### SYNTAX
```sql
   SELECT column_name(s)
   FROM table1 alias1, table1 alias2
   WHERE condition;
```
###### EXAMPLE:
```sql
      SELECT *
      FROM students A, students B 
      WHERE A.student_id <> B.student_id
      AND A.major = B.major
      ORDER BY A.name;
```

#### UNION 
-------------------------------------------------------------            
* The UNION operator is used to combine the result-set of two or more SELECT statements 

   * Each SELECT statement should have equal number of columns 
   * The columns must also have similar data type 
   * The columns in SELECT statements must also be in same order 


##### UNION 
-----------------------------------------
* It selects DISTINCT values  

###### SYNTAX:
```sql
      SELECT column_name(s) FROM table_1
      UNION
      SELECT column_name(s) FROM table_2;
```

###### EXAMPLE:
```sql 
      SELECT city FROM customers 
      UNION
      SELECT city FROM students
      ORDER BY city;
```


##### UNION ALL
-----------------------------------------
* It also selects duplicate values

###### SYNTAX:
```sql
      SELECT column_name(s) FROM table_1
      UNION ALL
      SELECT column_name(s) FROM table_2;
```
###### EXAMPLE:
```sql
      SELECT city FROM customers 
      WHERE country="India"
      UNION ALL
      SELECT city FROM students
      WHERE country="India"
      ORDER BY city;    
```   
            

**NOTES:** 
* The column names in the result-set are usually equal to the column names in the first SELECT statement
in the UNION

* Use alias name for different column name 

   
##### GROUP BY STATEMENT 
-------------------------------------------------------------
* It groups rows with same values into summary rows, like "find the number of customers in each country"
* It is often used with aggregate functions (COUNT, SUM, AVG, MIN, MAX) to group result-set by one or more columns   

###### SYNTAX:
```sql
      SELECT col_name(s)
      FROM table_name 
      WHERE condition
      GROUP BY col_name(s) 
      ORDER by col_name(s);     
```
###### EXAMPLE:
```sql 
      SELECT country COUNT(customerID)
      FROM customers 
      GROUP BY country
      ORDER BY country;
```

> GROUP BY with JOIN
```sql
      SELECT Shippers.ShipperName, 
      COUNT(Orders.OrderID) AS NumberOfOrders
      FROM Orders
      LEFT JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID
      GROUP BY ShipperName;  
```


##### HAVING CLAUSE 
------------------------------------------------------------             
* HAVING clause was added because WHERE keyword could not be used with aggregate functions 

###### SYNTAX: 
```sql
      SELECT col_name(s)
      FROM table_name 
      GROUP BY col_name(s)
      HAVING condition 
      ORDER BY col_name(s);
``` 

###### EXAMPLE:
```sql 
      SELECT Employees.LastName, 
      COUNT(Orders.OrderID) AS NumberOfOrders
      FROM Orders
      INNER JOIN Employees 
      ON
      Orders.EmployeeID = Employees.EmployeeID
      WHERE LastName = 'Davolio' 
      OR
      LastName = 'Fuller'
      GROUP BY LastName
      HAVING COUNT(Orders.OrderID) > 25; 
```            


##### EXISTS OPERATOR 
------------------------------------------------------------
* It is used to test for the existence of records in a sub-query 

###### SYNTAX
```sql 
      SELECT col_name(s)
      FROM table_name 
      WHERE EXISTS 
      (SELECT col_name(s) 
      FROM table_name
      WHERE condition);
```

###### EXAMPLE
> Returns TRUE and list the suppliers with a product price < 20

```sql
      SELECT SupplierName
      FROM Suppliers
      WHERE EXISTS 
      (SELECT ProductName FROM Products 
      WHERE Products.SupplierID = Suppliers.supplierID
      AND 
      Price < 20);   
```

##### ANY & ALL OPERATORS
--------------------------------------------------------------         
* They are used with WHERE & HAVING clauses 
* ANY returns true, if any of the records of sub-query satisfies the condition 
* ALL returns true, if all of the records of sub-query satisfies the condition 


###### **ANY CLAUSE** 
----------------------------
###### SYNTAX
```sql
         SELECT col_name(s)
         FROM table_name
         WHERE col_name operator ANY 
         (SELECT col_name(s) 
         FROM table_name
         WHERE condition);
```

> operator can be [=, <>, !=, >, >=, <, or <=)]      

###### EXAMPLE:
> Returns TRUE and lists the product names if it finds ANY records in the orders table that quantity > 10 

```sql
         SELECT productName 
         FROM products 
         WHERE productID = ANY 
         (SELECT productID FROM orders 
         WHERE quantity > 10);
```

###### **ALL CLAUSE** 
----------------------------
###### SYNTAX
```sql
         SELECT col_name(s)
         FROM table_name
         WHERE col_name operator ALL 
         (SELECT col_name(s) 
         FROM table_name
         WHERE condition);
```

###### EXAMPLE
* Returns TRUE and lists the product names if it finds ALL records in the orders table that quantity > 99

```sql
         SELECT productName 
         FROM products 
         WHERE productID = ALL 
         (SELECT productID FROM orders 
         WHERE quantity > 99);
```


##### CASE STATEMENT 
-----------------------------------------------------------
* It goes through conditions & returns a value if any of the condition are met otherwise it will return value in ELSE clause

###### SYNTAX: 
```sql
         CASE 
            WHEN condition_1 THEN result_1            
            WHEN condition_2 THEN result_2            
            WHEN condition_3 THEN result_3
            ELSE result
         END;
```

###### EXAMPLES 
------------------------------------------------------
Selects orderID, quantity & prints QuantityText using CASE statement
          
```sql
         SELECT OrderID, Quantity,
         CASE
            WHEN Quantity > 30 THEN 'The quantity is greater than 30'
            WHEN Quantity = 30 THEN 'The quantity is 30'
            ELSE 'The quantity is under 30'
         END AS QuantityText
         FROM OrderDetails;
```


Order the customers by city, if city = NULL, order by country
```sql
         SELECT CustomerName, City, Country
         ORDER BY
         (CASE 
            WHEN City IS NULL THEN Country 
            ELSE City
         END);
```


##### NULL FUNCTIONS 
-----------------------------------------------------------

###### 'Products' table 

   P_Id |	ProductName |	UnitPrice | UnitsInStock |UnitsOnOrder
   ---|---|---|---|---
   1	  |  Jarlsberg	|  10.45	 |   16	    |  15
   2	  |  Mascarpone|   32.56 |   23      |   	 
   3	  |  Gorgonzola|   15.67 |   	9 	    |  20

> Suppose UnitsOnOrder is optional & can contain NULL values


###### PROBLEM
```sql
      SELECT ProductName, UnitsPrice*(UnitsInStock + UnitsOnOrder)
      FROM Products;
```

> Here if any value of UnitsOnOrder will be NULL, result will be NULL 


###### SOLUTION

IFNULL() lets us return an alternative value if an expression is NULL

```sql   
         SELECT ProductName, UnitsPrice*(UnitsInStock + IFNULL(UnitsOnOrder,0))
         FROM Products;
```

Using COALESCE()
```sql
         SELECT ProductName, UnitsPrice*(UnitsInStock+ COALESCE(UnitsOnOrder,0))
         FROM Products; 
```

#### III) UPDATE OPERATION
---------------------------------------------------------------

##### 1. UPDATE ALL RECORDS 

###### SYNTAX
```sql
      UPDATE table_name
      SET col_1_name=val_1, col_2_name=val_2, ...;
```

###### EXAMPLE: 
```sql
      UPDATE students 
      SET major='undecided';
```

##### 2. UPDATE PARTICULAR RECORDS 
--------------------------------------------
###### SYNTAX:  
```sql 
      UPDATE table_name 
      SET col_1_name=val_1, col_2_name=val_2, ...
      WHERE condition;
```
###### EXAMPLE
```sql
      UPDATE students 
      SET major="undecided"
      WHERE student_id=1;   
```       

   
##### 3. SELECT INTO 
--------------------------------------------------------------
* It copies data from one table into a new table 

###### COPY ALL COLUMNS INTO A NEW TABLE 
--------------------------------------------------
###### SYNTAX
```sql 
         SELECT * 
         INTO new_table (IN external_database)
         FROM old_table 
         WHERE condition;
```

###### COPY PARTICULAR COLUMNS INTO A NEW TABLE 
--------------------------------------------------
###### SYNTAX
```sql
         SELECT col_name(s)
         INTO new_table (IN external_database)
         FROM old_table 
         WHERE condition;
```

###### EXAMPLES 
--------------------------------------------------            
Create a backup copy of customers 
```sql
         SELECT * 
         INTO customersBackup2020
         FROM customers; 
```

Copy a table into a new table in another database 
```sql
      SELECT * 
      INTO customersBackup2020IN 'Backup.mdb'
      FROM customers;
```

Copy a few columns into a new table 
```sql
      SELECT CustomerName, ContactName 
      INTO customersBackup2020
      FROM customers;
```

Copies records of 'Indian' into a new table 
```sql
         SELECT * 
         INTO IndianCustomersBackup2020
         FROM customers 
         WHERE country='India';
```

Copies records from more than one table into a new table 
```sql
         SELECT customers.name, products.name 
         INTO customersProductsBackup2020
         FROM customers 
         LEFT JOIN customers ON 
         customers.customersID = products.customersID;
```


**NOTES:**
* SELECT INTO can also be used create an empty 
table with schema of another 
* Just add a WHERE clause that causes query to return no data 

```sql
         SELECT * INTO new_table
         FROM old_table
         WHERE 1 = 0;
```


##### 4 INSERT INTO SELECT 
----------------------------------------------------------
* It is used to copy records from one table and inserts into another existing table 
* Data types in source & target tables should match 
* Existing records in the target table is unaffected 

###### SYNTAX  (All Columns):
```sql
      INSERT INTO table_2 
      SELECT * FROM table_1
      WHERE condition;
```    

###### SYNTAX (Specified Columns):
```sql
      INSERT INTO table_2
      SELECT col_name(s)
      FROM table_1
      WHERE condition;
```

###### EXAMPLES 
  
It copies "Suppliers" into "Customers" (the columns that are not filled with data, will contain NULL)
```sql
         INSERT INTO Customers 
         (CustomerName, City, Country)
         SELECT(CustomerName, City, Country) 
         FROM Suppliers;
```

It copies only the Indian suppliers into "Customers"     

```sql
         INSERT INTO Customers 
         (CustomerName, City, Country)
         SELECT (CustomerName, City, Country) 
         FROM Suppliers
         WHERE country='India';
```

##### ALTER TABLE COLUMN NAME 
-----------------------------------------------------------
      
###### SYNTAX
```sql
      ALTER TABLE table_name 
      ALTER COLUMN old_col_name new_col_name;
```      

###### EXAMPLE
```sql
      ALTER TABLE Persons
      ALTER COLUMN DateOfBirth year;
```
  



#### IV) DELETE OPERATION 
---------------------------------------------------------------

##### 1. REMOVE TABLE 
--------------------------------------------------------
###### SYNTAX: 
```sql
   DROP TABLE table_name;
```


##### 2. REMOVE A COLUMN FROM A TABLE 
--------------------------------------------------------
###### SYNTAX
```sql 
      ALTER TABLE table_name
      DROP COLUMN column_name;
```

##### 3. REMOVE CONTENT FROM TABLE
---------------------------------------------------------
      
###### **A. REMOVE PARTICULAR RECORD** 
------------------------         
###### SYNTAX:  
```sql
         DELETE FROM table_name
         WHERE condition;
```

###### EXAMPLE
```sql 
         DELETE FROM students
         WHERE name="Sangeeta";
```

###### **B. REMOVE ALL RECORDS WITHOUT REMOVING TABLE** 
-------------------------------------------------
###### SYNTAX
```sql 
      DELETE FROM table_name;
```
###### EXAMPLE
```sql 
      DELETE FROM students;
```

##### USING KEYWORD
--------------------------------------------------------------
* USING in MySQL is just a short form for a standard ON clause, and only works when the column name is identical in both tables


#### MISCELLANEOUS OPERATIONS
--------------------------------------------------------------
  
##### 1. DELIMITER 
-----------------------------------------------------------
* SQL server treats semicolon as the end of the SQL statement and executes it but Stored Procedure contains multiple semi-colons in a single SQL statement which is possible due to use of DELIMITER

###### SYNTAX
```sql
     DELIMITER delimiter_characte
```

* delimiter_character may contain single character  or multiple characters (//, $$)
* Avoid using \ as delimiter_character since it is a back escape character in SQL 
* We can end the DELIMITER using the same delimiter_character, where we want to end the 
SQL statement


##### 2. STORED PROCEDURE 
-----------------------------------------------------------
* If we want to save our frequently used SQL query on
SQL server then we can use Stored Procedure 

###### SYNTAX FOR DEFINING
```sql
            DELIMITER $$
            CREATE PROCEDURE nameOfProcedure(parameterList)
            BEGIN
               SELECT statement 
            END$$
            DELIMITER;   
```

###### SYNTAX FOR CALLING
```sql
         CALL nameOfProcedure(parameterList);
```
###### EXAMPLE    
```sql
         DELIMITER $$
         CREATE PROCEDURE GetCustomers()
         BEGIN
         	SELECT 
         		customerName, 
         		city, 
         		state, 
         		postalCode, 
         		country
         	FROM
         		customers
         	ORDER BY customerName;
         END$$
         DELIMITER ;
```
###### ADVANTAGES 
1. Reduce Network Traffic 
     * It is because applications have to send only the name & parameters of stored procedures

2. To Centralize business logic in the database 
      * Because it allows code reusablity for multiple applications

3. Make database more secure
      * The database administrator can grant   appropriate privileges to applications that only access specific stored procedures without giving any privileges on the underlying tables

###### DISADVANTAGES 

* Use of many Stored Procedures will increase the CPU usage 
* Troubleshooting is difficult in MySQL
* It requires special maintenances 

##### 3. SQL VIEW 
-----------------------------------------------------------
* A view represents a virtual table
* We can join multiple tables in a view and use the view to present the data as if the data were coming from a single table

###### SYNTAX
```sql
         CREATE VIEW nameOfView
         AS 
         SELECT statement;   
```

###### EXAMPLE
```sql
      CREATE VIEW customerPayments
      AS 
      SELECT 
          customerName, 
          checkNumber, 
          paymentDate, 
          amount
      FROM
          customers
      INNER JOIN
          payments USING (customerNumber); 
```

* Once we create the view, MySQL creates & stores the view in the database 
* Now we can refer view as the table in our SQL statements 

###### **DROP A VIEW**
        
###### SYNTAX (for single view)
```sql  
      DROP VIEW [IF EXISTS] view_name;
```

###### SYNTAX (for multiple views)
```sql
      DROP VIEW [IF EXISTS] view_name1, view_name2, ...;
```

> 'IF EXISTS' conditionally removes a view when it exists


###### SHOW ALL VIEWS 

List views of the same database 
```sql
      SHOW FULL TABLES 
      WHERE table_type = 'VIEW';
```
> SHOW FULL TABLES return all tables & views we need to use WHERE clause 


List views of other database 

```sql
      SHOW FULL TABLES
      [{FROM | IN } database_name]
      WHERE table_type = 'VIEW'; 
```

List views based on pattern 
```sql
      SHOW FULL TABLES
      [{FROM | IN} database_name]
      LIKE pattern;
```

**NOTE:**  If we have no privileges for a view, it will not show up the output of the 'SHOW TABLES' statement


###### USING INFORMATION_SCHEMA DATABASE 
* It provides access to MySQL database metadata like 
   * Names of Databases
   * Tables 
   * Data types of columns 
   *  privileges

* It is sometimes referred as a "Database Dictionary" or "System Catalog"


###### To show views of a database :  
```sql
         SELECT * FROM
         INFORMATION_SCHEMA.tables;
```

###### Columns returned by it are :-
1. table_schema 
   * Stores schema(or database) of the 
   view(or table)

2. table_name 
     * Stores name of the view(or table)

3. table_type 
      * Stores type of tables :-
         1. BASE TABLE (for table)
         2. VIEW (for view)
         3. SYSTEM VIEW (for an INFORMATION_SCHEMA table)


###### Finds all views whose names start with customer :
```sql      
         SELECT table_name view_name
         FROM information_schema.tables 
         WHERE table_type = 'VIEW' AND
         table_schema = 'classicmodels' AND 
         table_name   LIKE 'customer%';   
```

###### RENAME A VIEW
```sql
         RENAME TABLE original_view_name
         TO new_table_name;
```

###### ADVANTAGES OF  mySQL views           
* Simplify complex queries 
* Add extra security layers 



#### SQL OPERATORS 
--------------------------------------------------------------

##### 1. Arithmetic Operators
-----------------------------------------------------------

 Operator   |	Description	      |   EXAMPLE
------------|--------------------|-------------------
   +	      |   Add	            |   SELECT 20+30;  
   -	      |   Subtract	      |   SELECT 20-30;
   *	      |   Multiply	      |   SELECT 20*30;
   /	      |   Divide	         |   SELECT 20/30;
   %	      |   Modulo	         |   SELECT 20%30;


##### 2. Bitwise Operators
-----------------------------------------------------------
Operator | Description
---------|--------------------
&        |   Bitwise AND
\|        |   Bitwise OR
^        |   Bitwise exclusive OR


##### 3. Comparison Operators 
-----------------------------------------------------------

 Operator|   Description	
-----------|-----------------------------
   =	     |   Equal to	
   \>	     |   Greater than	
   <	     |   Less than	
   \>=	  |   Greater than or equal to	
   <=	     |   Less than or equal to	
   <>	     |   Not equal to


##### 4. Comparison Operators 
-----------------------------------------------------------

 Operator |     Description
----------|-------------------------------
   +=	    |     Add equals
   -=	    |     Subtract equals
   *=	    |     Multiply equals
   /=	    |     Divide equals
   %=	    |     Modulo equals
   &=	    |     Bitwise AND equals
   ^-=    |   	Bitwise exclusive OR equals
   |*=    |   	Bitwise OR equals



###### 5. Logical Operators 
-----------------------------------------------------------                 
      
 Operator	|   Description	
-------------|----------------------
ALL	   |    TRUE if all of the sub-query values meet the condition	
AND	   |    TRUE if all the conditions separated by AND is TRUE	
ANY	   |    TRUE if any of the sub-query values meet the condition	
BETWEEN	|    TRUE if the operand is within the range of comparisons	
EXISTS	|    TRUE if the sub-query returns one or more records	
IN	    |   TRUE if the operand is equal to one of a list of expressions
LIKE	  |     TRUE if the operand matches a pattern	
NOT	  |     Displays a record if the condition(s) is NOT TRUE
OR	     |  TRUE if any of the conditions separated by OR is TRUE	
SOME	  |  TRUE if any of the sub-query values meet  the condition
         




##### SOME COMMON CONSTRAINTS 
-------------------------------------------------------------

###### 1. FOREIGN KEY
--------------------------------------------------------------
* A Foreign key is used to link two tables
* A Foreign key is a field(or collection of fields) in one table that refers to the PRIMARY KEY in another table 
* Table containing the foreign key is called 'child' table, & the table containing the candidate key is  called 'referenced' or 'parent' table 


###### FOREIGN KEY on CREATE TABLE 
     
**EXAMPLE**

> Basic One 
```sql
      CREATE TABLE Students(
         RollNo INT NOT NULL PRIMARY KEY,
         Name VARCHAR(20) NOT NULL,
         ExamRollNo VARCHAR(20) NOT NULL,
         FOREIGN KEY (ExamRollNo) 
         REFERENCES Exams(ExamRollNo)
      ); 
```

> Named Foreign key   
```sql
      CREATE TABLE Students(
            RollNo NOT NULL PRIMARY KEY,
            Name VARCHAR(20) NOT NULL,
            ExamRollNo VARCHAR(30) NOT NULL,
            CONSTRAINT FKExamRollNo FOREIGN KEY (ExamRollNo)
            REFERENCES Exams(ExamRollNo) 
      );
```

###### ADD FOREIGN KEY DYNAMICALLY 
----------------------------------------------------------      

###### EXAMPLES 

> Basic One  (Without Name)
```sql
      ALTER TABLE Students 
      ADD FOREIGN KEY (ExamRollNo) 
      REFERENCES Exams(ExamRollNo);
```

> Named Foreign Key
```sql
      ALTER TABLE Students 
      ADD CONSTRAINT FKExamRollNo
      FOREIGN KEY (ExamRollNo)
      REFERENCES Exams(ExamRollNo);
```

###### DROP a FOREIGN KEY CONSTRAINT 
-----------------------------------------------------------

###### EXAMPLES 
```sql
      ALTER TABLE Students 
      DROP FOREIGN KEY FKExamRollNo;
```




1. NOT NULL 
   * Attribute cannot be null 
2. UNIQUE 
   * Attribute should be unique
3. AUTO_INCREMENT 
   * Auto increment the value 
   * Can be used for PRIMARY KEY

4. DEFAULT 'default_value'    
   * To set default value to a                   attribute

##### 5. CHECK condition         
-------------------------------------------------------------
* It is used to limit the value range that can be placed in a column 
* CHECK constraint defined for a single column allows certain values for that column 
* CHECK constraint defined for table can limit the values in certain columns based on values on other columns in the row 


###### CHECK on CREATE TABLE
* It ensures a person must be at least 18   
```sql
      CREATE TABLE persons(
         ID int NOT NULL,
         FirstName VARCHAR(20),
         LastName VARCHAR(20) NOT NULL,
         Age int,
         CHECK (Age >= 18) 
      );
```

* To allow naming of the constraint we can use CONSTRAINT keyword 
```sql
      CREATE TABLE persons(
         ID int NOT NULL,
         FirstName VARCHAR(20),
         LastName VARCHAR(20) NOT NULL,
         Age int,
         CONSTRAINT ValidAge CHECK (Age >= 18) 
      );
```

###### ADDING CHECK ON PARTICULAR COLUMN 
   ------------------------------------------------------      

```sql
      ALTER TABLE persons
      ADD CHECK (Age>=18);
```
```sql 
      ALTER TABLE persons
      ADD CONSTRAINT ValidAge CHECK (Age>=18);
```

###### DROP A CHECK CONSTRAINT 
---------------------------------------------------------

```sql
      ALTER TABLE persons
      DROP CONSTRAINT ValidAge;
```

```sql
      ALTER TABLE 
      DROP CHECK ValidAge;
```

##### 6. CREATE INDEX STATEMENT
---------------------------------------------------------------
* It is used to create indexes in table 
* Indexes are used to retrieve data from the database quickly 
* Users cannot see the indexes, they are just used to speed up searches/queries 


**NOTE:** Updating a table with indexes takes more time than updating a table without (because the indexes need an update)

###### CREATE INDEX syntax 
* Duplicate values are allowed 
```sql
      CREATE INDEX index_name 
      ON table_name (col_1, col_2, ..);
```


###### CREATE UNIQUE INDEX syntax
* Duplicate values are not allowed 
```sql
      CREATE UNIQUE INDEX index_name 
      ON table_name (col_1, col_2, ...);
```  
 

###### CREATE INDEX example
* It creates an index named "index_lastname"on "LastName" column in "persons" table  
```sql
      CREATE INDEX index_lastname 
      ON persons (LastName);
```

* It creates an index named 'index_personName' on combination of (FirstName, LastName)
```sql
      CREATE INDEX index_personName
      ON persons (FirstName, LastName);
```

###### DROP INDEX statement
* It is used to delete an index in a table 
```sql
      ALTER TABLE table_name
      DROP INDEX index_name; 
```


##### ON DELETE SET NULL 
--------------------------------------------------------------
* This clause can be used with FOREIGN KEY so that when the record in 'referenced' table is deleted, the child table's associated value of FOREIGN KEY will be set to NULL




##### ON DELETE CASCADE 
---------------------------------------------------------------
* This clause can also be used with FOREIGN KEY so that  when the records in child table is deleted, all records  that are associated with it will be deleted 

###### FIND TABLES AFFECTED by ON DELETE CASCADE action
      USE information_schema;

      SELECT [table_name]
      FROM referential_constraints 
      WHERE 
         constraint_schema = '[database_name]'
         AND referential_table_name = '[parent_table_name]'
         AND delete_rule = 'CASCADE';   



##### TRIGGERS 
--------------------------------------------------------------
* In MySQL, trigger is a stored program invoked  automatically in response to an insert, update or delete that occurs in the associated table

* **EXAMPLE :**
          We can define a trigger that gets automatically
          invoked before a new row is inserted to the table 


###### TYPES OF TRIGGERS 
* Row-level Trigger        
   * Invoked for each row 
* Statement-level Trigger 
    *  Invoked for each transaction 

**NOTE :** MySQL does not support Statement-level trigger


###### CREATION SYNTAX       
```sql
      CREATE TRIGGER TriggerName 
      {BEFORE | AFTER} {INSERT | UPDATE | DELETE}
      ON TableName
      FOR EACH ROW TriggerBody;
```
         
###### Description 
* First specify the name of the trigger we  want to create
* Next, specify the trigger's action time  which can be either BEFORE or AFTER which indicates that trigger is invoked before or after each row is modified   
*  Then, specify the operation that activates the trigger, which can be INSERT, UPDATE, or DELETE
* After that, specify the name of the table to which the trigger belongs after the ON keyword
* Finally, specify the statement to execute when the trigger activates
                   
**NOTE :** If you want to execute multiple statements, you use the BEGIN END compound statements


###### ACCESSING VALUES OF THE COLUMN BEING AFFECTED BY DML STATEMENT
--------------------
* We can use OLD & NEW keywords to access the values of the column affected before or after the DML statement  
* **EXAMPLE**
   * If we update the column "description", in the trigger body, you can access the value of the "description" before the update using "OLD.description" and the new value using  "NEW.description"


###### LIST TRIGGERS 
```sql   
      SHOW TRIGGERS;
```


##### DATE DATA TYPE
--------------------------------------------------------------
* MySQL comes with the following data types for storing a date or a date/time value in the database:

        1) DATE      - format: YYYY-MM-DD
        2) DATETIME  - format: YYYY-MM-DD HH:MI:SS
        3) TIMESTAMP - format: YYYY-MM-DD HH:MI:SS
        4) YEAR      - format: YYYY or YY 


* **TIP :** 
           To keep our queries simple and easy to maintain,
           do not allow time components in our dates!  



#### SQL Hosting
--------------------------------------------------------------
* If we want our website to be able to store and retrieve data from a database, our web server should have access to a database-system that uses the SQL language

* If our web server is hosted by an Internet Service Provider (ISP), we will have to look for SQL hosting plans

* The most common SQL hosting databases are :-
      *  MS SQL Server
      *  Oracle
      *  MySQL
      *  MS Access




##### SQL INJECTION 
--------------------------------------------------------------
* It is a code injection technique that may destroy our database 
* It is one of the most common web hacking techniques 
* It is the placement of malicious code in SQL statements, via web page input 


###### SQL in WEB PAGES
-----------------------------------------------------------
* It generally occurs when a web page asks for username/userID, and instead of it user provides input which results into a SQL statement which will always return records from the database 
* Consider the following SQL statement which uses username & password inserted by the user 
  
```sql  
      username = getUsername();
      password = getPassword();

      SELECT * FROM users 
      WHERE username=username AND password=password; 
```

###### SQL INJECTION based on 1=1 is always true 
------------------------------------------------------
        
```sql
          username = 525 OR 1=1 --
          password = ***

         // SQL statement
         SELECT * FROM users 
         WHERE username=525 OR 1=1 -- password=***;
```
> Condition will always be true therefore it  returns entire table containing username &  password of each individual user


###### SQL Injection based on ""="" is always true   
-------------------------------------------------
* Consider the following SQL statement :
```sql       
      sql = SELECT * FROM Users
      WHERE Name ="' + uName + '" 
      AND Pass ="' + uPass + '"';
```

* USER INPUTS
```  
      uName= " OR ""="
      uPass= ***
```
* Now SQL statement  becomes
```sql
      sql = SELECT * FROM Users
      WHERE Name ="" OR ""="" 
      AND Pass ="***";
```
> It will always be true and hence returns  the important data to the user   


###### SQL Injection based on batched SQL statements 

--------------------------------------------------
* Most databases support batched SQL statements
* A batch of SQL statements is a group of two or  more SQL statements, separated by semi-colons

* **EXAMPLE :**
```sql
      SELECT * FROM users; DROP TABLE suppliers 
```
* Suppose the following SQL statement is used for verifying for existing user 
```sql
      txtUserID = getUserID(); 

      txtSQL = "SELECT * FROM Users 
      WHERE UserId = " + txtUserId;
```
* USER'S INPUTS 
```
   txtUserID = 10; DROP TABLE suppliers 
```
 It will result into a valid SQL statement manipulating the database     


###### SQL Parameters for Protection From SQL Injection
----------------------------------------------------------              
* SQL parameters are values that are added to an SQL query at execution time, in a controlled manner 





#### ER (ENTITY RELATIONSHIP) DIAGRAMS 
-------------------------------------------------


##### What is an ER Diagram ?
----------------------------------------------------------
* It shows the relationship among entity sets 
* An entity-set is a group of similar entities & these entities can have attributes 
* In terms of DBMS, an entity is a table or attribute of 
  a table in database 

* **Example :**
   ![ER Diagram](/assets/E-R-Diagram.png)  
   

##### GEOMETRIC SHAPES & THEIR MEANING
-------------------------------------------------------------

* **Rectangle:** Represents Entity sets.
* **Ellipses:** Attributes
* **Diamonds:** Relationship Set
* **Lines:** They link attributes to Entity Sets and Entity  sets to Relationship Set
* **Double Ellipses:** Multivalued Attributes
* **Dashed Ellipses:** Derived Attributes
* **Double Rectangles:** Weak Entity Sets
* **Double Lines:** Total participation of an entity in a relationship set


##### COMPONENTS OF A ER DIAGRAM 
------------------------------------------------------------
ER Diagram has three main components :-
1. Entity 
2. Attribute 
3. Relationship 



###### 1. ENTITY 
------------------------------------------------------------
* An entity is an object or component of data
* It is represented as triangle in ER Diagram 
* **Example**
![Entity](/assets/ER_diagram_entity.png) 

* **Example Description**
  * **Entities :** Student & College 
  * **Relationship :** One to Many 
  * **Reason :** It is because many students can study in a college & a student can study in only one college at a time 

###### WEAK ENTITY
-------------------------
* An entity that cannot be uniquely identified by its own attributes 
* It relies on the relationship with other entity is called WEAK entity  
* It is represented by double rectangle 
* **Example :**
 ![Weak Entity](/assets/ER_diagram_weak_entity.png) 

* **Example Description :**
A bank account has no existence until is related to any bank 

###### 2. ATTRIBUTE 
-------------------------
* An attribute describes the property of an entity 
* It is respresented by oval shape 
* **Types of attributes :** 
   i)  Key Attribute 
   ii) Multi-valued Attribute 
   iv) Composite Attribute 
   v)  Derived Attribute   

###### i) KEY ATTRIBUTE 
------------------------
* A key attribute can uniquely indetify an entity from an entity set 
* Key attribute is underlined
* **Example :**
![Key Attribute](/assets/ER_diagram_key_attribute.png)

* **Example Description :**
RollNo can uniquely identify the student 
entity because it has unique for each records 
of Student 


###### ii) Composite Attribute 
-----------------------
* An attribute which is a combination of other attributes is known as Composite Attribute 

* **Example :**
![Composite Attribute](/assets/ER_diagram_composite_attribute.png)

* **Example Description :**
Address attribute is the combination of three other attributes(Pin, State, Country)


###### iii) Multi-valued Attribute 
-------------------------
* An attribute that can hold multiple values is known as multi-valued attribute 
* It is represented by **double ovals** 
* **Example :**
**PhoneNumber** attribute can have multiple values because a person may have multiple SIMs


###### vi) Derived Attribute 
-------------------------
* It is an attribute which is not part of the entity but we can derive it from the existing attributes of the entity 
* It is represented by dashed oval in ER Diagram 


> **_ER Diagram showing multi-valued  & derived attributes_**
 
![Derived + Multivalued Attributes](/assets/multivalued_derived_attribute.png) 



##### 3. RELATIONSHIP 
-------------------------
* Diamond shape shows the relationship between two entities 
* **Types of Relationship :-**
  i) One to One 
  ii) One to Many
  iii) Many to One 
  iv) Many to Many 
     

###### i) ONE TO ONE RELATIONSHIP 
------------------------
* When a single instance of an entity is associated with a single instance of another entity then it is called **one-to-one relationship**
* **Example :**
![One to One Relationship](/assets/ER_diagram_one_to_one.png)

* **Example Description :**
It is because one person can have only one passport & a passport must belongs to only one person


###### ii) ONE TO MANY RELATIONSHIP 
-------------------------
* When a single instance of one entity is associated with many instances of another entity then it is of **one to many relationship** 
* **Example :**
![One to Many Relationship](/assets/ER_diagram_one_to_many.png) 

* **Example Description :**
It is because a customer can have many orders but an order can have only one customer 


###### iii) MANY TO ONE RELATIONSHIP 
-------------------------
* When many instances of an entity is associated with only one instance of another entity then it is of **many to one relationship** 
* **Example :**
![Many to one Relationship](/assets/ER_diagram_many_to_one.png)
* **Example Description :**
It is because a college can have many students but a student can only study in one college 


###### iv) MANY TO MANY RELATIONSHIP 
-------------------------
* When many instances of an entity is associated with many instances of another entity then it is of **many to many relationship** 
* **Example :**
![Many to Many Relationship](/assets/ER_diagram_many_to_many.png)
* **Example Description :**
It is because a student can have many projects assigned to him/her also a project can have many students associated with it 


###### TOTAL PARTICIPATION OF AN ENTITY SET 
-------------------------
* A Total participation of an entity set represents that each entity in entity set must have at least one relationship in a relationship set.
* **Example :**
![Total participation](/assets/total_participation_diagram.png)

* **Example Description :**
Here each college must have at least one student 

[Images Source]((https://beginnersbook.com/))




#### DESIGNING AN ER DIAGRAM FROM DATA REQUIREMENTS 
-------------------------------------------------------------

Company Data Requirements 

```
      The company is organized into brances. Each branch 
      has a unique number, a name and a particular employee
      who manages it 

      The company makes it's money by selling to clients.
      Each client has a name & a unique number to identify
      it.

      The foundation of the company is it's employees. Each
      employee has a name, birthday, sex, salary and a unique number

      An employee can work for one branch at a time, and each
      branch will be managed by one of the employees that 
      work there. We will also want to keep track of when 
      the current manager started as manager.

      An employee can act as a supervisor for other employees
      at the branch, an employee may also act as the supervisor for employees at other branches. An employee can have at most one supervisor 

      A branch may handle a number of clients, with each 
      client having a name & a unique number to identify 
      it. A single client may only be handled by one branch at a time.

      Employees can work with clients controlled by their branch to sell them stuff. If neccessary multiple 
      employees can work with the same client. We will 
      want to keep track of how many dollars worth of stuff
      each employee sells to each client they work with

      Many branches will need to work with suppliers to buy
      inventory. For each supplier we will keep track of their name & the type of product they aree selling the branch. A single supplier may supply products to 
      multiple branches.  
```

> The company is organized into **brances**. Each branch has a **unique number**, a **name**

![Branch](/assets/branch.png)

> The company makes it's money by selling to **clients**.Each client has a **name** & a **unique number** to identify it.

![Clients](/assets/clients.png)

>  The foundation of the company is it's **employees**. Each employee has a **name**, **birthday**, **sex**, **salary** and a **unique number**

![Employees](/assets/employees.png)


>  An employee can **work for** one branch at a time

![Work For Relationship](/assets/worksFor.png)


>  Each **branch** will be **managed** by one of the **employees** that work there. We will also want to keep track of when the current manager **started as manager**.

![Manages by Relationship](/assets/manages.png)


>  An **employee** can act as a **supervisor** for other employees at the branch, an employee may also act as the supervisor for employees at other branches. An employee can have at most one supervisor 

![Supervision Relationship](/assets/supervisor.png)

> A **branch** may **handle** a number of **clients**, with each client having a name & a unique number to identify it. A single client may only be handled by one branch at a time.

![Handles Relationship](/assets/handles.png)


> _Employees_ can **work with** _clients_ controlled by their branch to sell them stuff. If neccessary multiple employees can work with the same client.
> We will want to keep track of how many dollars worth of stuff each employee **sells** to each client they work with

![Works with Relationship](/assets/worksWith.png)


> Many _branches_ will need to **work with** _suppliers_ to buy inventory. For each supplier we will keep track of their **name** & the **type** of product they are selling to the branch. A single supplier may supply products to multiple branches. 

![Supplies Relationships](/assets/supplies.png)



##### STEPS ON CONVERTING AN ER DIAGRAM INTO RELATIONSHIP TABLES 
-----------------------------------------------------------

1. **Mapping of Regular Entity Types** 
      * For each regular entity type create a relation(table)
        that includes all the simple attributes of that 
        entity 

![After step 1](/assets/afterStep1.png)



2. **Mapping of Weak Entity Types** 
      * For each weak entity type create a relation(table)
        that includes all simple attributes of the weak 
        entity
      * The partial key of the new relation should be the 
        partial key of the weak entity plus the primary
        key of its owner   

![After Step 2](/assets/afterStep2.png) 


3. **Mapping of Binary 1:1 relationship types** 
      * Include one side of the relationship as a foreign key (Favour total participation)

![After Step 3](/assets/afterStep3.png) 

4. **Mapping of Binary 1:N Relationship Types**

* Include the 1 side's primary key as foreign key on the N side's relation(table)

![After Step 4](/assets/afterStep4.png)


5. **Mapping Binary N:M Relationship Types**
   
* Create a new relation(table) who's primary key is a combination of both entites' primary key's. 
* Also include any relationship attributes 

![After Step 5](/assets/afterStep5.png)     

###### Relationship between Tables 

![Relationship between Table](/assets/relBetweenTables.png)

