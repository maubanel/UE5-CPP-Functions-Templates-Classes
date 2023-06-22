![](../images/line3.png)

### Containers

<sub>[previous](../static-array/README.md#user-content-static-array) • [home](../README.md#user-content-ue5-cpp-functions--templates--classes) • [next](../)</sub>

![](../images/line3.png)

C++ provides a variety of containers in the Standard Template Library (STL) that can be used to store and manipulate collections of objects. The containers are implemented as class templates, which allows great flexibility in the types supported as elements. The STL containers can be broadly classified into three categories: sequential containers, associative containers, and unordered associative containers.

Sequential containers allow us to store elements that can be accessed in sequential order. Internally, sequential containers are implemented as arrays or linked lists data structures. The following are the types of sequential containers in C++:

- `std::array`: Static contiguous array (class template)
- `std::vector`: Dynamic contiguous array (class template)
- `std::deque`: Double-ended queue (class template)
- `std::forward_list`: Singly-linked list (class template)
- `std::list`: Doubly-linked list (class template)

Associative containers implement sorted data structures that can be quickly searched (O(log n) complexity). The following are the types of associative containers in C++:

- `std::set`: Sorted set of unique keys (class template)
- `std::multiset`: Sorted set of keys with duplicates (class template)
- `std::map`: Sorted key-value pairs (class template)
- `std::multimap`: Sorted key-value pairs with duplicate keys (class template)

Unordered associative containers provide the unsorted versions of the associative container. The following are the types of unordered associative containers in C++:

- `std::unordered_set`: Unsorted set of unique keys (class template)
- `std::unordered_multiset`: Unsorted set of keys with duplicates (class template)
- `std::unordered_map`: Unsorted key-value pairs (class template)
- `std::unordered_multimap`: Unsorted key-value pairs with duplicate keys (class template)

Each container has its own set of member functions to access and manipulate its elements. Iterators are used to traverse the elements of a container. The elements of containers are accessed by using iterators, which have a common interface but each container defines its own specialized iterators.

<br>

---

##### `Step 1.`\|`UECPPFTC`|:small_blue_diamond:

Lets start with a dynamic contiguous array in the Standard Template Library (STL) called **Vector**.

A vector in C++ is a sequence container that represents an array that can change its size during runtime. It is a template class in the Standard Template Library (STL) of C++ programming language. Vectors are similar to dynamic arrays, but they have the ability to resize themselves automatically when an element is inserted or deleted. The storage of vector elements is handled automatically by the container, and the elements are placed in contiguous storage so that they can be accessed and traversed using iterators (pointers). In vectors, data is inserted at the end, and removing the last element is the most efficient.

Open up your **CPP_FTC** solution and open your **Function.cpp** file.Include the **vector** .h file from the STL.

![add vector container to project](images/addVectorClassToCPP.png)

![](../images/line2.png)

##### `Step 2.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: 

A template class has a different syntax than a static array.  We have the 

```cpp
// containerType<listType>(NumberOfStartingElements);
vector <string> Cards(4);
```

So we declare it in its unique way so it is a vector container with a list of 4 strings.  We then assign the strings in the same way we did with arrays.

Press the <kbd>Play</kbd> button and you see that [2] prints the third card.

![assigning method 1](images/declareTemplateArray.png)

![](../images/line2.png)

##### `Step 3.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

You can also assign the vector container with a list of multiple items in `{}` such as `{"one", "two", "three}`.  Press the <kbd>Play</kbd> button and notice that it is the same as before but takes much less space in the file and is a bit easier to read.

![assigning method 1](images/AssigningVectorAlternate.png)

![](../images/line2.png)

##### `Step 4.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now just like arrays, you should not exceed the size of the area and try and access an item that does not exist.  If you change the item to `20` and press the Press the <kbd>Play</kbd> button, you will get an assertion.  Now this would allow you to write code to handle the assertion and potentially not crash.  If you press the <kbd>Ignore</kbd> button, then it goes and crashes just olike the array did prior.

![out of bounds assertion](images/assertionInGame.png)

![](../images/line2.png)

##### `Step 5.`\|`UECPPFTC`| :small_orange_diamond:

Now we can also figure out how many items there are in the vector class using `vector::size()`.  [This method](https://cplusplus.com/reference/vector/vector/size/) returns the number of elements the vector class contains.

So now lets add a print out of how many cards are in the **Card** instance.  Press the <kbd>Play</kbd> button and you will notice that we have 4 cards.

![size of vector class](images/AddSize.png)

![](../images/line2.png)

##### `Step 6.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond:

![alt_text](images/.png)

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

| [previous](../static-array/README.md#user-content-static-array)| [home](../README.md#user-content-ue5-cpp-functions--templates--classes) | [next](../)|
|---|---|---|
