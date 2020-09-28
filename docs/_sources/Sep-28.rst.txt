9/28 Singletons and Decorators
==============================

Reminders
^^^^^^^^^

* Project 2 is due Wednesday and your next project will be released on Thursday.

* Debugging quiz is coming next Monday/Wednesday.
    * Professor Sadeghian will email you about it today.

    * The TA that will test you, will email you your time soon.

    * **Have Driver.java in Eclipse open with the quiz project imported and be sure you are in the Java Perspective.**

    * You may lose a lot of points if you do not have all of this done before the quiz starts. 

Material
^^^^^^^^

* Get this lesson's slides `from here. <https://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week5/SingletonDecoratorPatterns.pdf>`_

* Get the example code `from here. <https://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week5/PizzaDecoratorCode.zip>`_


Last Week Review
^^^^^^^^^^^^^^^^
Last week you learned about nested types and some more Java constructs like cloning, garbage collection, and initialization blocks.

Nested Types
~~~~~~~~~~~~
Nested types allow us to have classes within other classes. We usually use them when we do not want a 
class to be accessable outside of another class and the nested class is only needed for a small part of our code. 

Inner class
***********
These are classes that are defined inside of an outer class. 
The inner and outer class can access each other's content freely. 
These nested types are useful when we need helper classes for a single class's implementation. 

.. code-block:: Java

    // outer class
    public class MyOuter
    {
        int x = 2;
        // inner class
        private class MyInner
        {
            int x = 6;
            // inner class method
            private void getX() 
            {
                int x = 8;
                System.out.println( x); // prints 8
                System.out.println( this.x); // prints 6
                System.out.println( MyOuter.this.x); // prints 2
            }
        }
    }

.. note::
    The inner class is connected to the outer class thus, outside of the outer class, 
    the inner class can only be accessed through the outer class. 

Static Nested Class 
*******************
Same as an inner class but static. 

Local Class
***********
A class within a block of Java code, for example, a method.  

.. code-block:: Java

    // outer class
    public class MyOuter
    {
        public Iterator someMethod()
        {
            class IteratorClass implements Iterator<Object>
            {
                @Override
                public boolean hasNext() 
                {
                    // Implementation
                }

                @Override
                public Object next() 
                {
                    // Implementation
                }
            };

            return new IteratorClass();
        }
    }

Anonymous Class
***************
A local class without a name, it must implement or extend a class. 

.. code-block:: Java

    // outer class
    public class MyOuter
    {
        public Iterator someMethod()
        {
            return new Iterator()
            {
                @Override
                public boolean hasNext() 
                {
                    // Implementation
                }

                @Override
                public Object next() 
                {
                    // Implementation
                }
        
            };
        }
    }


Cloning
~~~~~~~
Method used to create a copy of a class, by default, it does a shallow copy.
To override the :code:`clone()` method, first implement the **Cloneable** interface,
then redefine the clone method so that it returns a new copy of your object. 

.. code-block:: Java

    public class Student implements Cloneable
    {
        private int id;
        private Computer computer;

        public Student clone()
        {
            Student cpStud = new Student();
            cpStud.id = this.id;
            
            Computer cpComp = new Computer(computer.getModel()); 
            cpStud.computer = cpComp;

            return cpStud; 
        }
    } 

Initialization Blocks
~~~~~~~~~~~~~~~~~~~~~
These are used to initialize static and instance variables outside of the constructor.

.. code-block:: Java

    public class Foo
    {
        private static int A = 1;
        private int B = 2;

        // Static Initialization Block
        static
        {
            A = 5;
        }

        // Initialization Block
        {
            A = 10;
            B = 5;
        }

        public Foo()
        {
            A = 12;
            B = 13;
        }
    }


Rest of Class
^^^^^^^^^^^^^
We went over the singleton and decorator design patterns by looking at the slides and going through the examples. 