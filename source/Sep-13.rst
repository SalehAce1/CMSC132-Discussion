9/13/2021 Memory Maps and Quiz
==============================

Reminders
^^^^^^^^^
* We will be taking a quiz in the last 20 minutes of this class (make sure you are in the correct section)
* Project 1 is due this Wednesday
* Project 2 is released this Thursday

Material
^^^^^^^^

* Get the memory map examples from `here. <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/resources/memorymap.html>`_

Inheritance Review
^^^^^^^^^^^^^^^^^^

If a **Student** *is a* (or extends) **Person**, then that means the **Student** will inherit all fields and methods of its parent, **Person**. 
Inside of the **Student** class, we use the keyword *super* to refer to the parent. Remember that when we initialize a child class, its parent's constructor
is run first, then the child's constructor.

.. note::
    The Object class is at the top of the inheritance hierarchy and includes methods such as toString() and equals(Object o).

Overriding
~~~~~~~~~~

We can *override* a method a child inherits from a parent thus redefining how it functions within the child. 
Do this by adding the method with the same exact name and parameter types in the child.

.. warning::
    Do not mix up *overriding* (redefining an inherited method) and *overloading* (having multiple versions of the same method distinguished by parameter difference).

Private and Protected
~~~~~~~~~~~~~~~~~~~~~
While *private* methods are inherited, they cannot be accessed from the child. We can use the *protected* keyword to allow 
a class's children to access its fields without giving access to other classes.

Early and Late Binding
~~~~~~~~~~~~~~~~~~~~~~
.. code-block:: Java

    // Assume Student extends Person
    Student sid = new Student(132);
    Person p = sid;
    // Does p.toString() run Student's version or Person's version?
    System.out.println(p.toString());

*Early binding* is when we choose which method is run based on what the variable is declared as (p is declared as **Person**)
and not what it actually is (p is more specifically a **Student**). 

*Late binding* (which Java uses) is when we run the version of the method based on the class it really is, in this case, **Student**.
Late binding means that we can store an array of different classes under the same parent method.

getClass() and instanceof
~~~~~~~~~~~~~~~~~~~~~~~~~
:code:`a.getClass()` returns the class of object "a". :code:`a instanceof ClassType` checks whether "a *is a* ClassType".

Upcast and Downcast
~~~~~~~~~~~~~~~~~~~
Upcasting is going from a child to a parent, Java does this automatically. Downcasting is going from a parent to a child. 
This must be done manually and Java will break if one attempts to cast a parent to a child it does not have.

.. note::
    Use *instanceof* to check whether downcasting is safe. 


Memory Maps
^^^^^^^^^^^
We looked at the pdf linked at the start.

Quiz Time!
^^^^^^^^^^