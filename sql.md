# SQL for Data Science


## SQL Basics
**SQL (Structured Query Language)** - standard language for many relational database management systems and data manipulation. SQL is used to:
- read / retrieve data
- write data - add data to the table
- update data - insert new data

**Database** (schema) - a set of tables. 
**Table** (relation) - A group of rows sharing the same labeled element
- Column (attribute) - Labeled element
- Row (entity, tuple) - a single item

  **Database models**
- Relational - allows for easy querying and manipulation 
- Transactional - more operational

**Relationships** - describe associations between entities. Main types:
- one-to-one
- one-to-many
- many-to-many

**Keys** - define. Types of keys:
- Primary Key - A column or set of columns whose values uniquely identify every row in a table
- Foreign Key - A column or set of columns that can be used to identify a single row in another table

**Temporary table** - will be deleted when session is terminated
- faster than creating a real table
- useful for complex queries

[https://www.vertabelo.com/blog/data-warehouse-modeling-star-schema-vs-snowflake-schema/](https://www.vertabelo.com/blog/data-warehouse-modeling-star-schema-vs-snowflake-schema/)
 

### Basic data types in SQL

Always use single quote `'` around strings and dates

#### Text and string types
- `text` — a string of any length, like Python \`str\` or \`unicode\` types
- `char(n)` — a string of exactly \*n\* characters.
- `varchar(n)\` — a string of up to \*n\* characters.

  

#### Numeric types

  

\- \`integer\` — an integer value, like Python \`int\`.

 \- \`real\` — a floating-point value, like Python \`float\`. Accurate up to six decimal places.

 \- \`double precision\` — a higher-precision floating-point value. Accurate up to 15 decimal places.

 \- \`decimal\` — an exact decimal value.

  

#### Date and time types

  

\- \`date\` — a calendar date; including year, month, and day.

 \- \`time\` — a time of day.

 \- \`timestamp\` — a date and time together.

  

## Introduction to Data Modeling

  

\*\*Databases\*\*: A database is a structured repository or collection of data that is stored and retrieved electronically for use in applications. Data can be stored, updated, or deleted from a database.

  

\*\*Database Management System (DBMS)\*\*: The software used to access the database by the user and application is the database management system. Check out these few links describing a DBMS in more detail.

  

\*\*Data modeling\*\* - an abstraction that organizes elements of data and how they relate to each other

  

\*\*Data Modeling Process\*\*

Conceptual -\\> Logical -\\> Physical

  

\*\*Key points about Data Modeling\*\*

  

\- Data Organization: The organization of the data for your applications is extremely important and makes everyone's life easier.

\- Use cases: Having a well thought out and organized data model is critical to how that data can later be used. Queries that could have been straightforward and simple might become complicated queries if data modeling isn't well thought out.

\- Starting early: Thinking and planning ahead will help you be successful. This is not something you want to leave until the last minute.

\- Iterative Process: Data modeling is not a fixed process. It is iterative as new requirements and data are introduced. Having flexibility will help as new information becomes available.

  

Who does data modeling:

  

 \- data scientists

\- software engineers

\- data engineers

\- anyone involved in the process of using and analyzing data

  

### Relational Databases

  

Relation model organizes data into one or more tables (relations) of columns (attributes) and rows (tuples) with a unique key identifying each row.

  

Relational database is a digital database based on a relational model; managed by Relational Database Management System (RDBMS)

  

Structured Query Language (SQL) - a domain-specific language used in programming and designed for managing data held in RDBMS or for stream processing in RDSMS.

  

#### Basics

  

\- Database (schema) - collection of tables

\- Table (relation) - A group of rows sharing the same labeled element

 \- Column (attribute) - Labeled element

 \- Row (tuple) - a single item

  

  

Advantages of relational databases

  

1. Ease of use - SQL

2. Ability to use \`JOIN\` (combine data from different tables)

3. Ability to use aggregations and analytics

4. Great for smaller data volumes

5. Easier to change business requirements

6. Flexibility for queries

7. Modeling the data not modeling queries

8. Ability to use secondary indexes

9. Data integrity - ACID transactions

  

#### ACID Transactions

  

Properties of database transactions intended to guarantee validity even in the event of errors, power failures.

\*\*Atomicity\*\*: The whole transaction is processed or nothing is processed. A commonly cited example of an atomic transaction is money transactions between two bank accounts. The transaction of transferring money from one account to the other is made up of two operations. First, you have to withdraw money in one account, and second you have to save the withdrawn money to the second account. An atomic transaction , i.e., when either all operations occur or nothing occurs, keeps the database in a consistent state. This ensures that if either of those two operations (withdrawing money from 1st account and saving the money to the 2nd account) fail, the money is neither lost nor created.

\*\*Consistency\*\*: Only transactions that abide by constraints and rules are written into the database otherwise the database keeps the previous state. The data should be correct across all rows and tables. 

\*\*Isolation\*\*: Transactions are processed independently and securely, order does not matter. A low level of isolation enables many users to access the data simultaneously, however this also increases the possibilities of concurrency effects (e.g., dirty reads or lost updates). On the other hand, a high level of isolation reduces these chances of concurrency effects, but also uses more system resources and transactions blocking each other.

\*\*Durability\*\*: Completed transactions are saved to database even of cases of system failure. A commonly cited example includes tracking flight seat bookings. So once the flight booking records a confirmed seat booking, the seat remains booked even if a system failure occurs.

  

#### When not to use relational databases

  

1. Have large amounts of data: Relational Databases are not distributed databases and because of this they can only scale vertically by adding more storage in the machine itself. You are limited by how much you can scale and how much data you can store on one machine. You cannot add more machines like you can in NoSQL databases.

2. Need to be able to store different data type formats: Relational databases are not designed to handle unstructured data.

3. Need high throughput -- fast reads: While ACID transactions bring benefits, they also slow down the process of reading and writing data. If you need very fast reads and writes, using a relational database may not suit your needs.

4. Need a flexible schema: Flexible schema can allow for columns to be added that do not have to be used by every row, saving disk space.

5. Need high availability: The fact that relational databases are not distributed (and even when they are, they have a coordinator/worker architecture), they have a single point of failure. When that database goes down, a fail-over to a backup system occurs and takes time.

6. Need horizontal scalability: Horizontal scalability is the ability to add more machines or nodes to a system to increase performance and space for data.

  

  

### NoSQL Databases

  

NoSQL database has a simpler design, simpler horizontal scaling and finer control of availability. Data structures are different than those in Relational Databases (and they make some operations faster) 

NoSQL = Not Only SQL

  

#### Examples of NoSQL databases

  

1. Apache Cassandra (Partition Row store)

2. MongoDB (Document store)

3. DynamoDB (Key-Value store)

4. Apache HBase (Wide Column store)

5. NEo4J (Graph Database)

  

#### The basics of Apache Cassandra

  

\- Keyspace - collection of tables 

\- Table - a group of partitions

\- Partition

 \- fundamental unit of access

 \- collection of rows

 \- how data is distributed

\- Primary Key

 \- PK is made up of a partition key and clustering columns

\- Columns

 \- Clustering Columns and Data Columns

 \- Labeled element

 \- Row - a single item

  

  

#### When to use a NoSQL Database

  

1. Need to be able to store different data type formats: NoSQL was also created to handle different data configurations: structured, semi-structured, and unstructured data. JSON, XML documents can all be handled easily with NoSQL.

2. Large amounts of data: Relational Databases are not distributed databases and because of this they can only scale vertically by adding more storage in the machine itself. NoSQL databases were created to be able to be horizontally scalable. The more servers/systems you add to the database the more data that can be hosted with high availability and low latency (fast reads and writes).

3. Need horizontal scalability: Horizontal scalability is the ability to add more machines or nodes to a system to increase performance and space for data

4. Need high throughput: While ACID transactions bring benefits they also slow down the process of reading and writing data. If you need very fast reads and writes using a relational database may not suit your needs.

5. Need a flexible schema: Flexible schema can allow for columns to be added that do not have to be used by every row, saving disk space.

6. Need high availability: Relational databases have a single point of failure. When that database goes down, a failover to a backup system must happen and takes time.

  

  

#### When NOT to use a NoSQL Database?

  

1. When you have a small dataset: NoSQL databases were made for big datasets not small datasets and while it works it wasn’t created for that.

2. When you need ACID Transactions: If you need a consistent database with ACID transactions, then NoSQL databases will not be able to serve this need. NoSQL database are eventually consistent and do not provide ACID transactions.

3. When you need the ability to do JOINS across tables: NoSQL does not allow the ability to do JOINS. This is not allowed as this will result in a full table scans.

4. If you want to be able to do aggregations and analytics

5. If you have changing business requirements : Ad-hoc queries are possible but difficult as the data model was done to fix particular queries

6. If your queries are not available and you need the flexibility : You need your queries in advance. If those are not available or you will need to be able to have flexibility on how you query your data you might need to stick with a relational database

  

## Relational Data Models

  

Database - a set of related data and the way it is organized

  

### Importance of Relational Databases:

  

1. Standardization of data model: Once your data is transformed into the rows and columns format, your data is standardized and you can query it with SQL

2. Flexibility in adding and altering tables: Relational databases gives you flexibility to add tables, alter tables, add and remove data.

3. Data Integrity: Data Integrity is the backbone of using a relational database.

4. Standard Query Language (SQL): A standard language can be used to access the data with a predefined language.

5. Simplicity : Data is systematically stored and modeled in tabular format.

6. Intuitive Organization: The spreadsheet format is intuitive but intuitive to data modeling in relational databases.

  

### OLAP vs. OLTP

  

#### Online Analytical Processing (OLAP):

  

Databases optimized for these workloads allow for complex analytical and ad hoc queries. These type of databases are optimized for reads.

  

#### Online Transactional Processing (OLTP):

  

Databases optimized for these workloads allow for less complex queries in large volume. The types of queries for these databases are read, insert, update, and delete.

  

The key to remember the difference between OLAP and OLTP is analytics (A) vs transactions (T). If you want to get a price of a shoe then you are using OLTP (this has very little or no aggregations). If you want to know the total stock of shoes a particular store sold, then this requires using OLAP (since, this will require aggregations).

  

\*\*Normalization\*\*: to reduce data redundancy and increase data integrity

\*\*Denormalization\*\*: must be done for read heavy workloads to increase performance

  

### Objectives of Normal Form:

  

1. To free the database from unwanted insertions, updates, & deletion dependencies

2. To reduce the need for refactoring the database as new types of data are introduced

3. To make the relational model more informative to users

4. To make the database neutral to the query statistics

  

### Normal Forms

  

#### How to reach First Normal Form (1NF):

  

1. Atomic values: each cell contains unique and single values

2. Be able to add data without altering tables (adding or removing columns)

3. Separate different relations into different tables

4. Keep relationships between tables together with foreign keys

  

#### Second Normal Form (2NF):

  

1. Have reached 1NF

2. All columns in the table must rely on the Primary Key

  

#### Third Normal Form (3NF):

  

1. Must be in 2nd Normal Form

2. No transitive dependencies

3. Remember, transitive dependencies you are trying to maintain is that to get from A-\\> C, you want to avoid going through B.

 When to use 3NF

 When you want to update data, we want to be able to do in just 1 place. We want to avoid updating the table in the Customers Detail table (in the example in the lecture slide).

  

### Denormalization

  

The process of trying to improve the read performance of a database t the expense of losing some write performance by adding redundant copies of data

  

JOINS on the database allow for outstanding flexibility but are extremely slow. If you are dealing with heavy reads on your database, you may want to think about denormalizing your tables. You get your data into normalized form, and then you proceed with denormalization. So, denormalization comes after normalization.

  

Normalization is about trying to increase data integrity by reducing the number of copies of the data. Data that needs to be added or updated will be done in as few places as possible.

  

Denormalization is trying to increase performance by reducing the number of joins between tables (as joins can be slow). Data integrity will take a bit of a potential hit, as there will be more copies of the data (to reduce JOINS).

  

  

Fact tables: measurements, metrics or facts of a business process

Dimension: a structure that categorizes facts and measures in order to enable users to answer business questions. Dimensions are people, products, places and time

  

### Data Mart Schemas:

  

1. Star schema

2. Snowflake schema

  

#### Star schema

  

One or more fact tables referencing any number of dimension tables

Benefits:

  

1. Denormalized

2. Simplified queries

3. Fast aggregations

 Drawabacks

4. Issues that come with denormalization

5. Data integrity

6. Decrease query flexibility

7. Many-to-many relationships

  

#### Snowflake schema

  

Centralized fact tables connected to multiple dimensions

Star schema is a simplified version of a snowflake schema

  

  

## Data Modeling for NoSQL Databases

  

### When Not to Use SQL:

  

\- Need high Availability in the data: Indicates the system is always up and there is no downtime

\- Have Large Amounts of Data

\- Need Linear Scalability: The need to add more nodes to the system so performance will increase linearly

\- Low Latency: Shorter delay before the data is transferred once the instruction for the transfer has been received.

\- Need fast reads and write

  

\[Different types of NoSQL databases\](https://www.xenonstack.com/blog/overview-types-nosql-databases/ "different types of NoSQL databases")

  

NoSQL = not only SQL

  

### Distributed Databases

  

\- Distributed database - sitting in many servers

\- In distributed databases you need many copies of your data to provide high availability

\- High availability - no downtime (full system, not each node)

  

#### Eventual consistency

  

Over time (if no new changes are made) each copy of the data will be the same, but if there are new changes, the data may be different in different locations. The data may be inconsistent for only milliseconds. There are workarounds in place to prevent getting stale data.

  

#### CAP Theorem:

  

Pick two:

  

1. Consistency: Every read from the database gets the latest (and correct) piece of data or an error

2. Availability: Every request is received and a response is given -- without a guarantee that the data is the latest update

3. Partition Tolerance: The system continues to work regardless of losing network connectivity between nodes

  

You can only have Consistency and Availability or Availability and Partition. Remember, relational and non-relational databases do different things, and that's why most companies have both types of database systems.

Cassandra - AP

  

### Data modeling in Apache Cassandra

  

#### Denormalization

  

\- Denormalization is not just okay - it's a must

\- Denormalization must be done for fast reads

\- Apache Cassandra has been optimized for fast writes

\- Think about Queries first

\- One table per query is a great strategy

\- Apache Cassandra doesn’t allow for JOINs between tables

  

\*\*CQL\*\* Cassandra Query Language - way of interacting with database

  

\- No JOINs

\- No GROUP BY

\- No subquerries

  

#### Primary Key

  

PK is how each row is identified and how data is distributed across the nodes in the system 

  

\- Must be unique

\- The PRIMARY KEY is made up of either just the PARTITION KEY or with the addition of CLUSTERING COLUMNS

\- A simple PRIMARY KEY is just one column that is also the PARTITION KEY. A Composite PRIMARY KEY is made up of more than one column and will assist in creating a unique value and in your retrieval queries

\- The PARTITION KEY will determine the distribution of data across the system (define it to ensure even distribution)

\- The PARTITION KEY will be hashed and stored on the node in the system

  

#### Clustering Columns:

  

\- The cluster column will sort the data in sorted ascending order, e.g., alphabetical order. Note: this is a mistake in the video, which says descending order.

\- More than one clustering column can be added (or none!)

\- From there the clustering columns will sort in order of how they were added to the primary key

 You can use as many clustering columns. You cannot use the clustering columns out of order in the SELECT statement. You may choose to omit using a clustering column in your SELECT statement. That's OK. Just remember to use them in order when you are using the SELECT statement.

  

#### \`WHERE\` clause

  

\- Data Modeling in Apache Cassandra is query focused, and that focus needs to be on the \`WHERE\` clause

\- Failure to include a \`WHERE\` clause will result in an error

\- The PARTITION KEY must be included in your query

  

  

  

## SQL Cheatsheet

  

### Basic \`SELECT\` statement

  

\`\`\`sql

SELECT column\_1, column\_2

FROM table\_1;

\`\`\`

  

##### Commenting code

  

\`\`\`sql

SELECT 

column\_name\_1, \--single\_line\_comment

 column\_name\_2, 

 \--column\_name\_3, 

column\_name\_4 

/\* comment\_line\_1

comment\_line\_2

\*/

FROM table\_name\_1

;

\`\`\`

  

##### Cleaner notation

  

\`\`\`sql 

SELECT 

column\_1, 

column\_2

FROM table\_1

;

\`\`\`

  

\`\`\`sql

\--Column alias

SELECT 

column\_1 AS t1c1, 

column\_2 AS t1c2

FROM 

table\_1

;

\`\`\`

  

##### Table prequalifying

  

\`\`\`sql

SELECT 

t1.column\_1, 

t1.column\_2

FROM 

table\_1 t1

;

\`\`\`

  

##### Selecting all columns

  

\`\`\`sql

SELECT \*

FROM table\_1

;

\`\`\`

  

##### Limiting results

  

\`\`\`sql

SELECT \*

FROM table\_1

LIMIT 10

;

\`\`\`

  

  

### Creating tables

  

\`\`\`sql

CREATE TABLE table\_1

(

column\_1 char(10) PRIMARY KEY,

column\_2 char(250) NULL,

column\_3 decimal(8, 2) NOT NULL

)

;

\`\`\`

  

Temporary tables

  

\`\`\`sql

CREATE TEMPORARY TABLE AS

(

SELECT \*

FROM table\_1

)

;

\`\`\`

  

### Views

  

View is a stored query

  

\`\`\`sql

CREATE \[TEMP\] VIEW \[IF NOT EXISTS\] view\_1 AS

SELECT \*

FROM table\_1

;

\`\`\`

  

  

  

### Update table

  

### Delete table

  

\`\`\`sql

DROP TABLE 

table\_1

;

\`\`\`

  

  

### Inserting data

  

\`\`\`sql

INSERT INTO table\_1

VALUES

(

value\_1,

value\_2,

value\_3

)

;

\`\`\`

  

\`\`\`sql

INSERT INTO 

table\_name\_1

(

column\_1,

column\_2,

column\_3

) 

VALUES

(

value\_1,

value\_2,

value\_3

)

;

\`\`\`

  

  

## Mathematical operations

  

### Basic operations

  

Math operators in SQL

  

\- \`+\` - addition

\- \`-\` - subtraction

\- \`\*\` - multiplication

\- \`/\` - division

  

\`\`\`sql

SELECT column\_1 \* column\_2 AS new\_column\_1

FROM table\_1

;

\`\`\`

  

### Aggregate functions

  

Aggregate functions in SQL

  

\- \`SUM()\`

\- \`COUNT()\`

\- \`AVG()\` - NULLs will be ignored

\- \`MIN()\`

\- \`MAX()\`

  

\`\`\`sql

SELECT AVG(column\_1) AS average\_column\_1

FROM table\_1

;

\`\`\`

  

\`\`\`sql

SELECT COUNT(\*) AS total\_rows \--counts NULLs as well

FROM table\_1

;

\`\`\`

  

\`DISTINCT\` clause

  

\`\`\`sql

SELECT COUNT(DISTINCT column\_1) AS unique\_column\_1

FROM table\_1

;

\`\`\`

  

## Filtering data

  

Operators:

  

\- \`=\` - Equal

\- \`<>\` - Not equal (sometimes \`!=\`)

\- \`>\` - Greater than

\- \`>=\` - Greater than or equal

\- \`<\` - Less than

\- \`<=\` - Less than or equal

\- \`BETWEEN\` - Between an inclusive range

\- \`IS NULL\` - Is a null value

  

### \`WHERE\` clause

  

\`\`\`sql

SELECT \*

FROM table\_1

WHERE column\_1 = 3

;

\`\`\`

  

\`\`\`sql

SELECT \*

FROM table\_1

WHERE column\_1 IN (1, 5, 9)

;

\`\`\`

  

Faster than \`OR\`

Can contain another \`SELECT\` statement

  

\`\`\`sql

SELECT \*

FROM table\_1

WHERE column\_1 BETWEEN 6 AND 16

;

\`\`\`

  

\`\`\`sql

SELECT \*

FROM table\_1

WHERE column\_1 'a' OR 'b'

;

\`\`\`

  

\`\`\`sql

SELECT \*

FROM table\_1

WHERE 

(column\_1 'a' OR 'b')

AND column\_2 = 3

;

\`\`\`

  

\`\`\`sql

SELECT \*

FROM table\_1

WHERE NOT column\_1 = 12

;

\`\`\`

  

\`\`\`sql

SELECT \*

FROM table\_1

WHERE column\_1 IS NULL

;

\`\`\`

  

### Wildcards

  

\- \`'%thing'\` - finds anything ending with ‘thing’

\- \`'thing%'\` - finds anything starting with 'thing'

\- \`'%thing%'\` - finds anything with 'thing' inside the text

\- \`'t%g'\` - finds anything starting with ’t’ and ending with ‘g’

\- \`'\_'\` - any single character (vs. \`%\` - any number of characters)

\- \`'\[acb\]'\` - single character - ‘a’, ‘b’ or ‘c’

  

  

\`\`\`sql

SELECT \*

FROM Table\_name\_1

WHERE column\_name\_1 LIKE 'd\_\_a'

;

\`\`\`

  

### Ordering data

  

\`\`\`sql

SELECT \*

FROM table\_1

ORDER BY column\_1, column\_2 \--ORDER BY should be the last clause

;

\`\`\`

  

\`\`\`sql

SELECT \*

FROM table\_1

ORDER BY 2, 3 \--sort by column position

;

\`\`\`

  

\`\`\`sql

SELECT column\_1, column\_2

FROM table\_1

ORDER BY column\_3 \--can order by columns not selected

;

\`\`\`

  

\`\`\`sql

SELECT \*

FROM table\_1

ORDER BY 

column\_1 ASC, 

column\_2 DESC \--ASCENDING is default option

;

\`\`\`

  

## Grouping data

  

### \`GROUP BY\`

  

NULLs will be grouped together

  

\`\`\`sql

SELECT column\_1, SUM(column\_2)

FROM table\_1

GROUP BY column\_1

;

\`\`\`

  

\`\`\`sql

SELECT column\_1, SUM(column\_2), column\_3

FROM table\_1

GROUP BY column\_1, column\_3

;

\`\`\`

  

Every column in \`SELECT\` statement must be present in \`GROUP BY\` clause, except for aggregated calculations

  

### filtering using \`HAVING\` clause

  

\`WHERE\` doesn’t work on grouped data, it works on rows only

Rows eliminated by \`WHERE\` will not be used for grouping 

  

\`\`\`sql

SELECT COUNT(column\_1), column\_2

FROM table\_1

GROUP BY column\_2

HAVING COUNT(column\_1) > 5

;

\`\`\`

  

## Combining data from different places

  

### Subqueries

  

\`\`\`sql

SELECT column\_1, column\_2

FROM table\_1

WHERE column\_1 IN (SELECT column\_1

FROM table\_2

WHERE column\_3 > 19

)

;

\`\`\`

  

subquery \`SELECT\` gets only single column - good for filtering

  

Subqueries as calculations 

  

\`\`\`sql

SELECT 

column\_1, 

column\_2,

(

SELECT COUNT(\*) AS column\_3

FROM table\_2

WHERE table\_2.column\_4 = table\_1.column\_4) AS column\_3

FROM 

table\_1

;

\`\`\`

  

### \`JOIN\` clauses

  

\*\*Cartesian (Cross) Join\*\* - each record from 1st table combined with every record in the 2nd table

  

\`\`\`sql

SELECT table\_1.column\_1, table\_2.column\_2, table\_2.column\_3

FROM table\_1 CROSS JOIN table\_2

;

\`\`\`

  

\*\*Inner join\*\* - select record that have matching values in both tables

  

\`\`\`sql

SELECT table\_1.column\_1, table\_2.column\_2, table2.column\_3

FROM table\_1 INNER JOIN table\_2

ON table\_1.column\_4 = table\_2.column\_4

;

\`\`\`

  

\*\*Self join\*\* - a join of two copies of the same table

  

\`\`\`sql

SELECT a.column\_1, 

 b.column\_2,

 a.column\_3

FROM table\_1 AS a, table\_1 AS b

WHERE a.column\_4 = b.column\_4

;

\`\`\`

  

\*\*Left join\*\* - returns all records from 1st table (left) with matched records from 2nd table (right)

  

\`\`\`sql

SELECT table\_1.column\_1, table\_2.column\_2

FROM table\_1

LEFT JOIN table\_2 ON table\_1.column\_3 = table\_2.column\_3

;

\`\`\`

  

\*\*Right join\*\* - returns all records from 2nd table (right) with matched records from 1st table (left). 

  

\`\`\`sql

SELECT table\_1.column\_1, table\_2.column\_2

FROM table\_1

RIGHT JOIN table\_2 ON table\_1.column\_3 = table\_2.column\_3

;

\`\`\`

  

\*\*Full outer join\*\* - returns all records when there is a match in either table.

  

\`\`\`sql

SELECT table\_1.column\_1, table\_2.column\_2

FROM table\_1

FULL OUTER JOIN table\_2 ON table\_1.column\_3 = table\_2.column\_3

;

\`\`\`

  

\*\*Unions\*\* - combines results of two or more \`SELECT\` statements.

Each \`SELECT\` statement must:

  

\- have the same number of columns

\- have similar data types

\- have columns in the same order

  

\`\`\`sql

SELECT column\_1, column\_2

FROM table\_1

  

UNION

  

SELECT column\_3, column\_4

FROM table\_2

;

\`\`\`

  

## Text functions

  

### Concatenate

  

\`\`\`sql

SELECT column\_1 || column\_2 || ' dupa'

FROM table\_1

;

\`\`\`

  

\`+\` instead of \`||\` in SQL Server

  

### Trim

  

\`\`\`sql

SELECT TRIM(" Some randon text with too many spaces. ")

FROM table\_1

;

\`\`\`

  

\`\`\`sql

SELECT LTRIM(" Some randon text with too many spaces.")

FROM table\_1

;

\`\`\`

  

\`\`\`sql

SELECT RTRIM("Some randon text with too many spaces. ")

FROM table\_1

;

\`\`\`

  

### Substring

  

\`\`\`sql

SELECT SUBSTR

(string, 

3, \--starting character

4 \--number\_of\_characters

)

FROM table\_1

;

\`\`\`

  

### Capital letters

  

\`\`\`sql

SELECT UPPER(column\_1)

FROM table\_1

;

\`\`\`

  

\`\`\`sql

SELECT LOWER(column\_1)

FROM table\_1

;

\`\`\`

  

\`\`\`sql

SELECT UCASE(column\_1)

FROM table\_1

;

\`\`\`

  

  

### Date & Time Strings

  

\`\`\`sql

SELECT

birth\_date,

STRFTIME('%Y', birth\_date) AS year,

STRFTIME('%m', birth\_date) AS month,

STRFTIME('%d', birth\_date) AS day

FROM table\_1

;

\`\`\`

  

\`\`\`sql

SELECT DATE('now')

\`\`\`

  

\`\`\`sql

SELECT STRFTIME('%Y %m %d', 'now')

\`\`\`

  

### \`CASE\` statements

  

can be used in \`SELECT\`, \`INSERT\`, \`UPDATE\`, \`DELETE\` statements

  

\`\`\`sql

SELECT column\_1, column\_2,

  

CASE column\_3

WHEN value\_1 THEN output\_1

WHEN value\_2 THEN output\_2

ELSE output\_else

END new\_column

  

FROM table\_1

;

\`\`\`

  

\`\`\`sql

SELECT column\_1, column\_2,

  

CASE 

WHEN column\_3 > value\_1 THEN output\_1

WHEN column\_3 > value\_2 THEN output\_2

ELSE output\_else

END new\_column

  

FROM table\_1

;

\`\`\`

  

  

  

  

  

  

  

  

  

## SQL using Python

  

### PostgreSQL in Python

  

Import PostreSQL wrapper for Python

  

\`\`\`python

import psycogp2

\`\`\`

  

Create a connection to the database

  

\`\`\`python

conn = psycopg2.connect("host=127.0.0.1 dbname=studentdb user=student password=student")

\`\`\`

  

Use the connection to get a cursor that can be used to execute queries.

  

\`\`\`python

cur = conn.cursor()

\`\`\`

  

Set automatic commit to be true so that each action is committed without having to call conn.commit() after each command.

  

\`\`\`python

conn.set\_session(autocommit=True)

\`\`\`

  

Run a query

  

\`\`\`python

cur.execute("SELECT \* FROM Table\_1;")

\`\`\`

  

Printing rows after \`SELECT\` statement

  

\`\`\`python

row = cur.fetchone()

while row:

 print(row)

 row = cur.fetchone()

\`\`\`

  

Close cursor and connection

  

\`\`\`python

cur.close()

conn.close()

\`\`\`

  

### Examples

  

Create a database to do the work in

  

\`\`\`python

cur.execute("CREATE DATABASE bd\_name;")

\`\`\`

  

Create a table in the database

  

\`\`\`python

cur.execute("""

CREATE TABLE IF NOT EXISTS TableName 

(column\_1 data\_type\_1, 

column\_2 data\_type\_2)

;

""")

\`\`\`

  

Inserting rows in the table

  

\`\`\`python

cur.execute("INSERT INTO TableName (column\_1, column\_2) \\

 VALUES (%s, %s)", \\

 (value\_1, value\_2))

\`\`\`

  

\`SELECT\` statement

  

\`\`\`python

cur.execute("SELECT \* FROM Table\_1;")

\`\`\`

  

Deleting a table

  

\`\`\`python

cur.execute("DROP TABLE Table\_1;")

\`\`\`

  

### Data Definition and Constraints

  

The \`CREATE\` statement in SQL has a few important constraints that are highlighted below.

  

\`NOT NULL\`

The \`NOT NULL\` constraint indicates that the column cannot contain a null value.

  

\`\`\`sql

CREATE TABLE IF NOT EXISTS customer\_transactions (

 customer\_id int NOT NULL, 

 store\_id int, 

 spent numeric

);

\`\`\`

  

You can add \`NOT NULL\` constraints to more than one column. Usually this occurs when you have a \`COMPOSITE KEY\`, which will be discussed further below.

Here is the syntax for it:

  

\`\`\`sql

CREATE TABLE IF NOT EXISTS customer\_transactions (

 customer\_id int NOT NULL, 

 store\_id int NOT NULL, 

 spent numeric

);

\`\`\`

  

  

`UNIQUE`
The `UNIQUE` constraint is used to specify that the data across all the rows in one column are unique within the table. The `UNIQUE` constraint can also be used for multiple columns, so that the combination of the values across those columns will be unique within the table. In this latter case, the values within 1 column do not need to be unique. 

  

```sql
CREATE TABLE IF NOT EXISTS customer\_transactions (
	customer\_id int NOT NULL UNIQUE, 
	store\_id int NOT NULL UNIQUE, 
	spent numeric 
);
```

  

Another way to write a \`UNIQUE\` constraint is to add a table constraint using commas to separate the columns.

``` sql
CREATE TABLE IF NOT EXISTS customer\_transactions (
	customer\_id int NOT NULL, 
	store\_id int NOT NULL, 
	spent numeric,
	UNIQUE (customer\_id, store\_id, spent)
);

```


`PRIMARY KEY`
The `PRIMARY KEY` constraint is defined on a single column, and every table should contain a primary key. The values in this column uniquely identify the rows in the table. If a group of columns are defined as a primary key, they are called a composite key. That means the combination of values in these columns will uniquely identify the rows in the table. By default, the `PRIMARY KEY` constraint has the unique and not null constraint built into it.

```sql
CREATE TABLE IF NOT EXISTS store (
	store\_id int PRIMARY KEY, 
	store\_location\_city text,
	store\_location\_state text
);
```

  

``` sql
CREATE TABLE IF NOT EXISTS customer\_transactions (
	customer\_id int, 
	store\_id int, 
	spent numeric,
	PRIMARY KEY (customer\_id, store\_id)
);
```

  

  

  

  

  

## Apache Cassandra in Python

Import Apache Cassandra wrapper for Python
``` python
import cassandra
```

Create a connection to the database
``` python
from cassandra.cluster import Cluster

cluster = Cluster(\['127.0.0.1'\]) #If you have a locally installed Apache Cassandra instance
session = cluster.connect()
```

Running a query
``` python
session.execute("""SELECT \* FROM my\_keyspace""")
```

Create a keyspace
``` python
session.execute("""
	CREATE KEYSPACE IF NOT EXISTS my\_keyspace 
	WITH REPLICATION = 
	{ 'class' : 'SimpleStrategy', 'replication\_factor' : 1 }
	"""
```

Connect to the keyspace
``` python
session.set\_keyspace('my\_keyspace')
```

Create a table to be able to run the following query: `SELECT * FROM songs WHERE year=1970 AND artist\_name="The Beatles"\`
```python
query = "CREATE TABLE IF NOT EXISTS songs "
query = query + """
	(song\_title text, 
	artist\_name text, 
	year int, 
	album\_name text, 
	single boolean, 
	PRIMARY KEY (year, artist\_name))
	"""

session.execute(query)
```

query = `"CREATE TABLE IF NOT EXISTS songs "`

``` python
query = query + """
	(column\_name\_1 text,
	column\_name\_2 text,
	column\_name\_3 text,
	column\_name\_4 text,
	PRIMARY KEY ((partitioning\_column), clustering\_column\_1, clustering\_column\_2))
	"""

session.execute(query)
```

```python
query = "INSERT INTO songs (song_title, artist_name, year, album_name, single)" 
query = query + " VALUES (%s, %s, %s, %s, %s)"
session.execute(query, ("Across The Universe", "The Beatles", 1970, "Let It Be", False))
```

```python
query = 'SELECT * FROM songs'
rows = session.execute(query)
for row in rows:
	print (row.year, row.album_name, row.artist_name)
```

Dropping a table
``` python
query = "drop table my_table"
rows = session.execute(query)
```

close the session and cluster connection
``` python
session.shutdown()
cluster.shutdown()
```