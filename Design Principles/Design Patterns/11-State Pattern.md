**State** is a behavioral design pattern that lets an object alter its behavior when its internal state changes. It appears as if the object changed its class.

هو behavioral pattern
بيسمح للاوبجكت انه يغير الbehavior بتاعه لما الState بتاعته بتتغير 
مثلا زي اشارة المرور 
لما بتكون في state معينه يبقا ليها behavior معين وهكذا

بدلا من الحاجه للconditional logic بستخدم الstate pattern
يعني بدلا ما استخدم if else واقول لو الcurrent state بكذا يبقا ال state الجديده بكذا

![[Pasted image 20250108225134.png]]

هستخدم الstate pattern بدلا من الحاجه للcondiaional logic هنا
يعني مش منطقي اني اعمل if current state = A then next is B 
و if else current state = B then next is E 
لان كده الكود هيكبر مني وهيخالف مبدا OCP 

بدلا من كده هيكون عندي لكل state كلاس مختلف بيعبر عنه 

الpattern بيتكون من 3 حاجات 
الاول هو الcontext class وده هيكون فيه ريفرنس بيتصرف كانه ال current state 
والتاني هو ال state interface بيكون فيها الميثودز الي بياخدها كل الstates ويعملولها override 
التالت هو ال state classes وهو الامبلمنتيشن بتاع كل state 

![[Pasted image 20250108225915.png]]
الكونتكست هيكون هو الكلاس الي بmanage الstates 
وهيشيل جواه ريفرنس من الstate عباره عن ال current state 

وهيكون فيه changeState method نقدر نديلها state جديده وهي تعملها set فالريفرنس بتاعنا وتكون هي الnew current 


###### Applicability

Use the State pattern when you have an object that behaves differently depending on its current state, the number of states is enormous, and the state-specific code changes frequently.

The pattern suggests that you extract all state-specific code into a set of distinct classes. As a result, you can add new states or change existing ones independently of each other, reducing the maintenance cost.

Use the pattern when you have a class polluted with massive conditionals that alter how the class behaves according to the current values of the class’s fields.

The State pattern lets you extract branches of these conditionals into methods of corresponding state classes. While doing so, you can also clean temporary fields and helper methods involved in state-specific code out of your main class.

Use State when you have a lot of duplicate code across similar states and transitions of a condition-based state machine.

The State pattern lets you compose hierarchies of state classes and reduce duplication by extracting common code into abstract base classes.

----
###### How to Implement

1. Decide what class will act as the context. It could be an existing class which already has the state-dependent code; or a new class, if the state-specific code is distributed across multiple classes.
    
2. Declare the state interface. Although it may mirror all the methods declared in the context, aim only for those that may contain state-specific behavior.
    
3. For every actual state, create a class that derives from the state interface. Then go over the methods of the context and extract all code related to that state into your newly created class.
    
    While moving the code to the state class, you might discover that it depends on private members of the context. There are several workarounds:
    
    - Make these fields or methods public.
    - Turn the behavior you’re extracting into a public method in the context and call it from the state class. This way is ugly but quick, and you can always fix it later.
    - Nest the state classes into the context class, but only if your programming language supports nesting classes.
4. In the context class, add a reference field of the state interface type and a public setter that allows overriding the value of that field.
    
5. Go over the method of the context again and replace empty state conditionals with calls to corresponding methods of the state object.
    
6. To switch the state of the context, create an instance of one of the state classes and pass it to the context. You can do this within the context itself, or in various states, or in the client. Wherever this is done, the class becomes dependent on the concrete state class that it instantiates.


----

###### Pros and Cons
pros:
- _Single Responsibility Principle_. Organize the code related to particular states into separate classes.
- _Open/Closed Principle_. Introduce new states without changing existing state classes or the context.
- Simplify the code of the context by eliminating bulky state machine conditionals.

cons:
- Applying the pattern can be overkill if a state machine has only a few states or rarely changes.