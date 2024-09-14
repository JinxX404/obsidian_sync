- SQL ⇒ Structured query language
- ANSI SQL ⇒ **American National Standards Institute Structured Query Language**

![[/Untitled.png|Untitled.png]]

  

- Type of query in Transact-SQL
    
    ![[Untitled 1.png]]
    
- When you create new database…
    
    there are two file
    
    1. filename.mdf ⇒ metadata file → table,
    2. filename.ldf ⇒ log file → any modify on data as archive

# ==Some of The Most Important SQL Commands==

- `SELECT` - extracts data from a database
- `UPDATE` - updates data in a database
- `DELETE` - deletes data from a database → delete raw
- `INSERT INTO` - inserts new data into a database
- `CREATE DATABASE` - creates a new database
- `ALTER DATABASE` - modifies a database
- `CREATE TABLE` - creates a new table
- `ALTER TABLE` - modifies a table → delete column
- `DROP TABLE` - deletes a table
- `CREATE INDEX` - creates an index (search key)
- `DROP INDEX` - deletes an index

  

- ==**Select**==
    
    ```SQL
    SELECT * FROM Customers;
    SELECT CustomerName, City FROM Customers;
    ------------------------------------------
    
    SELECT DISTINCT Country FROM Customers;
    ```
    
      
    
    ==**where**==
    
    |   |   |   |
    |---|---|---|
    |Operator|Description|Example|
    |=|Equal|[Try it](https://www.w3schools.com/sql/trysql.asp?filename=trysql_op_equal_to)|
    |>|Greater than|[Try it](https://www.w3schools.com/sql/trysql.asp?filename=trysql_op_greater_than)|
    |<|Less than|[Try it](https://www.w3schools.com/sql/trysql.asp?filename=trysql_op_less_than)|
    |>=|Greater than or equal|[Try it](https://www.w3schools.com/sql/trysql.asp?filename=trysql_op_greater_than2)|
    |<=|Less than or equal|[Try it](https://www.w3schools.com/sql/trysql.asp?filename=trysql_op_less_than2)|
    |<>|Not equal. **Note:** In some versions of SQL this operator may be written as !=|[Try it](https://www.w3schools.com/sql/trysql.asp?filename=trysql_op_not_equal_to)|
    |BETWEEN|Between a certain range|[Try it](https://www.w3schools.com/sql/trysql.asp?filename=trysql_op_between)|
    |LIKE|Search for a pattern|[Try it](https://www.w3schools.com/sql/trysql.asp?filename=trysql_op_like)|
    |IN|To specify multiple possible values for a column|[Try it](https://www.w3schools.com/sql/trysql.asp?filename=trysql_op_in)|
    ![[Pasted image 20240807191716.png]]
    ```SQL
    -- between
    SELECT * FROM Products
    WHERE Price BETWEEN 50 AND 60;  
    ------------------------------
    
    -- like
    SELECT * FROM Customers
    WHERE City LIKE 's%';
    -------------------------------
    
    -- in
    SELECT * FROM Customers
    WHERE City IN ('Paris','London');
    -------------------------------------
    
    -- and or
    SELECT * FROM Customers
    WHERE Country = 'Spain' 
    AND CustomerName LIKE 'G%' 
    OR CustomerName LIKE 'R%';
    -----------------------------
    
    -- not
    SELECT * FROM Customers
    WHERE NOT Country = 'Spain';
    
    -- not like
    SELECT * FROM Customers
    WHERE CustomerName NOT LIKE 'A%';
    
    -- not between
    SELECT * FROM Customers
    WHERE CustomerID NOT BETWEEN 10 AND 60;
    
    -- not in
    SELECT * FROM Customers
    WHERE City NOT IN ('Paris', 'London');
    ------------------------------------------
    
    -- null
    SELECT CustomerName, ContactName, Address
    FROM Customers
    WHERE Address IS NULL;
    
    -- not null
    SELECT CustomerName, ContactName, Address
    FROM Customers
    WHERE Address IS NOT NULL;
    ```
    
      
    
    ==**Order by**==
    
    ```SQL
    SELECT column1, column2, ...
    FROM table_name
    ORDER BY column1, column2, ... ASC|DESC;
    
    /*
    ORDER BY Several Columns
    The following SQL statement selects all customers from the
     "Customers" table, sorted by the "Country" and the "CustomerName"
      column. This means that it orders by Country, but if some rows 
      have the same Country, it orders them by CustomerName:
    */
    
    SELECT * FROM Customers
    ORDER BY Country ASC, CustomerName DESC;
    
    SELECT column1, column2, ...
    FROM table_name
    ORDER BY 1; // first column in select columns
    ```
    
- ==**Insert**==
    
    The `INSERT INTO` statement is used to insert new records in a table.
    
    ```SQL
    INSERT INTO table_name (column1, column2, column3, ...)
    VALUES (value1, value2, value3, ...);
    
    -- single row
    INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
    VALUES
    ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway')
    
    -- multi rows
    INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
    VALUES
    ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway'),
    ('Greasy Burger', 'Per Olsen', 'Gateveien 15', 'Sandnes', '4306', 'Norway'),
    ('Tasty Tee', 'Finn Egan', 'Streetroad 19B', 'Liverpool', 'L1 0AA', 'UK');
    ```
    
- ==**Update**== 
    
    ```SQL
    UPDATE table_name
    SET column1 = value1, column2 = value2, ...
    WHERE condition; -- without condition you will update all rows 🤡
    
    UPDATE Customers
    SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
    WHERE CustomerID = 1; 
    ```
    
- ==**Delete**==
    
    The `DELETE` statement is used to delete existing records in a table.
    
    ```SQL
    DELETE FROM table_name WHERE condition;
    
    DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
    
    DELETE FROM Customers; -- delet rows not table
    ------------------------------------
    DROP TABLE Customers; -- delet table completly
    ```
    
- ==**Alter**==
    
    The `ALTER TABLE` statement is used to add, delete, or modify columns in an existing table.
    
    The `ALTER TABLE` statement is also used to add and drop various constraints on an existing table.
    
    ```SQL
    // alter -> add, delete column. Rename and change column data type
    // add column
    ALTER TABLE Customers
    ADD Email varchar(255);
    
    // delete column
    ALTER TABLE Customers
    DROP COLUMN Email;
    
    // rename column
    ALTER TABLE table_name
    RENAME COLUMN old_name to new_name;
    
    //To change the data type of a column
    ALTER TABLE table_name
    ALTER COLUMN column_name datatype;
    // another way old version
    ALTER TABLE table_name
    MODIFY COLUMN column_name datatype;
    
    // delete table
    drop teble emp
    ```
    
- ==**Alias**==
    
    SQL aliases are used to give a table, or a column in a table, a temporary name.
    
    ```SQL
    SELECT CustomerID AS ID
    FROM Customers;
    
    SELECT CustomerID ID
    FROM Customers; -- as is optional
    
    SELECT ProductName AS [My Great Products]
    FROM Products; -- in case string include spaces
    
    SELECT ProductName AS "My Great Products"
    FROM Products;
    
    SELECT CustomerName, CONCAT(Address,', ',PostalCode,', ',City,', ',Country) AS Address
    FROM Customers;
    ```
    

  

- ==Type of join==
    
    - cross join
        - cartesian product
    - inner join
        - equijoin
    - outer join
        - left
        - right
        - full
    - self join (unary relationship)
    
    in case you can not open a diagram
    
    - right click, properties ,files, write sa
    
      
    
    - self join
        
        ```SQL
        
        select FirstN as employee, FirstN as super from 
        Employee X, Employee Y; 
        // Employee X, Employee Y -> create a copy of my table
        // any join from parent child one has PK and another has FK 
        // table in database is child
        // new table has PK, old table has  FK
        
        select FirstN as employee, FirstN as super from 
        Employee X, Employee Y
        where x.superssn = y.SSN; 
        ```
        
    - Isnull
        
        ```SQL
        select isnull(fname, '') from student;
        // replace any null value bt  ''
        ```
        

  

## ==Normalization==



  

---

  

  

- ==Aggregate Function==
    
    - Count, Max, Min, Average and sum
    - it’s output value
    - count function don’t take null value → count value
    
    ```SQL
    select sum(salary) from employee
    // count-> count row
    ```
    
    - aggregate function + select → you must do grouping
    
    ```SQL
    select Min(salary),did from employee // XXXX
    
    select Min(salary),did 
    from employee
    group by did;
    ```
    
    ![[/Untitled 3.png|Untitled 3.png]]
    
    - in case you want to use where with aggregate → where == have
    
    ```SQL
    select Min(salary),did 
    from employee
    group by did
    where sum(salary)>20000; // XXXXXXXXX
    
    select sum(salary),did 
    from employee
    group by did
    having sum(salary)>20000;
    ```
    
    - in case your group by two columns it will join them and group by it
    - ==where affect value not number of rows==
    - ==having affect rows (groups)==
    
      
    
      
    
- ==Subqueries==
    
    take output of query as input in another one
    
    ```SQL
    /*outer query*/select * 
    from Employee
    where Salary < (select avg(Salary) from Employee) -- inner query
    ```
    
    - you can use it without aggregate function
    
    ```SQL
    // department has student
    select Dname
    from Department
    where Dnumber in (select Dno from Employee
    					where Dno is not null)
    ```
    
    - Subqueries with DML (update, delete) is okay
- ==Union==
    
    two table in on table
    
    The `UNION` operator selects only distinct values by default. To allow duplicate values, use `UNION ALL`:
    
    ```SQL
    select Fname
    from Employee
    union all
    select Dname from Department
    ```
    
      
    
- ==EERD==
    
    - two entities from the same parent have some shared attributes
    - ERD + inheritance
    
    ![[/Untitled 4.png|Untitled 4.png]]
    
    ## ==Constraints in Supertype==
    
    - Completeness Constrains
        - Total Specialization (double line)
        - Partial Specialization
    - Disjoint-ness Constrains
        - Total Disjoint (d)
        - Overlap (o) → one parent may be consider more than one child
    
    - examples
        
        ![[/Untitled 5.png|Untitled 5.png]]
        
        ![[/Untitled 6.png|Untitled 6.png]]
        
        ![[Untitled 7.png]]
        
        ![[Untitled 8.png]]
        
          
        
    - Discriminator
        
        ![[Untitled 9.png]]
        
        ![[Untitled 10.png]]
        
    - ==Overall Example==
        
        ![[Untitled 11.png]]
        
        ![[Untitled 12.png]]
        
        ![[Untitled 13.png]]
        
        ![[Untitled 14.png]]
        
- ==Builtin function==
    - getdate()
    - isnull()
    - coalesce
    - concat
    - convert
    - year(getdate())
    - month(getdate())
    - substring(Fname, 1,3) from student
    - select db_name()
    - select suser_name()

---

  

# ==SQL Server==

- It is a fully RDBMS 
- The table 1 : M relationships ( parent and child )

![[Untitled 15.png]]

![[Untitled 16.png]]

- Instance it is a group of services

![[Untitled 17.png]]

  

- ==Authentication==: user name & password
- ==Authorization==: permission

You can add user to access the server but he can’t see the database , so add the same user to security from the database (ITI).

Now add the permission of the user

- You can connect service with excel and cmd

![[Untitled 18.png]]

  

---

# ==Queries==

- top(num)

```SQL

select top(3)
from employee;

select top(3) fname
from Employee
where Address = 'mansoura';
```

- top(num) with ties → come with order by

```SQL
select top(4) with ties *
from Employee
order by Salary
 
-- incase the lase salary another employee has the same salary it 
-- output
```

- newid() ⇒ return Global Universal ID (GUI)

```SQL
select * from Employee
order by newid();
```

- create identity to table

```SQL
ALTER TABLE Employee
ADD  id INT identity(1,1); -- start from 1 increase by one
```

- select into -> copy employee to table two

```SQL

select * into table2
from Employee;

select * into t4
from Employee
where 1= 2; -- false condition -> the name of column no data in t4  copy structure
```

- take date from table to another table

```SQL
insert into t4
select * from Employee;
```

```JavaScript
/*The COALESCE function in SQL is used to return the first non-null expression among its arguments. It takes multiple parameters and returns the first non-null value from those parameters.
*/
SELECT COALESCE(NULL, 2, 3); -- Returns 2
SELECT COALESCE(NULL, NULL, 3); -- Returns 3
```

```SQL
--DATEDIFF
SELECT DATEDIFF(end_date, start_date) AS day_difference;

----------
DATE_SUB(w.recordDate, INTERVAL 1 DAY)

--w.recordDate represents a date or datetime column named recordDate from a table or 
--a variable w.
--INTERVAL 1 DAY indicates that you want to subtract one day from the recordDate.
```

## ==Execution order==

1. from
2. join
3. on
4. where
5. group
6. having
7. select
8. order by
9. top

  

```SQL
DB Object [table view function SP Rule] to access it….
full path -> [ServerName].[DBName].[SchemaName].[ObjectName]
```

  

## ==Ranking function==

- Special builtin function to answer some question on business

1. Row_Number()
2. Dense_rank()
3. NTiles(group)
4. Rank()

```SQL
-- rowNumber

select * , 
ROW_Number() over(order by salary desc) as RN,
DENSE_RANK() over(order by salary desc) as DR,
NTile(3) over(order by salary desc) as G
 from employee;
 
 // create column RN numberde from 1 to n 
 // ntile() 
```

![[Untitled 19.png]]

```SQL
-- partition

select *, ROW_NUMBER() over(partition by dno order by salary desc)
from Employee;

-- make group for depend on dno then order salary fro each department
```

```SQL
select concat('The ', Name, ' is only! ', ListPrice)
from Production.Product
where ListPrice in (100, 120);

-- to concat the information
```

# ==Data Types==

- Numeric DT
    - bit —> bool
    - tiny int —> 1 Byte -128 : +127 — unsigned 0 : 255
    - smallint —> 2 byte -32768 : +32767
    - int —> 48
    - big int —> 88
- Decimal DT
    - money
    - smallmony
    - real
    - float
    - dec
- Char DT
    - char(10)
    - nchar(10)
    - varchar(10)
    - nvarchar(10)
    - nvarchar(max)
- DateTime
    - Date MM/DD/YYYY
    - Time hh:mm:12.765
    - Time(7) hh:mm:12.7655545
    - Smalldatatime MM/DD/YYYY hh:mm:00
    - datetime
    - datetime2(7)
    - datetimeoffset
- Binary DT
    - binary
    - image
- Other
    - XML
    - unique_identifier
    - sql_variant

  

- Details
    
    ![[Untitled 20.png]]
    
    ![[Untitled 21.png]]
    
    ![[Untitled 22.png]]
    
    ![[Untitled 23.png]]
    

  

## ==Wildcard Character==

- [https://www.w3schools.com/sql/sql_wildcards.asp](https://www.w3schools.com/sql/sql_wildcards.asp)

  

# ==@@==

- Global variable names begin with a `@@` prefix. You do not need to declare them, since the server constantly maintains them. They are system-defined functions and you cannot declare them.
- [https://www.codeproject.com/Articles/39131/Global-Variables-in-SQL-Server](https://www.codeproject.com/Articles/39131/Global-Variables-in-SQL-Server)

---

  

Every database language has a way to create

Microsoft ⇒ has two types of creation:

1. Physical Representation → on hard disk → Ldf, Mdf
2. Logical Representation → File group (Primary fg) it is a pointer for Mdf file

to protect your data from any destroy you can create Ndf files and another Fg files

- Ex
    
    - In case you have two tables to do join operations between them → put every file in different hard disk to increase you performance
    - Backup ⇒ there are a type of it call backup file group
    
      
    

## ==How files appear==

It is a connection of small files

![[Untitled 24.png]]

> [!important]  
> more details on this video https://www.youtube.com/watch?v=8tUcJJcWbys&list=PLYpJKvLDuJhgMzOXRwUJ2_ZlVt3zSh8PA&index=6&t=46s (minute 16:00) to practice  

- each table and each column has it’s own properties

==**Identity columns**==**: can be used for generating key values**. The identity property on a column guarantees the following conditions: Each new value is generated based on the current seed and increment. Each new value for a particular transaction is different from other concurrent transactions on the table.  
  

![[Untitled 25.png]]

if is Persisted is yes the value will save on the hard disk

---

![[Untitled 26.png]]

did not allow null value to take space on hard disk  
  

---

![[Untitled 27.png]]

update ⇒ parent updated child will update also

delete → parent deleted child will set as null

==📌====**TIPS**==

- Driven Attribute
    
    some time in your database ==you have to put the driven attribute in the same table== not in independence table cause of to improve the performance of the table in case you will call the table a lot
    
- Null in Equation
    
    null with any value == null
    
    ISNULL(_expression_, _value_) ⇒ if ==expression== is null return ==value==
    
- Schema (dbo)
    
    it is a logical grouping for table
    
    ![[Untitled 28.png]]
    
    To create scema
    
    ```SQL
    create schema HR
    // it is appear in security folder
    //////////////////////////////////////
    
    // to add table to schema
    alter schema hr transfer student
    ```
    
    ---
    
    Shortcut for table name
    
    ```SQL
    create synonym HE for employee
    ```
    
    ```SQL
    drop table course // delete data and metadata
    
    delete from course // delete data, can use where condition, slower than trancate as
    // it writen in log file so you can undelete,
     // did not reset identity () if you delete from 1-1000 it will start again from 1001
    // use delete with parent table
    
    truncate table course // delete data
    ```
    
      
    
    ---
    
      
    

---

# ==DB Integrity==

- `[NOT NULL](https://www.w3schools.com/sql/sql_notnull.asp)` - Ensures that a column cannot have a NULL value
- `[UNIQUE](https://www.w3schools.com/sql/sql_unique.asp)` - Ensures that all values in a column are different
- `[PRIMARY KEY](https://www.w3schools.com/sql/sql_primarykey.asp)` - A combination of a `NOT NULL` and `UNIQUE`. Uniquely identifies each row in a table
- `[FOREIGN KEY](https://www.w3schools.com/sql/sql_foreignkey.asp)` - Prevents actions that would destroy links between tables
- `[CHECK](https://www.w3schools.com/sql/sql_check.asp)` - Ensures that the values in a column satisfies a specific condition
- `[DEFAULT](https://www.w3schools.com/sql/sql_default.asp)` - Sets a default value for a column if no value is specified
- `[CREATE INDEX](https://www.w3schools.com/sql/sql_create_index.asp)` - Used to create and retrieve data from the database very quickly

![[Untitled 29.png]]

To add composite primary key

```SQL
create table emp(
eid int  identity(1,1),
ename varchar(20),
eadd varchar(20) default 'alex',
hiredate date default getdate(),
sal int,
overtime int,
netsalary as (isnull(sal,0) + isnull(overtime,0)) persisted,
BD date, 
age  as (year(getdate()) - year(BD)), -- can not be persisted as it will change every second cause of getdate() function 
gender varchar(10),
hourRate int not null,
did int,
constraint c1 primary key (eid, ename), // composite
constraint c2 unique(sal),
constraint c3 unique(overtime), //constraint c2 unique(sal, overtime) sal and overtime unique together 
constraint c4 check(sal>1000),
constraint c5 check (eadd in ('alex', 'cairo', 'mansoura')),
constraint c6 check (gender = 'F' or gender = 'M'),
constraint c7 foreign key(did) references dep(did)
	on delete set null on update cascade,
)
```

To edit some constraint

```SQL
alter table emp add constraint c100 check(hour_rate >100) -- constrain apply on old and new data
alter table emp drop constraint c3 -- delete constraint
```

---

## ==Rules==

- Constraint on new data only
- Constraint shared with many tables
- Datatype have constraint and default value
- 📍Column have on rule but many constrint

```SQL
create rule r1 as @x>1000;
// it is in programmabilitiy -> rules folder 
```

```SQL
alter table emp add constraint c20 check(sal<1000);
// if there sal > 1000 it will not apply the constraint and cause an error
// rules solve it
-----------------------------------------------------
create rule r1 as @x>1000;
sp_bindrule r1, 'emp.sal'; -- it will applay on new data only 

// to unbind rule
sp_unbindrule 'emp.sal';
// to drop rule you have to unbind it from tables
drop rule r1
```

---

## Default

```SQL
create default def1 as 5000;
sp_bindefault def1,'emp.sal';

sp_unbindefault 'emp.sal';
drop default def1;
```

## Data type

to create data type

- create rule
- create default
- don’t put them to any table

---

Create Schema

```SQL
CREATE SCHEMA new_schema;
ALTER TABLE old_schema.table1 SET SCHEMA new_schema;
ALTER TABLE old_schema.table2 SET SCHEMA new_schema;
```

```SQL
SELECT 
    constraint_name, 
    constraint_type
FROM 
    information_schema.table_constraints
WHERE 
    table_name = 'Employee';
```

```JavaScript
update project
set Budget += (Budget*20)/100
where projectNo in(
select projectNo
from works_on w
where EmpNo = 10102
);
```