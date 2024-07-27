لو عايز اتعامل مع الاوبجكت كانه داتا تايب عادي واقدر اجمع واطرح واقارن ما بين الاوبجكتس

بستخدم الاوبريتور اوفرلودينج

---

لو حاولت اجمع اتنين اوبجكت زي كده وجواهم قيمه مثلا

```C#
class Money
{
    private decimal amount;
    public string Amount { get; set; }
    public Money(decimal amount)
    {
        this.amount = amount;
    }
}

        Money m1 = new Money(10);   
        Money m2 = new Money(20);
        Money m3 = m1 + m2;
```

m3 كان بيحاول يجمع القيمتين الي جوه اول اتنين اوبجكت

لاكن هيديلي ايرور لانه مش عارف يجمع ايه جوه الاوبجكتس

ساعتها بييجي دور الاوبريتور اوفرلودينج

وهو واحد من عناصر الكلاس زيه زي البروبرتي والفيلد

بعمل اوبرتور اوفرلودينج جوه الكلاس وبحدد فيه اللوجيك الي هنمشيه علي العمليات الحسابيه الي هنعملها علي الاوبجكت من الكلاس ده

بعمل اوبرتور اوفرلودينج جوه الكلاس وبحدد فيه اللوجيك الي هنمشيه علي العمليات الحسابيه الي هنعملها علي الاوبجكت من الكلاس ده

```C#
class Program
{
    static void Main()
    {
        Money m1 = new Money(10);   
        Money m2 = new Money(20);
        Money m3 = m1 + m2;

        Console.WriteLine(m3);//30
    }
}
class Money
{
    private decimal amount;
    public decimal Amount => amount;
    public Money(decimal value)
    {
        this.amount = value;
    }
    public static Money operator +(Money money1, Money money2)
    {
        var value = money1.Amount + money2.Amount;
        return new Money(value);
    }
    public override string ToString()
    {
        return Amount.ToString(); // Convert the amount to a string when ToString is called.
    }

}
```

ونقدر نعمل اكتر من اوبيرتور للكلاس

نقدر نعمل - -,++,+ , - بشكل طبيعي بدون مشاكل

لاكن عندنا حالات بتيجي in pairs

يعني بتيجي مع حاجه تاني مش فرديه

**(≥,≤) , (==,≠),(>,<)**

**الحالات دول لو عملت منهم واحده مثلا لازم اعمل عكسه**ا

```C#
class Program
{
    static void Main()
    {
        Money m1 = new Money(10);   
        Money m2 = new Money(20);
        Money m3 = m1 + m2;
        Money m4 = m1 - m2;
        bool m5 = m1 > m2;
        bool m6 = m1 < m2;
        bool m7 = m1 >= m2;
        bool m8 = m1 <= m2;
        bool m9 = m1 == m2;
        bool m10 = m1 != m2;
        Money m11 = ++m1;
        Money m12 = --m2;
        Console.WriteLine("summation : "+m3);
        Console.WriteLine("substraction : " + m4);
        Console.WriteLine("greater than : " + m5);
        Console.WriteLine("less than : " + m6);
        Console.WriteLine("greater than or equal : " + m7);
        Console.WriteLine("less than or equal : " + m8);
        Console.WriteLine("equallity : " + m9);
        Console.WriteLine("Inequallity : " + m10);
        Console.WriteLine("prefix sum m1 : " + m11);
        Console.WriteLine("prefix sub m2 : " + m12);


    }
}
class Money
{
    private decimal amount;
    public decimal Amount => amount;
    public Money(decimal value)
    {
        this.amount = value;
    }
    public static Money operator +(Money money1, Money money2)
    {
        var value = money1.Amount + money2.Amount;
        return new Money(value);
    }
    public static Money operator -(Money money1, Money money2)
    {
        var value = money1.Amount - money2.Amount;
        return new Money(value);
    }
    public static bool operator >(Money money1, Money money2)
    {
        return money1.Amount > money2.Amount;
    }
    public static bool operator <(Money money1, Money money2)
    {
        return money1.Amount < money2.Amount;

    }
    public static bool operator >=(Money money1, Money money2)
    {
        return money1.Amount >= money2.Amount;
    }
    public static bool operator <=(Money money1, Money money2)
    {
        return money1.Amount <= money2.Amount;

    }
    public static bool operator ==(Money money1, Money money2)
    {
        return money1.Amount == money2.Amount;
    }
    public static bool operator !=(Money money1, Money money2)
    {
        return money1.Amount != money2.Amount;

    }
    public static Money operator ++(Money money)
    {
        var res = money.Amount;
        return new Money(++res);
    }
    public static Money operator --(Money money)
    {
        var res = money.Amount;
        return new Money(--res);
    }
    public override string ToString()
    {
        return Amount.ToString(); // Convert the amount to a string when ToString is called.
    }

}
```