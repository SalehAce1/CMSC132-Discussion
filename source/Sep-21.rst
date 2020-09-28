9/21 Comparators
================

Reminders
^^^^^^^^^
* Your first exam is coming this Friday (Sep-25th)

* The second project was released last Thursday and is due Wednesday next week

Last Week Review
^^^^^^^^^^^^^^^^
Lecture covered more inheritance, debugging, and exceptions.

Abstract
~~~~~~~~
**Abstract classes** essentially allow us to make a class that cannot be instantiated. 
Use this when you wish to create an inheritance hierarchy where the parent cannot stand by itself
but it contains methods/fields that all of its children need to share.

For example, the *Shape* class is the parent of *Square* and *Circle* and it contains a method *draw()*.
Calling *draw()* on *Shape* does not make sense so we make it abstract while still allowing the children
to inherit and use the *draw()*.

**Abstract methods** are methods that do not have an implementation. 

Abstract vs. Interface Use
**************************
Use abstract classes when the class's children are directly linked in terms of implementation with each other
like in the case of *Shape* and its children.

Use interfaces when the classes implementing the interface don't need to be related to each other. For example,
a *MusicPlayer* class can implement the interface *Comparable* and a *Student* class can as well. The implementation of
*Student* and *MusicPlayer* are not related at all.

Inheritance vs. Composition
~~~~~~~~~~~~~~~~~~~~~~~~~~~
Inheritance should be used to create an *is a* relationship so for example, *Student is a Person*. 
On the other hand, **Composition** should be utilized when we want to say an object contains another object.
For example, *Student has a Phone* would occur when the *Student* class contains a *Phone* object within it.

.. note::
    Composition is less messy compared to inheritance so use it whenever possible.

Multiple Inheritance
~~~~~~~~~~~~~~~~~~~~
**Multiple Inheritance** is when a class has more than one parent. This is not allowed in Java.

.. note::
    You can achieve similar results to multiple inheritance by implementing (implementing multiple interfaces is allowed).

Final
~~~~~
The **final** keyword has three major use-cases. 

1. A final variable means that the variable is a constant

2. A final method cannot be overriden.

3. A final class cannot be extended. 

Exceptions
~~~~~~~~~~
**Run-time exceptions** happen when unexpected behavior occurs while your code is running.
For example, if your program divides by zero during a calculation it will throw an exception. 

When an exception occurs, the method or stack it occured in sends the exception to the previous
stack, this action is called **propagating**. If the exception propagates upto the main stack,
the program will crash. 

Handling Exceptions
*******************
Preventing an exception from reaching the main stack is called **handling the exception** or **catching** it.
We can use a try-catch to do this.

.. code-block:: Java

    try
    {
        // Tries the code here.
    }
    catch(ExceptionType e)
    {
        // If the code in try throws an exception of type ExceptionType...
        // ...the code here will run.
    }
    finally // Optional
    {
        // This block will run no matter what.
        // Use this if you have to do something no matter what happens.
        // For example, you might need to close an opened file. 
    }

Checked vs Unchecked
********************
**Unchecked exceptions** are all exceptions caused by bad code, you must fix these.

**Checked exceptions** are exceptions that are outside of your power. If you're reading a file,
there might be an *IOException*. Methods that can potentially cause this type of error require you to 
do one of two things. Either catch these potential errors with a *try and catch* or 
declare that the code may thrown an exception. 


Comparators
^^^^^^^^^^^
`Comparators <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Comparator.html>`_ are an interface in Java
that allow us to provide alternative ways of comparing the same class as opposed to the *Comparable* interface which only
allows for a single method for comparing. 

A class that implements *Comparator* requires a single method:

.. code-block:: Java

    public int compare(T a, T b)
    {
        // Return negative if a < b, 0 if a == b, positive if a > b
    }

So for example, if we want to sort *Students* based on their id in reverse order:

.. code-block:: Java

    class StudentComparator implements Comparator<Student>
    {
        public int compare(Student a, Student b)
        {
            // Note that I cannot directly access the id field.
            return b.getId() - a.getId(); 
        }
    }

.. note::
    Collections.sort has an overload that allows us to sort using the Comparator rather than the Comparable. 
    Looking at the above example, if we had an ArrayList of students *studList*, we could sort them with
    :code:`Collections.sort(studList, new StudentComparator());`. 

We spent the rest of class looking at `ComparatorCode.zip <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week4/ComparatorCode.zip>`_. 