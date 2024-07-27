بنستخدم الاكسبريشن في اننا نتشيك علي الاسترينج ده null ولا لا

ولو null هنحط فيه قيمه مثلا

```C#
            string s1 = null;
            s1 = s1 ?? "moataz";  غلامتين الاستفهام بيسالو هو فاضي ولا لا ولو ايوه هيحطو الاسترينج جواه
            s1 = s1 ?? "mohammed"; هنا هو مش فاضي ف مش هحط حاجه جواه
            Console.WriteLine(s1);//moataz
```

The null coalescing operator (`??`) is a C# operator used to provide a default value for a nullable expression if it evaluates to `null`. It's a concise way to handle null values and ensure that you have a non-null result.

Here's the basic syntax of the null coalescing operator:

```C#
result = expression1 ?? expression2;
```

- `expression1` is the nullable expression that you want to check for null.
- `expression2` is the default value or expression to use if `expression1` is null.

Here's how it works:

1. If `expression1` is not null, the result will be the value of `expression1`, and `expression2` is not evaluated.
2. If `expression1` is null, the result will be the value of `expression2`.

Here are a few examples of how you can use the null coalescing operator:

```C#
int? nullableValue = ...; // Some nullable integer

// If nullableValue is null, assign 0 as the default value
int result = nullableValue ?? 0;
```

In this example, if `nullableValue` is null, `result` will be assigned the default value of 0.

```C#
string name = GetNullableName(); // Some method that may return null

// If name is null, assign "Unknown" as the default value
string displayName = name ?? "Unknown";
```

Here, if the `GetNullableName` method returns `null`, the `displayName` will be assigned the default value "Unknown."

The null coalescing operator is particularly useful when you want to provide sensible default values for nullable expressions, making your code more robust and less prone to null reference exceptions.

You can also chain the null coalescing operator to provide multiple fallback values, like this:

```C#
result = expression1 ?? expression2 ?? expression3;
```

In this case, it will evaluate each expression from left to right and return the first non-null value or the last expression if all expressions are null.

Here's a breakdown of the example:

```C#
result = expression1 ?? expression2 ?? expression3;
```

- `expression1`, `expression2`, and `expression3` are three different expressions, which could be variables, method calls, or any other expressions that can produce a result. These expressions may be nullable, meaning they might evaluate to `null`.
- The null coalescing operator (`??`) is used to provide a default value or fallback value in case all the expressions in the chain are `null`.
- The operator works as follows:
    - It evaluates `expression1`. If `expression1` is not `null`, it returns the result of `expression1`, and `expression2` is not evaluated.
    - If `expression1` is `null`, it then evaluates `expression2`. If `expression2` is not `null`, it returns the result of `expression2`, and `expression3` is not evaluated.
    - If both `expression1` and `expression2` are `null`, it evaluates `expression3` and returns its result.

Here's a practical example to illustrate this:

```C#
string firstName = null;
string middleName = "John";
string lastName = "Doe";

string fullName = firstName ?? middleName ?? lastName;
```

In this example:

- `firstName` is `null`.
- `middleName` contains "John."
- `lastName` contains "Doe."

The `fullName` variable will be assigned the first non-null value in the chain, which is "John." Since `firstName` is `null`, it evaluates `middleName` (which is not `null`) and assigns its value to `fullName`. If `middleName` were also `null`, it would evaluate `lastName` as the last resort.

So, `fullName` will contain "John" in this case. The null coalescing operator allows you to handle a sequence of potentially nullable values gracefully and obtain a non-null result from the first non-null expression in the chain.