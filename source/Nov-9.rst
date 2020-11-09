11/2 BST Worksheet
==================
Reminders
^^^^^^^^^

    * Project 5 is due today.

    * Project 6 will release today and is due next Wednesday.

Materials
^^^^^^^^^

    * `Today's Worksheet <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week11/BSTWorksheet.pdf>`_


Review
^^^^^^

Polymorphic BST
~~~~~~~~~~~~~~~
A binary search tree where instead of indicating the ends of the tree using null,
we use a class. This allows us to not have to check for null. While this isn't
the most efficient way of implementing a BST, it is a good way to learn about 
polymorphism.

We start out with a **Tree** interface that requires the implementation of typical tree methods
such as **insert()**. We will have an **EmptyTree** and a **NonEmptyTree** class that implement the
**Tree** interface. The implementation of the two classes will be different. For example, the **EmptyTree** 
won't have a left and right node as instance variables since it is empty but the **NonEmptyTree** will. 

.. note::
    Since our **EmptyTree** only ever needs a single instance, we can define and use single final instance
    of it as a **Singleton**.  


Class Worksheet
^^^^^^^^^^^^^^^
We split into groups and did the worksheet from the materials section. 