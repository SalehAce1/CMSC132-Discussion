11/8 Polymorphic Lists
======================

Reminders
^^^^^^^^^

* Project 5 is due Tuesday.

Material
^^^^^^^^

* `Code file <http://www.cs.umd.edu/class/fall2021/cmsc132-030X/labs/Week11/PolymorphicListsTreesCode.zip>`_

Last Week Review
^^^^^^^^^^^^^^^^
We learned about hashing last week.

Hashing
~~~~~~~
Hashing allows us to access a value in a list at O(1) time by using a **Hash Function**
to ideally turn each of the values of our list into a unique number. Depending on the hash
function, not all values will get a unique hash code, in which case, a **collision** occurs.
The best hash functions minimize collisions but in cases where they do happen, there are several
approaches that can be taken. 

A few approaches for handling collisions:

* **Open Addressing**: Look for another open spot on the table.

    * Linear probing: Place the value into the next open spot.

    * Quadratic probing: If at index k = j, go to index k + j^2, this prevents clustering.

* **Separate Chaining**: Each element can store multiple values. 

**Java's Hash Code Contract**: :code:`a.equals(b) => a.hashCode() == b.hashCode()` but the inverse and converse are not true. 

Polymorphic Linked List
~~~~~~~~~~~~~~~~~~~~~~~

This is a Linked List where instead of defining the end of a list using null, we will define it using a class
called :code:`EmptyList`. The structure of our code can be recursively defined as :code:`List = NoneEmptyList(data, List) or EmptyList`

.. note::
    This isn't the most efficient or best way to implement a Linked List. 
    This is meant to demonstrate how using polymorphism can reduce complexity of code. 


The rest of discussion was spent working through the code file. 
