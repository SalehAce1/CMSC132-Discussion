10/13 UML Continued
===================

Reminders
^^^^^^^^^

* Project 4 was released yesterday (Tuesday)

Material
^^^^^^^^

* Get the exercise `from here. <http://www.cs.umd.edu/class/fall2021/cmsc132-030X/labs/Week7/DesignExercise.pdf>`_

Week 6 Lecture Review
^^^^^^^^^^^^^^^^^^^^^

Collections
~~~~~~~~~~~
We will take a look at the `slides <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/lectures/Week6/Collections.pdf>`_

Generics
~~~~~~~~

* Generic Programming is defining constructs that can be used with different data types

    * Example is ArrayList

* Generic Class is a class with one or more type variables

* When using a generic class, you must provide an actual type

.. code-block:: Java

    class ArrayList<E> { ... }

    ArrayList<Integer> alist = new ArrayList<Integer>();
    ArrayList<int> invalidList = new ArrayList<int>(); // INVALID!


.. code-block:: Java

    public class myGeneric<T> {
        private T value;

        public myGeneric( T v ) { 
            value = v; 
        } 

        public T getVal( ) { 
            return value; 
        }
    }


Be careful when using Arrays with Generic types.

.. code-block:: Java

    T [] data = new T[size]; // WRONG
    T[] data = (T[]) new Object[size]; // Need to cast


You can also specify what types are allowed for your class.

.. code-block:: Java

    public class Example < T extends Comparable <T> > { 
        T myVar; //For sure, T is a Comparable
    }

UML Exercise
^^^^^^^^^^^^

* Take some time to work on the UML exercise
