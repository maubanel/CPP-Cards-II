<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Decltype

<sub>[previous](../) • [home](../README.md#user-content-gms2-top-down-shooter) • [next](../)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

We have another way of deriving type.  We have `decltype()` that returns the type of what is passed to it.  Lets look at a few examples. 

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

 `decltype(type)` derives the type to what is passed within parenthesis.  In this case it derives from `K` a **const int**. 

![alt_text](images/DecltypeOnInt.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

The type is derived by `decltype()` and is the same as `K` an **integer**. Again we can't see the const-ness.

![alt_text](images/DerivedType.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

So to test whether the const got carried by the **decltype()** lets try and increment this new variable.  We get a compiler error saying that it is const.

![alt_text](images/XisStilLConst.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now we can also pass a literal expression and have **decltype()** derive the type.  So in this case we pass a float literal to **decltype()**.  To make it trickier, we are passing it an integer.

![alt_text](images/FloatDeclType.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

So sure enough it did derive the type as a **float**.

![alt_text](images/QIsFloat.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond:

 Now you can also use **decltype** to derive the return type of a function.  Lets create a simple function to see it in practice that returns a **char**.

![alt_text](images/FunctionReturnsChar.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

So now we are determining the type of `Ch` with the return type of the function `ReturnQ()`.

![alt_text](images/CharReturnDeclType.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now when you run it you see that it correctly derived the type **char** from the return of the function. Next up we will apply these concepts in Unreal engine in our small card class.

![alt_text](images/ChAsChar.jpg)


___


<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - ADD NEXT PAGE">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [previous](../)| [home](../README.md#user-content-gms2-top-down-shooter) | [next](../)|
|---|---|---|
