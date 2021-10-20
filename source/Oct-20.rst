10/20 Exam Review
=================

Reminders
^^^^^^^^^

* Project 4 is due next Tuesday.

* Exam 2 is **Friday**.

    * Find exam information `here. <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/exams/exam2/>`_


Exam Review
^^^^^^^^^^^

* Revisit 9/22 discussion page to look over concepts from Exam 1 (topics can carry over)

Nested Types
~~~~~~~~~~~~

* Slides for Nested Types are `here. <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/lectures/Week4/NestedTypes.pdf>`_


Lambda Expressions
~~~~~~~~~~~~~~~~~~

* A very concise approach to define an anonymous class instance.

* Lambda expressions are objects, and the compiler treats them as objects created from an anonymous inner class.

* Lambda expressions require a **functional interface**, which is an interface with only 1 abstract method.

.. code-block:: Java

    // Expressions syntax
    (type1 parameter1, type2 parameter2, ... ) -> expression
    // For example
    (int x, int y) -> x + y;

    // Statements syntax
    (type1 parameter1, type2 parameter2, ... ) -> {statements;};
    // For example
    (int x, int y) -> { return x + y; };

    // Additionally, you can leave out the types as the compiler can infer the type
    (x, y) -> x + y;

    // For just 1 parameter without an explicit type, you do not need parenthesis
    x -> x + 2;


Clone Method
~~~~~~~~~~~~

* Object class provides the :code:`clone()` method which provides shallow copying.

* To write the :code:`clone()` method for a particular class:

    * Call the Object class' :code:`clone()` method.

    * Any primitive types are taken care of by the Object's :code:`clone()` call.

    * Any fields that are not primitives/references to immutable objects need to be duplicated.

* **Covariant Return Type** - When you define the return type to be a subtype of the return type of the method being overriden.

* A class must implement the :code:`Cloneable` interface if it calls the Object class :code:`clone()` method.

* The :code:`CloneNotSupportedException` is thrown is a class calls the :code:`clone()` method but does not implement the interface.


Initialization Blocks
~~~~~~~~~~~~~~~~~~~~~

* Blocks of code used to initialize static and instance variables for a class.

* **Static Initialization Blocks** happen when the particular object is created (at the beginning of the call to the constructor).

* The order of initialization blocks goes Static -> Non Static -> Constructor

.. note::
    Static Initialization blocks are only executed once.
    So if you create more than 1 instance of the class,
    the static blocks only run the first time, but the other
    blocks run for every instance of the class.


.. code-block:: Java

    // Syntax for initialization blocks
    
    class Foo {
        static { A = 1; }

        { A = 2}
    }


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
