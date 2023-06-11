![](../images/line3.png)

### Blueprint Functions

<sub>[previous](../vanilla-functions/README.md#user-content-vanilla-cpp-functions) • [home](../README.md#user-content-ue5-cpp-functions--templates--classes) • [next](../unreal-cpp-functions/README.md#user-content-unreal-capp-functions)</sub>

![](../images/line3.png)

Blueprint functions are a bit different in C++.  They allow for multiple return values and don't require a declaration.  It is defined and declared all in place.  

Blueprint functions are node graphs that belong to a particular Blueprint and can be executed or called from another graph within the Blueprint. They allow the reuse of code, improve overall organization, and make it easier to maintain and update your project. Functions have a single entry point designated by a node with the name of the function containing a single exec output pin. When the function is called from another graph, the output exec pin is activated, causing the connected network to execute.

To create a function inside a Blueprint Class or Level Blueprint, you can use the My Blueprint tab and click the Add Button on the functions list header. You can then enter a name for your function and create the function graph by dragging off the function node and adding nodes to it. You can also create functions in code by specifying the BlueprintCallable or BlueprintPure keyword in the UFUNCTION declaration.

Blueprint functions can be used to perform a wide range of tasks, such as calculating distances between objects, spawning actors, or playing sounds. They can also be used to create custom events that can be triggered by other parts of the Blueprint. By using Blueprint functions, you can create more complex and efficient Blueprints that are easier to understand and maintain.

Lets rebuild what we did in Vanilla C++ in Unreal.

<br>

---

##### `Step 1.`\|`UECPPFTC`|:small_blue_diamond:

Start a new UE5 5.2.X project.  Select the **Game** template tab and select **Blank**.  Make sure it is type **C++** as we will need to use C++ classes as well.  Select a **Target Platform** of `Desktop`, **Quality Preset** of `Maximum`, and no **Starter Content** and **Raytracing** is not necessary. Pick a **Directory** and select a **Project Name**, I used `UE5_CPP_FTC`.

If you have not already done so, you will need to set up visual studio and make sure you have all the components you need to compile the game.  Clear instructions are given on Unreal's [Setting up Visual Studio for Unreal Engine](https://docs.unrealengine.com/4.26/en-US/ProductionPipelines/DevelopmentSetup/VisualStudioSetup/).

![start a new C++ empty project called UE5_CPP_FTC](images/UE5CPPFTCProject.png)

![](../images/line2.png)

##### `Step 2.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: 

Again, we do not need a streaming large level so press **File | New Level** and select a **Basic** level.

![add basic level to game](images/NewLevel.png)

![](../images/line2.png)

##### `Step 3.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/saveLevel.png)

![](../images/line2.png)

##### `Step 4.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/bp_healthCounter.png)

![](../images/line2.png)

##### `Step 5.`\|`UECPPFTC`| :small_orange_diamond:

![alt_text](images/healthTextComponent.png)

![](../images/line2.png)

##### `Step 6.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond:

![alt_text](images/doDamageParamsReturn.png)

![](../images/line2.png)

##### `Step 7.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/defineFunction.png)

![](../images/line2.png)

##### `Step 8.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/delayDoDamage.png)

![](../images/line2.png)

##### `Step 9.`\|`UECPPFTC`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/playerHealthVar.png)

![](../images/line2.png)

##### `Step 10.`\|`UECPPFTC`| :large_blue_diamond:

![alt_text](images/doDamageToText.png)

![](../images/line2.png)

##### `Step 11.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: 

![alt_text](images/setText.png)

![](../images/line2.png)

##### `Step 12.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

![alt_text](images/dragBPHealthCounterIntoLevel.png)

![](../images/line2.png)

##### `Step 13.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/defaultPlayerStart.png)

![](../images/line2.png)

##### `Step 14.`\|`UECPPFTC`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

https://github.com/maubanel/UE5-CPP-Functions-Templates-Classes/assets/5504953/3ca43e93-6c6f-4e2f-8079-aae3b8e8ec3a

![](../images/line2.png)

##### `Step 15.`\|`UECPPFTC`| :large_blue_diamond: :small_orange_diamond: 

![alt_text](images/checkHealthAboveZero.png)

![](../images/line2.png)

##### `Step 16.`\|`UECPPFTC`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

![alt_text](images/falseBranchPath.png)

![](../images/line2.png)

##### `Step 17.`\|`UECPPFTC`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/addDeathMessage.png)

![](../images/line2.png)

##### `Step 18.`\|`UECPPFTC`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/playerIsDead2.png)



![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Unreal CPP Functions"> -->

![next up - ](images/banner.png)

![](../images/line.png)

| [previous](../vanilla-functions/README.md#user-content-vanilla-cpp-functions)| [home](../README.md#user-content-ue5-cpp-functions--templates--classes) | [next](../unreal-cpp-functions/README.md#user-content-unreal-capp-functions)|
|---|---|---|
