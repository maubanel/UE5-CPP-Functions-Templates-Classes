![](../images/line3.png)

### Class Inheritance

<sub>[previous](../classes-cpp-ii/README.md#user-content-classes-in-cpp-ii) • [home](../README.md#user-content-ue5-cpp-functions--templates--classes)</sub>

![](../images/line3.png)

In C++, inheritance is a process in which one class acquires the properties and behaviors of another class automatically. The class that inherits the members of another class is called the derived class, and the class whose members are inherited is called the base class.

To inherit a class in C++, we use the colon (:) symbol followed by the access specifier and the name of the base class. The access specifier can be public, protected, or private, and it determines the visibility of the base class members in the derived class. The most common is to use the public access specifier.

<br>

---

##### `Step 1.`\|`UECPPFTC`|:small_blue_diamond:

Add a new project to the solution by selecting **File | Add New | Project** and select a console C++ project and press the <kbd>Next</kbd> button.

![add console cpp project to solution](images/addProject.png)

![](../images/line2.png)

##### `Step 2.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: 

Call the project `ClassInheritanceCasting` and leave it in the same folder. Press the <kbd>Create</kbd> button.  Now right click the new project in the **Solution Explorer** and select **Set as Startup Project**. 

![create ClassInheritanceCasting project and set as default](images/solutionExplorer.png)

![](../images/line2.png)

##### `Step 3.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Add a `Main.cpp` file to the project.  We will start by including `iostream` and allowing us to direftly call `cout` and `string`. We will start with our base class `Enemy` which will have two public members, with the first being the number of heads the creature has and then the species name.  We initialize the number of heads to a default of `1` the most common and since each **Name** will be unique we leave it an empty string.

We will then create two derived classes one `Aligator` and the other `Lion`.  Now they are derived by deriving aligator from enemy using the public access specifier.
```cpp
class Aligator : public Enemy
{
// do something
};
```

Then we will create a **Lion** type and define its name.  We don't need to define the **NumberOfHeads** as the default of `1` we inherit will do.

![create two derived classes from Enemy](images/startingMain.png)

![](../images/line2.png)

##### `Step 4.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 5.`\|`UECPPFTC`| :small_orange_diamond:

Run the project.  Even though there are no variables in the derived **Lions** class it still has access to its parents public and protected members.  Remember protected allows any derived class to access those members but not other classes.

This is called encapsulation which is a fundamental concept in object-oriented programming (OOP) that involves bundling data members and functions inside a single class. 

Encapsulation helps to protect the internal state of an object by keeping its data members private, and access to and modification of these data members is restricted to the class’s public methods, ensuring controlled and secure data manipulation. 

Encapsulation also leads to data abstraction, which is a mechanism of exposing only the interfaces and hiding the implementation details from the user.

So we get a lion with 1 head.


![run projetd lion with 1 head](images/InheritDerivedVars.png)

![](../images/line2.png)

##### `Step 6.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond:

Now what if we wanted to keep an array of all enemies regardless of the derived class (so in our case both **Aligator** and **Lion**). This is where pointers can be useful.  Since they both derive from the same enemy class we can store an array of pointers of the base class type.

Now when we access this base class member we will get the derived value.  Let me demonstrate this.

We create a pointer to the base class by calling:

```cpp
Enemy* pE = &L;
```

So we create a pointer to the **Enemy** (not the **Lion**) base class of **L** (which is an instance of the derived Lions class).  We then output the **Name** from the parent class.  But it prints out **Lion** and not an empty string as it wasn't initialized.

![alt_text](images/derivedPointer.png)

![](../images/line2.png)

##### `Step 7.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

This is called polymorphism.  This is one of the key features of object-oriented programming. In C++, polymorphism can be achieved through inheritance, overriding, and overloading.

Inheritance is a mechanism that allows a class to inherit properties and methods from another class. Overriding is a feature that allows a subclass to provide its own implementation of a method that is already defined in its superclass. 

Polymorphism is useful for code reusability, as it allows us to reuse attributes and methods of an existing class when we create a new class. Polymorphism is also useful for creating more flexible and extensible code, as it allows us to write code that can work with different types of objects.

It also can cause some interesting challenges that we need to be aware of. So it allows us to have variables that are only accessible in the derived classes.  Lets add a new `string` called **Feature** to each derived class and output them.

![output feature variable](images/derivedMembers.png)

![](../images/line2.png)

##### `Step 8.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now since this is not in the derived class we cannot access the member.  We get a compiler error.

![cannot access members not in base class](images/notInDerivedClass.png)

![](../images/line2.png)

##### `Step 9.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

We now will change the number of heads a **Lion** has to `3`.  Now the base class initialized it to `1`.  What will we get when we point to this variable in the **Base Class**?

![change lionts head to three](images/changeLionsHead.png)

![](../images/line2.png)

##### `Step 10.`\|`UECPPFTC`| :large_blue_diamond:

It is still showing the derived value even though it is pointing to the base class **NumberOfHeads**.

![showing derived value](images/stillShowsDerivedValue.png)

![](../images/line2.png)

##### `Step 11.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: 

This can be dangerous though as there can be some issues.  If we create a **Private** member in the base class of **Feature** the compiler will not complain.  We can add a getter function to get the value in a derived class.  But when we point to **Feature** in from the pointer to the base class we don't get the overloaded derived public feature but the private one.  So be careful.  

![feature in base class with different access specifier](images/dangerousBug.png)

![](../images/line2.png)

##### `Step 12.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

To access this member through a pointer to the base class we will have to **cast** it to the derived class. This is very common in Unreal to go from a class like your **Character** class then cast to your derived class that you are using in the game.  

In C++, `static_cast` is an operator that performs an explicit type conversion. It can be used for operations such as implicit conversions between types as well as pointers.

To cast a pointer from one type to another, `static_cast` can be used. For example, to cast a pointer of a `base class` to a pointer of a `derived class`, `static_cast` can be used. In our case we are casting from our **Enemy** base class to our **Aligator** derived class.

![static cast with pointers](images/staticCastPointers.png)

![](../images/line2.png)

##### `Step 13.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

That's it for this walk through. Thanks for following through to the end.

![](../images/line.png)

![the end](images/banner.png)

![](../images/line.png)

| [previous](../classes-cpp-ii/README.md#user-content-classes-in-cpp-ii)| [home](../README.md#user-content-ue5-cpp-functions--templates--classes) |
|---|---|
