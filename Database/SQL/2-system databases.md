لما بنفتح الsql server 
هنلاقي انه فيه فولدر لداتابيز موجوده قبل كده 
هما system databases 
متحملين قبل كده مع ال rdbms

- master database 
	records all the system-level information for an instance of SQL Server
	هي داتابيز السيرفر بيخزن فيها كل المعلومات اللازمه لاداره الmicrosoft sql server
	فيها كل المعلومات الضرورية لادارة كل الداتابيز الي هنحطها علي السيرفر
	هيكون فيها معلومات زي اسماء الداتابيز كلها الي عملناها علي السيرفر ده , login information 
	كل الداتابيز الملفات بتاعتهم مخزنين فين ....
- msdb database 
	used b sql server agent for scheduling alerts and jobs 
	ال ms sql server
	بيحتاج انه ينفذ بعض الjobs
	مثلا باكاب او اي وظائف بتتكرر بشكل دوري علي فترات زمنية محددة 
	كل المعلومات والتوقيتات هتكون فالداتبيز دي
- model database
	Is used as the template for all databases created on the instance of SQL Server.
	Modifications made to the model database, such as database size. collation ,recovery
	model and other database options. are applied to any databases created afterward.
	هتكون زي تيمبلت للداتابيز الي بعملها 
	بتاخد منها الديفولت بروبيرتس 
	مثلا لو المودل ده بيكون مساحته 100 ميجا
	ف اي داتابيز هعملها هتاخد نفس المساحه 
- tempdb database
	is a workspace for holding temporary objects or intermediate result sets. في اثناء الشغل محتاجين جداول موقته نشيل فيها بيانات موقتا 
	ف ده بيكون مكانها 

نقدر نعمل عليهم اي queries 
لاكن منقدرش نعدل علي بياناتهم 
