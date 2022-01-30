<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### More Const

<sub>[previous](../) • [home](../README.md#user-content-gms2-top-down-shooter) • [next](../)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Our default posture should be to ask yourself if this variable needs to be const or not.  Making a variable that is not supposed to change non-mutable is important.  So if you were to define Pi you would want it to be a const of `3.141592653589793`. Const gets tricky when we start using it on references and pointers and requires a bit more clarification. 

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

Now comment out that final failed attempt of a reference to a reference and put all the previous work within curly braces `{ ... }` so that it goes out of scope and open up a new scope to look at more on **const**.

![alt_text](images/PutPreviousOutOfScope.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

Lets create a `const int` which will create an unmutable **integer**. You get two error messages.  The second is that an expression must be modifiable lvalue.  It is not.  But the previous lines says that **++ needs 1-value**.<br><br>You might have noticed that **lvalues** and **rvalues** come up a lot in error messages.  To oversimplify an lvalue is an expression that can be on the left side of an assignment and an rvalue can be on the right side of an assignment.  So an lvalue represents an object that occupies a location in memory.  So when we have `const int` this is creates a unmutable `lvalue`.

![alt_text](images/AlterConstInt.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

To give you an example lets flip an lvalue and rvalue and see what happens. In this case it says that the **left operand must be a modifialbe lvalue**.  `4` is an prvalue (pure rvalue) of type integer.

![alt_text](images/FlipLvalueRvalue.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

The `const` initializer does not copy over.  So if we make a copy of a const integer then this copy is a mutable lvalue.  Try the below:

![alt_text](images/ConstNotCopiedAsLvalue.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

When using a const you need to assign the value and cannot leave it undefined.  Notice the error mentions `extern`.  This allows you to share a variable accross multiple files and is best to avoid to keep type safety.

![alt_text](images/MustInitConst.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond:

Comment out the un-initialized assignment and lets look at a `const int&` reference.  If we make a reference **const** then the object it is aliasing cannot be modified.  When we attempt we get an error. We see the **expression must be a modifiable lvalue** error.

![alt_text](images/ConstIntRef.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

But the const reference means we can't affect the object through the reference but if the object it is pointing to in not const you can alter the original variable.  Lets try it and you can see that it compiles.

![alt_text](images/ChangeRefToNonConst.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

 Now a pure rvalue of type integer of say the number `55` is a constant.  So if we have a reference, it needs to be a const reference.  Remove const from the below and see what error you get.  But this is a valid assignment.

![alt_text](images/ConstIntReference.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

 Again, lets look at another example where we try and take a const rvalue and assign it to a const lvalue and non-const lvalue.  You get a compile error.

![alt_text](images/NonConstFailedAssignment.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`SPCRK`| :large_blue_diamond:

This also applies to pointers. If we assign a **const float** then the pointer to that float HAS to be **const** as well.  Try assigning a non-const pointer and you get a compile error like below: 

![alt_text](images/ConstPointersAsWell.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: 

So if we have a non const variable the pointer to it can be const or not.  If we put const before the type then the object it is pointing to is constant.  That means that if we try and dereference the pointer and change it you will get a compiler error.

![alt_text](images/FloatConstObject.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>


##### `Step 12.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Now the pointer's memory though is not constant in this case.  It is still mutable.  That means we can change what object this pointer is pointing to.  So we can change the object from `F2` with value of `3.3` to `F` with a value of  `1.1`.

![alt_text](images/PointerItselfNotConst.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 13.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Compile, fix any errors and run the project.  You will see that we have succesfully reassigned what object this **const float** is pointing to.  We still can't dereference the pointer the know as the object that it is pointing to will keep its const-ness.

![alt_text](images/NonConstPointerReassigned.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 14.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

So with pointers you can see there is the pointer and the object is pointing to that can be const.  To make the pointer (or memory address it is holdihng) const you place it after the pointer like **type \* const**.


![alt_text](images/MakePointerConst.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 15.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: 

So in this case we cannot reassign the object this pointer `pF3` is pointing to.

![alt_text](images/CantReassigneConstMemory.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

Now you can see since `F2` was **non-const** and the pointer to the object is not **const** so we can change the underlying value.

![alt_text](images/NonConstObjectChanged.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 17.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Compile and run and see that we have changed the underlying value of `F2`.

![alt_text](images/ChangeF2RunProject.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 18.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

 We can make a pointer both const for the memory AND for the object it is pointing to.  In this case we have `const type * const` before the variable name making both constant.  Below we try changing the pointer unsucessfully.

![alt_text](images/ConstPointerConstObject.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 19.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Even though `F2` is not const `pF4` that points to an object is const so you can't dereference and change the object.  You will get a compile error.  This is the only way to make a pointer completely const.

![alt_text](images/DoubleConstWorksOnObject.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 20.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond:

The pointer is called a **top-level const** (type* const) and the object it is pointing to is considered a **low-level const** (const type*).<br><br>When we copy an object the **top-level consts** are ignored but the **low-level const** is never ignored. Below we were able to copy `const float* const pF4` into `pF6` even though **pF6** is missing the **top-level const**.  It should compile.

![alt_text](images/ConstCopyting.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 21.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

Now if we try and copy into `pF7` that is missing its **low-level const** gives a compiler error.

![alt_text](images/LowLevelConstError.jpg)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 22.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:

 Comment out the line so that the project can compile again!

![alt_text](images/.jpg)

___




<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - ADD NEXT PAGE">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [previous](../)| [home](../README.md#user-content-gms2-top-down-shooter) | [next](../)|
|---|---|---|
