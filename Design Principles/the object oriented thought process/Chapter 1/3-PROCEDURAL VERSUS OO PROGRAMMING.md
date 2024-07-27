What exactly is an object? This is both a complex and a simple question. It is complex because learning any method of software development is not trivial. It is simple because people already think in terms of objects.
الاوبجكت هي اي حاجه قدامنا ليها attributes (خواص) و methods (افعال)

For example, when you look at a person, you see the person as an object. And an object is defined by two components: attributes and behaviors. A person has attributes, such as eye color, age, height, and so on. A person also has behaviors, such as walking, talking, breathing, and so on. In its basic definition, an object is an entity that contains both data and behavior. The word both is the key difference between OO programming and other programming methodologies.
الattributes و behavior متغلفين مع بعض وبيعملو object


In procedural programming, for example, code is placed into totally distinct functions or procedures, these procedures then become “black boxes,” where inputs go in and outputs come out. Data is placed into separate structures and is manipulated by these functions or procedures.
ال procedural programming عباره عن شويه functions , data
الفانكشنز هنعتبرها black box بيدخل عليه انبوت وتطلع اوتبوت
يعني الداتا والفانكشنز مفصولين عن بعض
![[Pasted image 20240623163851.png]]


---
**Difference Between OO and Procedural In OO design, the attributes and behaviors are contained within a single object, whereas in procedural, or structured, design the attributes and behaviors are normally separated.**

---
in structured programming the data is often separated from the procedures, and often the data is global, so it is easy to modify data that is outside the scope of your code. This means that access to data is uncontrolled and unpredictable (that is, multiple functions may have access to the global data). Second, because you have no control over who has access to the data, testing and debugging are much more difficult. Objects address these problems by combining data and behavior into a nice, complete package.
فالاستراكشرد بروجرامنج الداتا مفصوله عن الفانكشنز وبتكون جلوبال
يعني اكتر من فانكشن تقدر تشتغل عليها 
يعني الاكسس عليها uncontrolled وبتصعب مهمة ال debug , test
علي عكس ال Objects بيحل المشاكل دي بانه بيدمج الداتا والفانكشنز جوه باكدج واحده 

---
**Proper Design**
	We can state that when properly designed, there is no such thing as global data in an OO model. This fact provides a high amount of data integrity in OO systems.


---
**Data Hiding**
	In OO terminology, data are referred to as attributes, and behaviors are referred to as methods. **Restricting access** to certain attributes and/or methods is called data hiding.
	لما بنحدد مين يقدر ياكسس ايه يبقا بنعمل Data hiding 
	بنطبقها بالaccess modifiers
	**who can access what**


---
**By combining the attributes and methods in the same entity, which in OO parlance is called encapsulation**
لما بنحط الميثودز والاتريبيوت فنفس "الحاجه" يبقي طبقنا ال encapsulation
نعتبر ان ال attributes , methods محطوطين جوه كبسولة مع بعض

---
**it is normally better to build small objects with specific tasks rather than build large objects that perform many.**


