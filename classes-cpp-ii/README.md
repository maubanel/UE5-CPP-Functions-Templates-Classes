![](../images/line3.png)

### Classes in CPP II

<sub>[previous](../classes-cpp/README.md#user-content-classes-in-cpp) • [home](../README.md#user-content-ue5-cpp-functions--templates--classes) • [next](../)</sub>

![](../images/line3.png)

Lets look at overloading the C++ constructor to allow for different ways to initialize the class.  We will also look at ways to cast from integers to enumerators safely.

<br>

---

##### `Step 1.`\|`UECPPFTC`|:small_blue_diamond:

Now lets say we wanted to allow a power user to remember the order of the cards and suits (which are alphabetical) and use integers to save time (may not be a recommneded practice though).  We can overload the constructor to also accept two integers.

![overload constructor](images/overloadConsructor.png)

![](../images/line2.png)

##### `Step 2.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: 

Now the compiler doesn't natively convert from `int` to `enum`.  So you need to call the `static_cast` operator. It is a compile-time cast that can be used for operations such as implicit conversions between types (such as int to enumerator class, int to float, or pointer to void*). The syntax of `static_cast` is `static_cast<dest_type>(source)` where `dest_type` is the data type to which the source is to be converted.

So in our case we want to go to **CardNumber** and **CardClass** as a destination and our sourse is an **int**. So in ther override definition cast from a interger to each of our enumerators.

![static cast](images/staticCast.png)

![](../images/line2.png)

##### `Step 3.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Open up the **Main.cpp** and pass the **Card** initialization two integers.  In this case a 3 of clubs.  Run the program to see if it overrides the constructor correctly.

![use int to initialize card](images/UseIntToInializeCard.png)

![](../images/line2.png)

##### `Step 4.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now we have to be careful about using `static_cast` to ensure a safe conversion.  If we pass card a value that is no in the range of our enumerator there will be a runtime crash. Make the following change to line 5.

```cpp
Card NextCard(1, 5);
```

So we know there is no 5 cards suit and the program crashes when run.

![program crashes on out of bounds array](images/staticCastCrash.png)

![](../images/line2.png)

##### `Step 5.`\|`UECPPFTC`| :small_orange_diamond:

Now it is crashing in our operator overload as there is no case for the switch statement that is valid.  This is where the **default** catch all will work and we will return an error message warning the programmer that they are not accessing a valid value. 

This default cast will run on any other possible integer value and return the error message below. 

![add default case to both enumerators](images/addDefaultToBothEnums.png)

![](../images/line2.png)

##### `Step 6.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond:

Now it will run without crashing and give us some feedback.

![messsage on suit without crashing](images/enterInvalidSuit.png)

![](../images/line2.png)

##### `Step 7.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Now, what if we wanted to have a default initializer than just gives us an ace of spades (first number and first suit) if you don't care which card is created or for a user that is just getting used to the class and doesn't know all of the enumerators yet.  We can create an initializer for a class with no parameters (you cannot use empty parenthesis `()` just a the name of the class or it won't compile).

![alt_text](images/defaultInitializer.png)

![](../images/line2.png)

##### `Step 8.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

We can overload the constructor so it has a a default constructor to run if no parameters are passed.

![default overload for constructor](images/overloadConstructor.png)

![](../images/line2.png)

##### `Step 9.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

In the definition we will pass an Ace of Clubs to the default constructor.

![ace of clubs in default constructor](images/defineAceClubs.png)

![](../images/line2.png)

##### `Step 10.`\|`UECPPFTC`| :large_blue_diamond:

Now you can run and the constructor overload will pick the correct definition and return the ace of spades!

![ace of spades when running program](images/overloadedDefaultConstructorRun.png)

![](../images/line2.png)

##### `Step 11.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: 

Now what if we wanted the player to be able to increment the card?  This is just an example since we have made the card read only and private I wouldn't want you to mutate the card.

This is just a demonstration that for custom classes we can override the mathematical operators with any logic we want.  Now we want to be germain to their original meaning.  So I am interpreting `++` operator as the next card number in the same suit.

So lets override the `++` operator.  We need to versions for for `foo++` a post fix operator and `++foo` a prefix operator.

For the postfix we are returning with a pass by reference and prefix a by value.

![add ++ overide initilialization](images/override++Operator.png)

![](../images/line2.png)

##### `Step 12.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Right click on both override initializations and select **Create definition of `operator++` in Card.cpp**. This will create two boilerplates to work from in the `.cpp` file.

![boilerplate definition](images/boilerplateDefinition.png)

![](../images/line2.png)

##### `Step 13.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

We can overload the pre-increment operator by returning a reference to the object being incremented. So `Card& overload++(Card& Orig)` returns a reference to the object itself which allows for chaining multiple increment opertaions todather like `++(++NextCard)`.

We also need to allow for ++ to wrap so that when we increment the **King** we go back to the **Ace**.  We then need to cast the to a **CardNumber** the private **Number** member.  This means we need to make it a friend class which we did in the `.h`.  If it was not a private member we could have left it a public class.

For the postfix operator we pass it a `operator++(Card& Orig, int)` a dummy parameter to differentioate it from the prefix operator. So in this case we make a copy of the card and return that value so it is unchanged.  Then we increment the rereference with the prefix operator (handles the King wrapping logic).  So this function retunrs a copy of the object before it was incremented.  So the next line we will get the incremented value.

Lets test this definition.

![incrementer definitions](images/incrementerDefinitions.png)

![](../images/line2.png)

##### `Step 14.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 



![alt_text](images/testPrefixOverload.png)

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

| [previous](../classes-cpp/README.md#user-content-classes-in-cpp)| [home](../README.md#user-content-ue5-cpp-functions--templates--classes) | [next](../)|
|---|---|---|
