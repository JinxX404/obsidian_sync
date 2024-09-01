
#### Association
The association is a “has-a” type relationship. The association establishes the relationship b/w two classes using their objects. Association relationships can be one-to-one, to-many, many-to-one, and many-to-many.

هي علاقة قصيره الاجل ما بين 2 classes واحد فيهم هيستخدم التاني وبعد ما بيخلص من الاوبجكت بيسيبه

معني ان كلاس  X هيستخدم كلاس Y 
يعني X محتاج ياخد اوبجكت من Y جواه علشان يستخدمه

الاتنين كلاس مبيكونوش عارفين اي حاجه عن بعض
وكل واحد بينشأ في وقت غير التاني
والlife cycle بتاعت كل كلاس غير معتمده علي الاخر
وكل واحد واحد يقدر يعيش غير التاني
لو الكلاس ده مات (مبقاش فالميموري) التاني مش هيتاثر بيه

العلاقه بتنشا مع ميثود فيها الكلاس الاول بيستخدم اوبجكت من الكلاس التاني
وبعد تنفيذ الميثود دي ما تخلص العلاقه ما بينهم مش هتبقي موجوده

suppose we have two classes then these two classes are said to have a “has-a” relationship if both of these entities share each other’s object for some work and at the same time they can exist without each other's dependency or both have their own lifetime.

```C#
class Employee
{
    public Employee() { }
    public string Emp_Name { get; set; }

    public void Manager_Name(Manager Obj)
    {
        Obj.manager_Info(this);
    }
}
class Manager
{
    public Manager() { }
    public string Manager_Name { get; set; }
    
    public void manager_Info(Employee Obj)
    {
        WriteLine($"Manager of Employee {Obj.Emp_Name} is {this.Manager_Name}");
    }
}
class Program
{
    static void Main(string[] args)
    {
        Manager Man_Obj = new Manager();
        Man_Obj.Manager_Name = "Dazy Aray";
        Employee Emp_Obj = new Employee();
        Emp_Obj.Emp_Name = "Ambika";
        Emp_Obj.Manager_Name(Man_Obj);
        ReadLine();
    }
}
```
كلاس manager استخدم اوبجكت من employee والعكس 
كل واحد استخدم اوبجكت التاني جوه ميثود 
وبعد الميثود ما خلصت مش هيكون بينهم اي علاقه 
ووجود واحد منهم غير مرتبط بوجود واحد تاني

both Employee and Manager classes use the object of each other and both their own independent life cycle.

 Association means that an object `"uses"` another object. "Association is a weaker form of Aggregation where the class doesn't keep a reference to the object it receives."_

#### Aggregation

Aggregation is based on a "has-a" relationship. Aggregation is a special form of association. In association, there is not any classes (entities) that work as owners but in aggregation one entity work as an owner. In aggregation, both entities meet for some work and then get separated. Aggregation is a one-way association.
هي علاقه طويله الاجل 
فيها كلاس هيحتوي علي اوبجكت من كلاس تاني
مش مجرد هيستخدمه فميثود زي الassociation 
لاكن اطول شويه 

وكل كلاس الlife cycle بتاعته مش هتكون زي التاني
مفيش بينهم اعتماديه
لو واحد فيهم مات مش هيموت التاني

الكلاس بيحتوي علي اوبجكت 
يعني هيكون عندي ريفرنس جوه الكلاس شايل الاوبجكت ده 
مش مجرد انه يكون موجود جوه ميثود واحده فقط

هيكون معانا ريفرنس نقدر نستخدمه فاكتر من اكشن 
ولما نحتاج ننهي العلاقه ما بين الاتنين كلاس بنعمل الريفرنس ده null

الكلاس الي بيستخدم الاوبجكت 
مش مسئول عن انه يعمله Create
هو مجرد بيستخدمه لاكن فيه حد بره الكلاس ده هو الي عمله create



#### Composition 
نقدر نقول ان كلاس A بيتكون من B , 
consists of
علاقه اقوي من الاستخدام والاحتواء في association , aggregation
علاقه طويله الاجل زي الaggregation  
لاكن هتفرق في الlife cycle والاعتمادية ما بين الاتنين
علاقه ممتده وفيه واحد منهم الcreate بتاعه معتمد علي التاني ومش هيقدر يعيش من غير التاني

معني ان A بيستخدم B
معناه ان A بيعمل create ل B جواه
مجالهوش الريفرنس من بره زي الAggregation
يعني كده لو A مات هيموت معاه B لانه معمول جواه 

Composition is a "part-of" relationship. Simply composition means mean use of instance variables that are references to other objects. In a composition relationship, both entities are interdependent on each other for example “engine is part of car”, and “heart is part of body”.

```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using static System.Console;
namespace Entity2
{
    class Car
    {
        public Car() { }
        public string Color { get; set; }
        public string Max_Speed { get; set; }
    }
    class Suzuki : Car
    {
        public Suzuki() { }
        public int Total_Seats { get; set; }
        public string Model_No { get; set; }
        public void CarInfo()
        {
            string Info = $"Color of car is {this.Color} \nMaximum speed is {this.Max_Speed}\nNumber of seats is {this.Total_Seats}\nModel No is {this.Model_No}\n";
            WriteLine(Info);
            Engine Obj = new Engine();
            Obj.Engine_Info();
        }
    }
    class Engine
    {
        public void Engine_Info()
        {
            WriteLine("Engine is 4 stroke and fuel efficiency is good");
        }
    }
    class Program
    {
        static void Main(string[] args)
        {
            Suzuki Obj = new Suzuki();
            Obj.Color = "Black";
            Obj.Max_Speed = "240KM/Hour";
            Obj.Model_No = "SUZ234";
            Obj.Total_Seats = 4;
            Obj.CarInfo();
            ReadLine();
        }
    }
}
```
العلاقة فالكود هتكون composition لانه suzuki عملت اوبجكت لengine جواها