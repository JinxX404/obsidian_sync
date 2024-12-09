Relational Model  
هي طريقة ابستراكشن بنمثل بيها الداتا بتاعتنا 
في ال relational model عندنا الداتا متخزنه علي شكل relations(tables) 

ازاي بنخزن الrelations دي علي ال physical storage دي بتختلف من سيستم للتاني كل واحد بيعمل امبلمنتيشن بطريقه مختلفه

ال relational databases هي نوع من الداتابيز بيتبع الطريقه او المودل بتاع ال relational في انه يخزن الداتا ك جداول
من انواع ال relational databases هي mssqlserver , mysql , postgresql 

ال DBMS هو سوفتوير بيساعدنا ن interact مع اي نوع من الداتابيز 
ال RDBMS هو السوفتوير الي بيساعدنا نinteract مع الداتابيز ال relational الي هي بتتبع ال relational model 
![[Pasted image 20241209153321.png]]

ال relation هي تمثيل لاوبجكت او اينتيتي معينه وكل relation بيكون ليها attributes 

---
ال SQL مبنيه علي ال Relational Algebra ومجموعة اخري من ال theories 

ال relational algebra هي عمليات بعملها علي انبوت وبتديلي اوتبوت 
الانبوت والاوتبوت هنا هما relation or table 

**What is Relational Algebra?** 

Relational Algebra is a procedural query language. Relational algebra mainly provides a theoretical foundation for relational databases and SQL. The main purpose of using Relational Algebra is to define operators that transform one or more input relations into an output relation. Given that these operators accept relations as input and produce relations as output, they can be combined and used to express potentially complex queries that transform potentially many input relations (whose data are stored in the database) into a single output relation (the query results).

Relational algebra consists of a certain **set of rules or operations** that are widely used to manipulate and query data from a relational database. It can be facilitated by utilizing SQL language and helps users interact with database tables based on querying data from the database more efficiently and effectively.

Relational Algebra incorporates a collection of operations, such as filtering data or combining data, that help us organize and manipulate data more efficiently. This ” algebra ” is the foundation for most database queries, and it enables us to extract the required information from the databases by using SQL query language.

