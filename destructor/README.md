<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Destructor

<sub>[previous](../) • [home](../README.md#user-content-gms2-top-down-shooter) • [next](../)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

A [destructor](https://en.cppreference.com/w/cpp/language/destructor) is a special function that is called when the object is no longer in scope and is destroyed. The purpose is for any functionality that is required like adapting to the change or freeing up resources.

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

Now what happens when a card is no longer is scope and is not in memory?  We have a problem, our static member will still show 4 cards.  There is a special function that is run when the class is destroyed.  It is the destructor special function for the class.<br><br>It is defined with the name of the class preceded by the `~` symbol.  This is the very last function to run before the object is de-allocated. It has the `virtual` keyword that we will get into later.

![alt_text](images/DeconstructorCardClass.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

 Now in the destructor definition all we need to do is subtract a card from the deck.

![alt_text](images/SubtractNumberOfCardInDestructor.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

All we need to do is to put curly braces `{}` around two of the cards and they will go out of scope and the destructor will run after **line 26** when those two objects go out of scope.

![alt_text](images/PutTwoCardsOutOfScope.jpg)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Compile and fix all errors.  Run the program and you will see that the destructor ran on **DisplayCard1** and **DisplayCard2** when they went out of scope (the memory is freed up when they go out of scope).  It subtracts `1` twicevand it is now only `2` cards left on the table (in memory).

![alt_text](images/RunCardsOutOfScope.jpg)

___


<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - ADD NEXT PAGE">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [previous](../)| [home](../README.md#user-content-gms2-top-down-shooter) | [next](../)|
|---|---|---|
