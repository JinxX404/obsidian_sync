```C#
using System;
using static System.Console;
namespace DotNetJourney.DateTimeClass
{
    class Program
    {
        static void Main(string[] args)
        {
            DateTime currentDateTime = DateTime.Now;
            var y = currentDateTime.Year;
            var mon = currentDateTime.Month;
            var d = currentDateTime.Day;
            var h = currentDateTime.Hour;
            var min = currentDateTime.Minute;
            var s = currentDateTime.Second;
            var ms = currentDateTime.Millisecond;
            var k = currentDateTime.Kind;
            var dayOfWeek = currentDateTime.DayOfWeek;
            var dayOfYear = currentDateTime.DayOfYear;
           
            WriteLine($"Year {y} , Month {mon} , Day {d} , Hour {h} , Min {min} , Seconds {s} , MilleSeconds {ms} , Kind {k} , DW {dayOfWeek} , DY {dayOfYear}");
        }
    }
}
```

> [!info] ChatGPT  
> Mastering the DateTime struct in C# involves understanding its various properties and methods for working with date and time values effectively.  
> [https://chat.openai.com/share/787e59a9-a2cc-42c8-87b2-3b8aa10a0c91](https://chat.openai.com/share/787e59a9-a2cc-42c8-87b2-3b8aa10a0c91)