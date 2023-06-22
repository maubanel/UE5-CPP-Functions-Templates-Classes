![](../images/line3.png)

### const Keyword

<sub>[previous](../macros/README.md#user-content-macros--blueprints) • [home](../README.md#user-content-ue5-cpp-functions--templates--classes) • [next](../static-array/README.md#user-content-static-array)</sub>

![](../images/line3.png)

In C++, the const keyword is used to specify that a variable's value is constant and cannot be modified. 

Declaring a variable as const means that its value cannot be changed once it has been initialized. A const variable in C++ needs to be initalized and assigned at the same time.

<br>

---

##### `Step 1.`\|`UECPPFTC`|:small_blue_diamond:

Load the **UE5_CPP_FTC** project and open the **CPP_HealthCounter.h**. Now comment out our Macro and we will replace it with a more suitable **const** var.

```cpp
const int32 RESETHEALTH = 6000;
```

![alt_text](images/resetHealth.png)

![](../images/line2.png)

##### `Step 2.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: 

![alt_text](images/runThroughEditor.png)

![](../images/line2.png)

##### `Step 3.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/sixThousandConst.png)

![](../images/line2.png)

##### `Step 4.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/changeConst.png)

![](../images/line2.png)

##### `Step 5.`\|`UECPPFTC`| :small_orange_diamond:

![alt_text](images/wontCompile.png)

![](../images/line2.png)

##### `Step 6.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond:

![alt_text](images/commentOutBug.png)

![](../images/line2.png)

##### `Step 7.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/nowCompiles.png)

![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Static Array"> -->

![next up - ](images/banner.png)

![](../images/line.png)

| [previous](../macros/README.md#user-content-macros--blueprints)| [home](../README.md#user-content-ue5-cpp-functions--templates--classes) | [next](../static-array/README.md#user-content-static-array)|
|---|---|---|
