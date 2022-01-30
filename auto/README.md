<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Auto

<sub>[previous](../) • [home](../README.md#user-content-gms2-top-down-shooter) • [next](../)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Sometimes, we might know the type of the object we are pointing to.  C++ has a keyword `auto` that will deduce the type for us.  Lets take a look.

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

We can deduce type at runtime.  Sometimes we don't know the exact type of the object we are trying to access.  The `auto` keyword lets the initializer determine the type.  So if we add two **integers** together the resulting variable would derive to **int**.  

![alt_text](images/autoKeyword.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

Prove it by running the program and seeing what type is derived by `auto`:

![alt_text](images/ProveAutoToInt.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Be careful when you are mixing types. It is not immediately obvious to what type it will resolve to with the `auto` keyword.  Try and guess what type `S` will be?

![alt_text](images/BeCarefulWithMixedTypes.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Did you guess that this value is with **int** and 2 **floats** resolved to a float?  Well it did...

![alt_text](images/DidYouGuessFloat.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

The `auto` keyword ignores **top-level const**. Lets look at an example of what a const pointer const type looks like.

![alt_text](images/AutoIgnoresTopLevelConst.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond:

 When we look at the type it only shows us the **low-level const**.

![alt_text](images/ConstConstTypeDebugger.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

But notice that the **top-level** const holds as you can't reassign the pointer to another object of the same type.

![alt_text](images/TopLevelConstHolds.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now lets look at what happens with `auto`.  It does not copy the **top-level** const.  Lets let `auto pJ = pI` and see what happens.

![alt_text](images/AutoDoesntCopyHighLevel.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

 When you run it, it looks the same as before without showing the **top-level** const.

![alt_text](images/StillLeavesOffTopLevelConst.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`SPCRK`| :large_blue_diamond:

Now we can reassign the pointer to another object as **auto** did not in fact copy the **top-level const**.

![alt_text](images/ProvesDidntCopyConst.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: 

We can also force `auto` to a **low-level const**.  If we declare `const auto` then that variable will be const regardless of the type on the right hand side of the `=` sign.  Now we have an `int K` that is not const.  But if we assign it to `const auto L` lets see if it is const?

![alt_text](images/MakeAutoConst.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>


##### `Step 12.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Run it, and you see that the type is deduced to **int**. [In all cases, cv-qualifiers are ignored by typeid](https://en.cppreference.com/w/cpp/language/typeid#Explanation).  This means that the constness of literals will not be shown. On the next page we will prove that it is const.

![alt_text](images/TypeInt.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 13.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

 Now try and change `L` and you will see that `const auto` forced the consteness on `L`.  You get a compile error.

![alt_text](images/ConstAutoWorked.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 14.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Now literal expressions on the right hand side are **const expressions**. We know their value at compile time and would apply to build in types (5, 1.2f, 'f').  

![alt_text](images/ConstLiterals.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 15.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: 

 Lets just send the literal expression to `typeid`.

![alt_text](images/5LiteralOutput.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

 Run it and as before you will not see the constness of the integer using `typeid` as previously mentioned.

![alt_text](images/LiteralConstMissing.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 17.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

You can also force an `auto` to be a reference instead of a unique copy.  If you declare `auto&` before the variable name it will make it a reference to the type of the object that is derived. Try making a reference to `J` and use `auto` to derive the type.

![alt_text](images/MakeAutoReference.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 18.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

For a reference **typeid** returns the type of the object it is refering to, so you don't know that this variable is an alias with this method.

![alt_text](images/RefShowsTypeOfRef.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 19.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Prove that `rJ` is a reference.  Lets change the value to `30`.  This should change the underlying value of **int J** from `10` to `30` through reference **rJ**. 

![alt_text](images/ProveReference.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 20.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond:

Run the project and you will see that the reference worked as the original value of `J` has changed through the reference whose type was derived through `auto`.

![alt_text](images/RefChangedRun.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 21.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

You can also do the same thing with pointers.  We can force the auto to be a pointer to that type by using `auto *`.

![alt_text](images/ForceAutoToPointer.jpg)

![alt_text](images/RefChangedRun.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 22.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Run the project and you will see that it is a **int \* __ptr64**.  Please remember that this is going to change if we were on a different platform.  It might be on a 32 bit machine and thus a different type.

![alt_text](images/intpointer.jpg)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 23.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Lets triple check and dereference `pJ2` and set it to `50`.  Then output the original value of `J` again.

![alt_text](images/DoubleCheckPointer.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 24.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Run the game and notice that `J` was changed through the dereferenced point to `50`.

![alt_text](images/PointerChangedRun.jpg)

___


<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - ADD NEXT PAGE">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [previous](../)| [home](../README.md#user-content-gms2-top-down-shooter) | [next](../)|
|---|---|---|
