Enumerations (enums) in C# provide a convenient way to define a set of named values. However, there are scenarios where we must represent multiple values or combinations of values using a single enum variable. This is where bitwise enums come into play. Bitwise enums in C# allow for efficient and flexible flag-based enumerations, enabling us to store and manipulate multiple values in a compact form.

## What is Bitwise Enums?

A bitwise enum is an enum type that uses bitwise operations to combine multiple enum values into a single value. Each enum value is assigned a unique bit flag, represented by a power of 2. By assigning these flags, we can represent multiple enum values by combining or masking them using bitwise operators.



نوع من الenum بيشيل اكتر من قيمه فنفس الوقت 
وبنقدر نعمل عليه عمليات الbitwse operations زي ~ & | ^ 
بنستخدمه فاكتر من حاجه ومن ضمنهم اننا نخزن اكتر من قيمه جوه الداتابيز

علشان احدد انه flag enum بنحط attribute فوق الenum يحدد انه flag
زي كده \[flag]
بيقول للكومبايلر انه يعامله بطريقه مختلفه 
وتاني حاجه اننا هنمشي علي طريقه في الترقيم 
مش 1 2 3 
فالاول هنعمل None = 0  ك best practice لاول اختيار 
وهنبدا نرقم من 
1 2 4 8 16 32 64 128 

```C#
[Flags] enum DaysOfWeek {
  None = 0,
  Monday = 1,
  Tuesday = 2,
  Wednesday = 4,
  Thursday = 8,
  Friday = 16,
  Saturday = 32,
  Sunday = 64
};
```



flag enums in C#! Flag enums are a way to create enumeration types where each value represents a single bit in a binary value. This allows you to combine multiple values into a single variable, which can be useful for scenarios where you need to represent multiple options or settings.

example of a flag enum in C# that represents file permissions:

```C#
[Flags]
enum FilePermissions
{
    None = 0,       // No permissions
    Read = 1,       // Read permission (0001 in binary)
    Write = 2,      // Write permission (0010 in binary)
    Execute = 4,    // Execute permission (0100 in binary)
    Delete = 8      // Delete permission (1000 in binary)
}
```

In this example, each permission is represented by a bit in binary form. You can combine these permissions to represent different sets of file permissions.

1. **Setting Permissions**:
    
    You can set permissions by combining them using the bitwise OR operator:
    
    ```C#
    FilePermissions myPermissions = FilePermissions.Read | FilePermissions.Write;
    ```
    
    This represents read and write permissions.
    
2. **Checking Permissions**:
    
    You can check if a specific permission is set using the bitwise AND operator:
    
    ```C#
    if ((myPermissions & FilePermissions.Read) != 0)
    {
        // Read permission is granted
    }
    ```
    
    This checks if the read permission is granted in `myPermissions`.
    
3. **Adding or Removing Permissions**:
    
    You can add or remove permissions using bitwise OR and bitwise XOR operators:
    
    ```C#
    // Add execute permission
    myPermissions |= FilePermissions.Execute;
    
    // Remove write permission
    myPermissions &= ~FilePermissions.Write;
    ```
    
4. **Testing for Specific Combinations**:
    
    You can test for specific combinations of permissions:
    
    ```C#
    if ((myPermissions & (FilePermissions.Read | FilePermissions.Write)) == (FilePermissions.Read | FilePermissions.Write))
    {
        // Both read and write permissions are granted
    }
    ```
    

This example demonstrates how you can use flag enums to represent and manipulate different sets of file permissions efficiently.

---

> [!info] ChatGPT  
> Hello!  
> [https://chat.openai.com/share/939317ef-097c-4fb3-9427-3579fcff2189](https://chat.openai.com/share/939317ef-097c-4fb3-9427-3579fcff2189)