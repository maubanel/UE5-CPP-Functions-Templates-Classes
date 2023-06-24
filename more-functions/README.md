![](../images/line3.png)

### More with Functions

<sub>[previous](../containers/README.md#user-content-containers) • [home](../README.md#user-content-ue5-cpp-functions--templates--classes) • [next](../)</sub>

![](../images/line3.png)

Lets take a close look at **Functions** in C++.  

<br>

---

##### `Step 1.`\|`UECPPFTC`|:small_blue_diamond:

Re-open **CPP_FTC** solution and pick **Functions.h** and lets add a new function called `Abso`. This function will return type **double** and take an integer parameter.  This will return an absolute value to the integer passed (so it is always a positive number -5 would be become 5).

![add Abso function to .h](images/newFunction.png)

![](../images/line2.png)

##### `Step 2.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: 

Now click on the paintbrush next to the function declaration and select **Create definition of `Abso` in Function.cpp**.  This will give you a compilable start to the function definition.

![create definition](images/copySignature.png)

![](../images/line2.png)

##### `Step 3.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Open up the `.cpp` file and lets define **Abso()**.  We will check to see if value is positive,and if so just return the integer and if it is negative return the opposite sign (--X == +X). Then in the **main()** function call this new method.

Press the <kbd>Play</kbd> button and notice that if we pass `-15` we get `15` back!

![define abso cpp and call it](images/defineAndCallAbso.png)

![](../images/line2.png)

##### `Step 4.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

If we send a double to the function by parameter it will cast it to an integer and we will get a truncated double back so `-15.7` becomes `15`. How can we accomplish this objective?

![pass double to parameter](images/sendDoubleToInt.png)

![](../images/line2.png)

##### `Step 5.`\|`UECPPFTC`| :small_orange_diamond:

We can overload a function (a feature of C++) that allows multiple functions to have the same name but different parametersIn function overloading, the function name should be the same but the arguments should be different. Function overloading can be considered an example of a polymorphism feature in C++. Overloaded functions are those that belong to a class but have more than one instance with the same name but different parameters.

So in our case we can overload **Abso()** with a different parameter type. Open up the `.h` file and we will use the same return type, and the same name but a different parameter type.  In this case we will pass a double. It will be up to the program to pick the most appropriate version of the function based on the parameter given.

![overload Abso with double parameter](images/overloadDoubleParam.png)

![](../images/line2.png)

##### `Step 6.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond:

Now we have to define this new function in the `.cpp` file.  Now the code is the same as the math is identical.

Now when we Press the <kbd>Play</kbd> button, the program picks the overloaded function and does this math on the double parameter, preserving the fractional number.

![overloaded definition same as int](images/overloadedAbso.png)

![](../images/line2.png)

##### `Step 7.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 8.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 9.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 10.`\|`UECPPFTC`| :large_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 11.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 12.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 13.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 14.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 15.`\|`UECPPFTC`| :large_blue_diamond: :small_orange_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 16.`\|`UECPPFTC`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 17.`\|`UECPPFTC`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 18.`\|`UECPPFTC`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 19.`\|`UECPPFTC`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 20.`\|`UECPPFTC`| :large_blue_diamond: :large_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 21.`\|`UECPPFTC`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - ADD NEXT PAGE"> -->

![next up - ](images/banner.png)

![](../images/line.png)

| [previous](../containers/README.md#user-content-containers)| [home](../README.md#user-content-ue5-cpp-functions--templates--classes) | [next](../)|
|---|---|---|
