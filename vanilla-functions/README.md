![](../images/line3.png)

### Vanilla CPP Functions

<sub>[previous](../setting-up/README.md#user-content-setting-up-unreal) • [home](../README.md#user-content-ue5-cpp-functions--templates--classes) • [next](../bp-functions/README.md#user-content-blueprint-functions)</sub>

![](../images/line3.png)

In C++, a function is a block of code that performs a specific task. It is a reusable piece of code that can be called from anywhere in the program. Every C++ program has at least one function, which is the `main()` function. A function can be predefined or user-defined.

A predefined function is a function that is already defined in the C++ standard library, such as `std::cout`. A user-defined function is a function that is created by the programmer to perform a specific task. It is defined by specifying the function name, return type, and parameters (if any) in the function declaration, followed by the function body in the function definition.

Lets create a user defined function.
<br>

---

##### `Step 1.`\|`UECPPFTC`| :small_blue_diamond:

A user defined function has:

```ReturnValueType NameOfFunction(Parameter to pass, Paremeter2 to pass....)```

A function starts with a **return value** type.  If the function returns nothing the type is `void`. In C++, `void` is a keyword that is used to indicate the absence of a type. It is used in several different contexts. It is important to note that void is not a type qualifier on any value. Despite the name, this is semantically similar to an implicit unit type, not a zero or bottom type (which is sometimes confusingly called the "void type").

Lets now create a function. Now we have used functions before `main()` but Rider runs **main()** by default.  We can also define a new function before `main()`.  In this case we defined a new function that returns no value (it is void).  Next run the game to see what happens. Then we have `void Sorry()` a function that returns no value and prints `Sorry!` to console.

![alt_text](images/basicFunction.png)

![](../images/line2.png)

##### `Step 2.`\|`UECPPFTC`| :small_blue_diamond: :small_blue_diamond: 

 Run the program and `main()` runs and calls the `Sorry()` function.  The function just prints `Sorry!` to the console.

![run Sorry() function](images/sorryToConsole.png)

![](../images/line2.png)

##### `Step 3.`\|`UECPPFTC`| :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now what happens when we move the **Sorry** function after the **Main** function.  Will it still work?  Copy and paste the function definition below the **main** function. Now before we even try and run the program or compile **Rider** is indicating that we have a problem.  It is really convenient that we can start to debug and know there is a problem even before we compile!

![ move Sorr() to end](images/moveSorryAfterMain.png)

![](../images/line2.png)

##### `Step 4.`\|`UECPPFTC`| :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now we don't know what the error is yet.  So you can put your cursor over the red highlighted text and rider tells you it **Cannot resolve sympol 'Sorry'**.

Now **Build** the project <kbd>cntrl shift B</kbd> and you get an error saying **'Sorry': identifier not found**. It also tells us that the compile did not succeed so we cannot run the program as is.

In C++ you can have the definition of the **C++** file anywhere but you need to **declare** it to the compiler before it is called. Otherwise the linker does not know where the definition of the function resides.

In C++, a *function declaration* tells the compiler about a function's name, return type, and parameters, while a function definition provides the actual body of the function.

![compiled function error](images/identifierNotFound.png)

![](../images/line2.png)

##### `Step 5.`\|`UECPPFTC`| :small_orange_diamond:

So all we need to do to fix the problem is have a **Function Declaration** before it is called in `main()`.  In C++, a function declaration tells the compiler about a function's name, return type, and parameters, while a function definition provides the actual body of the function.

Now press <kbd>Run</kbd> button and the function runs as it did before and compiles fine.

![run project with function declaration](images/functionDeclaration.png)

![](../images/line2.png)

##### `Step 6.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond:

In C++ programming, header files are used to declare functions, that are used in a program. Header files are included in a program using the `#include` **preprocessor** directive. This way if the **.cpp** file loads the header file at the top and it includes all our declarations, it will not matter what order we define all of our functions.

In C++, header files should but does not have to end with the .h extension, but it is customary to do so.

User-defined header files are created by the user and can also be imported using the #include directive (just like we do for <iostream>. To create one right click on the **Functions** Project folder and select **Add | File** and call it `Functions.h` the same name as the `.cpp` file with a different extension.  Press the <kbd>OK</kbd> button.

![add Functions.h to header folder](images/cppHeaderFile.png)

![](../images/line2.png)

##### `Step 7.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Open up **Functions.h" which includes `#pragma once`.  This is a preprocessor directive that is used to ensure that a header file is included only once in a single compilation. It is a non-standard but widely supported directive that serves the same purpose as include guards, but with several advantages, including less code, avoidance of name clashes, and sometimes improvement in compilation speed.  This means that you can include the same file in multiple portions of the game but it will only include a single copy of this code regardless of how many times the header is called.

Now move the function declaration from the `Functions.cpp` to `Functions.h`.

![move the Sorry function definion to the .h file](images/moveSorryToDotH.png)

![](../images/line2.png)

##### `Step 8.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now at the top of **Functions.cpp** we need to include the header.  So this will basically read this before processing the code on the page so the compiler will know that this files will define `Sorry()` regardless of the order. This is why all of our *#include*'s are at the top of the page.

```
#include "Functions.h"
```
> We do not use the `<>` naming as this is not a standard include.  We use the `""` and it will look in the project directory for that file.

![add an inlcude in the cpp file](images/includeNewHeader.png)

![](../images/line2.png)

##### `Step 9.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now when you run the program it is the same as before but we are declaring our functions in the `.h` file and including it in the `.cpp`.

![h and cpp files working when run](images/dotHdotCPP.png)

![](../images/line2.png)

##### `Step 10.`\|`UECPPFTC`| :large_blue_diamond:

Start off by adding a comment on top of the first function. 

Lets add another function that will return an integer.  

```
//ReturnValueType NameOfFunction(Parameter to pass, Paremeter2 to pass....)
int DoDamage(int Damage, int Health);
```
So we always start with the return value type.  In C++ we can pass many parameters but it can only return one type of data, and in the above example that is an `int`.  Then the name of the function is `DoDamage` and it requires the caller to include two integer parameters, one representing the amount of damage and the other representing the player's health.

So add this function decalration in **Functions.h**.

![add int DoDamage(int Damage, int Health) declaration](images/addDoDamage.png)

![](../images/line2.png)

##### `Step 11.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: 

In C++, the return statement is used to return a value from a function. The value returned by the function can be of any data type, including built-in types and user-defined types. The return value must return the type specified by the function.  So in this case we are return the result of subtracing `Damage` from `Health`. So this is in our function definition.  We also in **main()** need to add an integer representing our `Health` percentage that starts at `100`.  Then we take the return from `DoDamage()`and put it in the health variable.  The damage parameter is passed at `10` so it should return `90` to health when called.

![return Damage - Health](images/returnInt.png)

![](../images/line2.png)

##### `Step 12.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Now press the <kbd>Local Windows Debugger</kbd> button to run the program, and will print the new player health value of 90.

Next up lets try and build the same thing using a **Blueprint** function in Unreal.

![run project to see player health](images/runtheSimulation.png)

![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Blueprint Functions"> -->

<!--![next up - ](images/banner.png)--><!-- old code -->
<a href="../bp-functions/README.md#user-content-blueprint-functions"><!-- new code -->
  <img src="images/banner.png" alt="next up - !" />
</a>

![](../images/line.png)

| [previous](../setting-up/README.md#user-content-setting-up-unreal)| [home](../README.md#user-content-ue5-cpp-functions--templates--classes) | [next](../bp-functions/README.md#user-content-blueprint-functions)|
|---|---|---|
