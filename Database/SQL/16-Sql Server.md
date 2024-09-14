![[Untitled 15.png]]
بنقول علي الsql server  و oracle انهم Fully RDBMS
يعني هما محققين كل الservices بتاعت الداتابيز علشان كده اسمهم fully

مثلا access مفيهوش backup وخواص تاني ف كده يعتبر not fully

-----
في الsql server عندنا كلمتين edition و version
كل كام سنه مايكروسوفت بتنزل version جديده (التول جديده) زي sql server 2012 , 2008 وهكذا 
لاكن الedition هي نسخ مختلفه من نفس الversion حسب الاستخدام (فيتشرز مقابل فلوس)

----
لما بنسطب الsql server عالجهاز بنسطب حاجه اسمها instance مش service
الinstance بيكون تحتها services and applications
بختار منهم الي بحتاجه وانا بسطب او اسيبه يحمل الديفولت بتوعهم 

عندنا 5 services بينزلو ديفولت 
1-DB Engine SQLServer (MSSQLServer)
2-Sql server integration service (SSIS)
3-Sql server reporting service (SSRS)
4-Sql server analysis service (SSAS)
5-Data quality service
دول ال5 الي بينزلو 
بنحتاج ابلكيشنز تنزل علشان ت interact مع الservices دي
عندنا 5 ابلكيشنز 
1-Sql server management studio (SSMS)
بيتعامل مع الDB Engine service
2-Sql server data tools 
بيتعامل مع الservices بتاعت ال business intelligence (BI) الي هما SSIS , SSRS , SSAS
3-Data quality client
بنشتغل بيها عالداتا ونشوف بتماتش حاجه معينه ولا لا , وبنشيل بيها الدابلكيشن
ولو فيه داتا مكتوبه غلط بنصلحها

4-Sql server profiler
5-Sql server tuning advisor
اخر اتنين خاصيين بالperformance 

![[Pasted image 20240914150439.png]]

لما بنسطب الsql server بينزل معاه ال10 حاجات دول

لو سطبناه تاني مش بينزل معاه الابلكيشنز لانهم Shared ما بين اكتر من instance بنسطبه
لاكن لو سطبناه تاني ممكن تنزل معانا Service جديده

***What is an Instance?***
An **instance** is a separate installation of the SQL Server database engine. Each instance operates independently and has its own databases, settings, and configuration. So when you install multiple instances, it’s like having multiple SQL Servers running on your laptop.

 **Each Instance Acts Like a Server**
- Each instance listens on its own ports.
- Each instance manages its own memory, CPU, and storage.
- You can configure each instance separately (e.g., security settings, version, recovery models).

ليه ممكن اسطب اكتر من DB Engine علي نفس الجهاز؟؟

ينفع اسطب اكتر من واحده عالجهاز ولو سطبنا مثلا اتنين يبقا عندنا سيرفرين عالجهاز 
ممكن اكون محتاج اكتر من instance علشان احط كونفجريشن معينه لكل واحد او سكيورتي مختلفه 

او احدد resource requirement مختلفه لكل واحد

مثلا عندي 10 داتابيز وعندي مليون يوزر
الinstance بتاعتي هتشتغل علي جزء معين من الرامات وبروسيسور معين (core معينه) 
لو انا عايز اوزع الحمل ده علي اجزاء تاني ف هعمل instance تانيه احط عليها داتابيز تانيه علشان اوزع الحمل علي اكتر من جزء من الرام والبروسيسور

لسبب تاني ممكن اعمل replication هخلي نسخه عالسيرفر الاصلي ونسخه علي سيرفر تاني علشان لو فيه سيرفر وقع التاني هيقوم

كل instance هحملها تعتبر سيرفر مختلف


لما بسطب اكتر من instance 
الديفولت بتاعتي بتكون باسم MSSQLSERVER وبقدر اناديها ب . او local او الip او pc_name
دي بيكون اسمها الdefault instance

لاكن لو هسطب واحده تاني او اكتر كده هيكون اسمها named instance مش هينفع اناديها زي الdefault ف هحطلها اسم
ولنفترض myInstance
يبقا هناديها 
./myInstance  , local/myInstance , pc_name/myInstace , ip/myInstace


**Default vs Named Instances**
- **Default Instance**: This is the main SQL Server instance that you install. You can connect to it using just the computer name (e.g., `localhost` or `your_computer_name`).
    
- **Named Instances**: These are additional instances you can install on the same machine. They require a unique name and you connect to them using `computer_name\instance_name`.




----
authentication 
دي بحدد انت صاحب الحساب ولا لا (انت الي بتدعي انه انت ولا لا) 
كده محتاج username + pa