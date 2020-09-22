9/23 Exam Review
================

Reminders
^^^^^^^^^
* Your first exam is coming this Friday (Sep-25th)

* Project 2 (Webpage Generator) was released last Thursday and is due Wednesday 9/30

Exam Logistics
^^^^^^^^^^^^^^
* Will be posted on Friday 9/25 at 9 AM and due Friday Sep 25 at 5 PM

* NO LECTURE VIDEO ON FRIDAY 9/25

* Normal OH on Friday 9/25 but TAs CANNOT answer exam questions

* Make sure you have correct version of Eclipse, Java 13, course management software

* Exam will be similar to a project (write code in Eclipse and submit)

* Piazza is for CLARIFICATION questions

* Do not reply to other students' questions regarding the exam

* DO NOT POST CODE ON PIAZZA

* Open note/lecture


Exam is made up of 2 sections:

1. Short answer questions (multiple choice, true/false, fill-in-the-blank)

2. Code writing (write code to solve a problem)

Exam Review
^^^^^^^^^^^

OOP Principles
~~~~~~~~~~~~~~
**Abstraction** : Practice of providing high-level model of activity/data (WHAT not how)

* **Procedural Abstraction** : Provide action to be performed but hide algorithm (ex. Sorting an array but not saying what sorting algorithm was used)

* **Data Abstraction** : Specify data objects for problem but hide representation (ex. List of names instead of ArrayList<String>())

**Encapsulation** : Design technique that calls for hiding implementation details while providing an interface (methods) for data access

* Making things private is an example of this, because to users, the implementation details are hidden but methods allow for access to private data

Testing
~~~~~~~
JUnit Tests

* assertTrue(...), assertEquals(...), assertFalse(...)

.. code-block:: Java

    @Test
    public static void studentTest1() {
        int expectedResults = 5;
        int result = 7;
        /* Note that there is no assertion but this test still passes */
    }

    @Test
    public static void studentTest2() {
        int expectedResults = 10;
        assertEquals(expectedResults, 10);
        assertTrue(true);
        /* Multiple assertion statements are OK */
    }

Java Constructs
~~~~~~~~~~~~~~~

* **this** keyword refers to the current object

* **public** is visible to any class

* **private** is visible only within scope (within the class)

* **package** is visible within the package

* **protected** is visible to class & subclasses

* **Interface** is an abstract type in Java that ensures classes that **implement** the interface define certain methods

* **StringBuffer** -> just be familiar with append(String s) method as well as constructor

* **Array** -> fixed size

* **ArrayList** -> get(int index), remove(int index), constructor

* **Method Overloading** is having multiple methods with the same name, but different number/types of parameters

* **Method Overriding** is when a subclass "redefines" a method in a parent class

* **Autoboxing** is conversion from primitive type to corresponding wrapper class *ex)* int x -> Integer x

* **Unboxing** is conversion from wrapper class to corresponding primitive type *ex)* Double x -> double x

* Enhanced for loop

.. code-block:: Java

    /* Suppose you have an ArrayList of Strings arr */
    for(String s : arr) {
        /* Code */
    }

Enumerated Types
~~~~~~~~~~~~~~~~

* A set of fixed values

.. code-block:: Java

    public enum Color { Red, Green, Blue }
    /* Very simple enumerated type */

Equals
~~~~~~

.. code-block:: Java

    public boolean equals(Object obj) {
        if (obj == this) {
            return true;
        }
        if (!(obj instanceof A) {
            return false;
        }
        A a = (A) obj;
        /* Write code to compare this object to the object passed in parameter */
    }

Interfaces
~~~~~~~~~~
* **IS A** relationship -> *ex)* Dog **IS A** Animal

* **implements** keyword establishes the IS A relationship

.. code-block:: Java

    public class Dog implements Animal {
        /* This is how you define a class that implements an interface */
        /* Animal is an interface that may have methods that need to be implemented in the class Dog */
    }

Comparable vs Comparator
~~~~~~~~~~~~~~~~~~~~~~~~
* **Comparable** is an interface that has **compareTo(T obj)** method

* **Comparator** is an interface that has **compare(T obj)** method

* Both need to specify <T> the object type

Iterator & Iterable
~~~~~~~~~~~~~~~~~~~
* Both Iterator<T> and Iterable<T> are interfaces

* **Iterable<T>** has only 1 mandatory method that needs implementation : **Iterator<T> iterator()**

* **Iterator<T>** is another interface that has 2 mandatory methods : **boolean hasNext()** and **E next()**

This is generally how implementation of this would look like:

.. code-block:: Java

    public class Roster implements Iterable<Student> {
        public Iterator<Student> iterator() {
            /* There can be other methods for the Roster class */
            /* We will focus on the ones for Iterable and Iterator */

            return new Iterator<Student>() {
                public boolean hasNext() {
                    /* Code to check whether the roster has another student left */
                }

                public Student next() {
                    /* Code to return the next available student in the roster */
                }
            }
        }
    }

Inheritance
~~~~~~~~~~~
* **super** keyword refers to the parent class

* **IS A** relationship -> *ex)* Student **IS A** Person

* **extends** keywork establishes the **IS A** relationship

.. code-block:: Java

    public class CockerSpaniel extends Dog {
        /* This is how you establish an inheritance relationship */
        /* CockerSpaniel IS A Dog */
    }

* Constructor of subclass needs to have **super** call first
