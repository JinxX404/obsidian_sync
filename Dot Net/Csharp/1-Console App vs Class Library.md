اشهر اتنين بنعملهم فالسي شارب هما الconsole app , class lib 
الconsole app بيطلعلنا فايل .exe يعني فايل executable  بيتنفذ اكواد معينه جواه لما ادوس عليه 

لاكن الclass library هو بيشيل مجموعة كلاسات وبيطلع فايل .dll ده مش بيتنفذ لوحده , لازم حاجه تناديه


----
![[Pasted image 20240710220750.png]]
لما بعمل new console app بيعمل solution ويحط جواه البروجكت ده 
بيحط السوليوشن فنفس فولدر البروجكت وبيكون ليه اكستنشن .sln

![[Pasted image 20240710221030.png]]

البروجكت بيعمل فايل للكونفجريشن وبيكون .csproj 
![[Pasted image 20240710220940.png]]
بيكون شايل داتا معينه مكتوبه ب XML علشان الIDE يفهم البروجكت
زي الفريمورك الي شغال بيها ونوع الفايل الي هينتجه البروجكت




الفولدر بتاع obj بيكون فيه داتا استخدمناها في مرحلة الbuild للبروجكت 
- **obj Folder**:
    
    - **Purpose**: This folder is used for temporary object files and other files needed during the build process.
    - **Subfolders**:
        - `Debug` or `Release` subfolders, just like in the bin folder.
    - **Contents**:
        - Intermediate files created during the build process, including temporary object files, generated code files, and build log files.



الفولدر بتاع الbin بيكون فيه ال.exe فايل بعد ما نعمل build للبروجكت

- **bin Folder**:
	- **Purpose**: This folder contains the compiled binaries (executable files and other necessary files) of your application.
	- **Subfolders**:
	    - `Debug` or `Release` subfolders are common, depending on your build configuration. `Debug` is used during development, and `Release` is used for the final product.
	- **Contents**:
	    - The actual executable (.exe) and any dependent libraries (.dll files).



الProgram.cs ده جواه  الentry point بتاعتنا الي هي Main Method

لو ضيفت اي كلاس تاني هيتضاف .cs وهيكون فالفولدر الي بره زي كده 
![[Pasted image 20240710223759.png]]


- **bin**: Holds the final output of your build, separated by configuration (Debug/Release).
- **obj**: Contains intermediate files and other build artifacts.


لما ضفت بروجكت تاني لنفس السوليوشن هنلاقيه عدل فالفايل بتاع السوليوشن وضاف تفاصيل البروجكت الجديد 
![[Pasted image 20240710225455.png]]


---
"build" refers to the process of converting source code files into executable software.
بيختلف حسب الenvironment واللغه المستخدمه وبتتعامل ازاي 

generally include:

1. **Compilation**:
    
    - Source code files (like `.cs` files in C#) are translated into intermediate language or machine code.
    - In C#, the source code is compiled into Intermediate Language (IL) code, which is platform-independent.
2. **Linking**:
    
    - The compiled code is combined with libraries and other resources to create a complete executable program.
    - In C#, this includes linking against .NET assemblies that your code depends on.
3. **Packaging**:
    
    - The executable file and any necessary resources (such as configuration files, images, etc.) are packaged together.
    - This can involve creating an installer or just packaging files into a specific directory structure.


### Detailed Steps in a Build Process

1. **Pre-processing**:
    
    - Any necessary code generation or modification steps before compilation.
2. **Compilation**:
    
    - Each source code file is compiled into an intermediate object file.
3. **Assembly**:
    
    - The object files and libraries are assembled into a single unit (an executable or a DLL).
4. **Linking**:
    
    - Resolving references between object files and libraries.
    - Combining these into a single executable file.
5. **Post-processing**:
    
    - Additional steps after the main build process, such as code signing, creating a package, or running tests.



- **Compilation**: The C# compiler (`csc.exe`) compiles `Program.cs` into Intermediate Language (IL) code, producing an object file (`Program.obj`).
- **Linking**: The object file is linked with other necessary libraries (like the .NET runtime libraries) to create the final executable (`ConsoleAppTEST.exe`).
- **Packaging**: The `ConsoleAppTEST.exe` and any other required files (like configuration files) are placed in the `bin\Debug` or `bin\Release` folder.




### Build Configuration

You can build your project in different configurations, typically:
ممكن البيلد يتم بطريقتين 
- **Debug**: Includes debugging information to help developers debug the application. The `bin\Debug` folder contains the output.
الاولي بيحط debugging information علشان اقدر اعمل debug للابلكيشن وبيتحط في bin/debug

- **Release**: Optimized for performance and without debugging information. The `bin\Release` folder contains the output.
التاني بيكون optimized من غير debug وبيتحط في bin\release