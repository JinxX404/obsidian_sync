![[Pasted image 20240623202409.png]]
There are so many benefits of using OOD but every developer should also know the SOLID principle for good object-oriented design in programming. The SOLID principle was introduced by Robert C. Martin, also known as Uncle Bob and it is a coding standard in programming. This principle is an acronym of the five principles which are given below:

- Single Responsibility Principle (SRP)
- Open/Closed Principle
- Liskov’s Substitution Principle (LSP)
- Interface Segregation Principle (ISP)
- Dependency Inversion Principle (DIP)
each letter in 'solid' represent one principle


The SOLID principle **helps in reducing tight coupling**. Tight coupling means a group of classes are highly dependent on one another which you should avoid in your code.

- Opposite of tight coupling is loose coupling and your code is considered as a good code when it has loosely-coupled classes.
- Loosely coupled classes minimize changes in your code, helps in making code more reusable, maintainable, flexible and stable.

الtight coupling يعني عندنا اكتر من كلاس معتمدين علي بعض 
يعني فيه dependencies كتيره
يعني اي تعديل فاي كلاس هينتج عنه تعديلات فكلاسات تاني
وده مش عايزينه 
بنحاول نحقق ال loosely coupled يعني هنقلل الاعتماديه ما بين الكلاسات علشان التعديل فواحد منهم مياثرش فواحد تاني
والsolid principles بتساعدنا نعمل كده