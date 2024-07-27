**Database**: A structured collection of data. It can store various types of data like text, numbers, images, etc.
هو مكان بنخزن فيه داتا 

---
**DBMS (Database Management System)**: Software that manages databases. It provides functionalities for storing, retrieving, and managing data. It ensures data integrity, security, and performance.
هو سوفتوير بيساعدنا نتحكم فالداتا دي وازاي نخزنها ونرجعها 

من انواعه RDBMS , NoSQL 
- **RDBMS (Relational Database Management System)**: Manages data in tables with rows and columns. It supports SQL for querying and manipulating data. Examples include SQL Server, MySQL, PostgreSQL, and Oracle Database.
-النوع ده بيخزن الداتا ك table وبيكون ما بينهم علاقات 
ومن ضمن الDBMS الي بتشتغل بالنوع ده هو Sql server , mysql
	- **SQL Server**: A specific RDBMS developed by Microsoft. It uses SQL for interacting with the data and provides a robust environment for database management.
	- **MySQL**: Another popular RDBMS, known for being open-source and widely used in web applications.


- **NoSQL (Non-relational Database Management System)**: Manages data that might not fit well into tables. It can store unstructured or semi-structured data and often supports more flexible data models like key-value pairs, documents, or graphs. Examples include MongoDB, Cassandra, and Redis.
-النوع ده بيخزن الداتا باشكال تاني غير الrelational ومن انواع الDBMS هي MongoDB .....

---

**SQL (Structured Query Language)**: A standardized language used to interact with relational databases (RDBMS). It allows you to perform tasks like querying data, updating records, and managing database schemas.
هي اللغه الي بنحتاجها علشان نتواصل مع ال RDBMS ونطلب منه تاسكات معينه علي الداتا

---



---

**SSMS (SQL Server Management Studio)**: A graphical user interface (GUI) tool provided by Microsoft for managing SQL Server databases. It offers a user-friendly way to interact with SQL Server, run SQL queries, design databases, and perform administrative tasks.
هي توول من مايكروسوفت بتساعدنا نتحكم فالsql server 

----
 عندنا في الRDBMS بنستخدم SQL علشان نعمل queries عالداتا 
 لاكن الوضع في ال NoSQL مختلف
 
 NoSQL databases don't use SQL as their query language because they are designed to handle different types of data models that aren't necessarily relational. Instead, each type of NoSQL database typically has its own query language or API. Here are some examples of popular NoSQL databases and the query languages or methods they use to interact with data:

### 1. **Document Databases**
   - **MongoDB**: Uses a JSON-like query language.
     - **Example**: Query to find documents in a collection:
       ```javascript
       db.collection.find({ "field": "value" })
       ```
   - **CouchDB**: Uses a RESTful HTTP API and supports querying using MapReduce or Mango Query.

### 2. **Key-Value Stores**
   - **Redis**: Uses simple commands for data operations.
     - **Example**: Set and get a value:
       ```bash
       SET key value
       GET key
       ```
   - **Riak**: Uses a RESTful HTTP API or its own protocol buffers API for data operations.

### 3. **Column-Family Stores**
   - **Cassandra**: Uses CQL (Cassandra Query Language), which is similar to SQL but designed for the database's specific needs.
     - **Example**: Query to select data from a table:
       ```sql
       SELECT * FROM table_name WHERE key = 'value';
       ```
   - **HBase**: Uses a Java API or REST for data operations.

### 4. **Graph Databases**
   - **Neo4j**: Uses Cypher, a declarative query language for graph databases.
     - **Example**: Query to find nodes and relationships:
       ```cypher
       MATCH (n:Label) WHERE n.property = 'value' RETURN n
       ```
   - **Amazon Neptune**: Supports SPARQL and Gremlin for querying graph data.

### Examples of Query Languages and Methods in NoSQL Databases

#### MongoDB (Document Database)
- **Query**: Find documents where the field "name" is "John".
  ```javascript
  db.users.find({ "name": "John" })
  ```

#### Redis (Key-Value Store)
- **Commands**: Set a value for a key and retrieve it.
  ```bash
  SET user:1 "John Doe"
  GET user:1
  ```

#### Cassandra (Column-Family Store)
- **CQL Query**: Select all columns from a table where the key is "user123".
  ```sql
  SELECT * FROM users WHERE user_id = 'user123';
  ```

#### Neo4j (Graph Database)
- **Cypher Query**: Find nodes labeled "Person" where the name is "Alice".
  ```cypher
  MATCH (p:Person {name: 'Alice'}) RETURN p
  ```

Each NoSQL database is optimized for specific types of data and use cases, so their query languages and methods are designed to best suit their architecture and data models. If you have a particular NoSQL database in mind, I can provide more detailed examples and explanations for that system!
