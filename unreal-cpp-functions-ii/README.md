![](../images/line3.png)

### Unreal CPP Functions II

<sub>[previous](../unreal-cpp-functions/README.md#user-content-unreal-app-functions) • [home](../README.md#user-content-ue5-cpp-functions--templates--classes) • [next](../macros/README.md#user-content-macros--blueprints)</sub>

![](../images/line3.png)

Chapter introduction here.

<br>

---

##### `Step 1.`\|`UECPPFTC`|:small_blue_diamond:


So back in **Rider** we comment out the prior line we used in **BeginPlay** and instead set a timer for 2 seconds out.  `GetWorld()` is a getter for the cached world pointer and will get us access to the actor in the current level (sort of like using a level blueprint). This is needed as a the concept of the timer is within a level and not within the actor blueprint.

So we call the PlayerIsHit function in **Begin Play**.  Then we need to uncomment out **PlayerIsHit()** and call oneself recursively every 2 seconds. This will mean that the player will get damage every 2 seconds, no matter what.

![recursive timer call](images/getTimerManager.png)

![](../images/line2.png)

##### `Step 2.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: 


Press the <kbd>Play</kbd> button and notice that we have the original function back from the blueprint version.  The only issue is that the timer goes below zero to negative number space.  Lets fix it.

https://github.com/maubanel/UE5-CPP-Functions-Templates-Classes/assets/5504953/11b18195-a838-4b85-a7c8-b49a8fa5e0fb

![](../images/line2.png)

##### `Step 3.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:


First, in the constructor we assign **DeadText** with teh string `"Player is Dead"`. This is the message we will use when the health goes below zero.

![assign DeadText](images/playerIsDeadText.png)

![](../images/line2.png)

##### `Step 4.`\|`UECPPFTC`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now open up **HealthCounter.cpp** and in **PlayerIsHit()**, and wrap the recursive function of doing damage then displaying the health string in a conditional statement check if `Health > 0`.  If not then set the text to the  **DeadText**.

![set dead text if health is less than zero](images/ifHealth.png)

![](../images/line2.png)

##### `Step 5.`\|`UECPPFTC`| :small_orange_diamond:

Press the <kbd>Play</kbd> button and notice that when the **Health** goes below zero we display "Player is Dead".

![play game to see dead text](images/playDeadText.png)



![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Macros & Blueprints"> -->

![next up - ](images/banner.png)

![](../images/line.png)

| [previous](../unreal-cpp-functions/README.md#user-content-unreal-cpp-functions)| [home](../README.md#user-content-ue5-cpp-functions--templates--classes) | [next](../macros/README.md#user-content-macros--blueprints)|
|---|---|---|
