10/19 Linked Lists
==================

Reminders
^^^^^^^^^

* Project 4 is due next Tuesday.

* Exam 2 is on Friday. 

Material
^^^^^^^^

* Simplified linked list slides `from here. <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week8/SimplifiedListImplementation.pdf>`_

* LinkedList `Java documentation. <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/LinkedList.html>`_

* Special iterator `Java documentation. <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/ListIterator.html>`_

Last Week Review
^^^^^^^^^^^^^^^^

Recursion
~~~~~~~~~
Algorithm that manages repetition by calling itself.
Each recursion algorithm has a **recursive case** that repeats and a 
**base case** that occurs once we do not wish to repeat.
While using iteration (loops) is typically more efficient, some problems
are easier to understand/implement recursively. 

**Tail Recursion** is a recursive algorithm that only recursively calls itself and no other function.
These are automatically turned into regular loops by the compiler. 

.. code-block:: Java

    // Non-tail Recursive
    int factorial(int n)
    {
        if (n==0) return 1;
        return n * factorial(n-1);
    }

    // Tail Recursion
    int factorial(int n, int ans)
    {
        if (n == 0) return ans;
        return factorial(n-1, n * ans);
    }

A **stack overflow** occurs when a recursive algorithm goes over the stack limit, typically due to an infinite recursion.

Linked Lists
^^^^^^^^^^^^

Dummy Nodes
~~~~~~~~~~~
First we went through the simplified linked list slides which demonstrated the 
use of a **dummy node**, a head node with no value that always exists at the start of
our linked list and does not change. By having such a node, we no longer have to write out
special cases that check or manipulate the head node.

.. warning::
    You cannot use dummy nodes in your project.

Java's LinkedList Class 
~~~~~~~~~~~~~~~~~~~~~~~
Java has its own Linked List library as a part of its Collections framework. 
A LinkedList is-a:

* Iterable (interface): Can be iterated over.

* Collection (interface): Collection of values.

* List (interface): Collection of ordered values that allows for duplicates. 

* Queue (interface): Collection that follows FIFO.

* Dequeue (interface): Collection that follows FIFO and LIFO.

.. figure:: resources/oct19/diag.png
   :scale: 50 %
   
   Figure 1: Diagram that depicts the relationship between the LinkedList class and other Collection classes. 

We went over the different methods within the Java documentation for LinkedList and ListIterator.
ListIterator allows for forward and backward traversal of a linked list.

.. note::
    Since LinkedList is a Dequeue and AbstractList, it implements methods from both Dequeue and ArrayList. 

Here's some example code:

.. code-block:: Java

    public class LinkedListDemo 
    {
        public static void main(String[] args) 
        {
            LinkedList<String> list = new LinkedList<>();
            list.add("B"); // Adds to the end of the list
            list.add("C");
            list.addFirst("A"); // Adds to the front
            list.addLast("D"); // Adds to the end
            list.addFirst("Z");
            System.out.println(list); // [Z, A, B, C, D]
            list.remove("D"); // Removes first instance of D
            list.remove(0); // Removes element at index 0
            
            System.out.println("Regular for each loop");
            for (String i : list)
            {
                System.out.println(i);
            }
            
            System.out.println("Backwards with descendingIterator method");
            Iterator<String> iter = list.descendingIterator();
            while (iter.hasNext())
            {
                System.out.println(iter.next());
            }
            
            System.out.println("Backwards with ListIterator");
            ListIterator<String> lstIter = list.listIterator(list.size());
            while (lstIter.hasPrevious())
            {
                System.out.println(lstIter.previous());
                // lstIter.next(); -> Creates infinite loop
            }
            
        }
    }

ArrayList vs LinkedList
~~~~~~~~~~~~~~~~~~~~~~~
LinkedLists have more functionality than ArrayLists but 
this comes at the cost of them being slower. This is mainly due to 
how LinkedLists are linear data structures (elements are seperate objects 
that must be traversed towards) where as Arrays are stored in a single chunk of
memory and can be accessed with O(1) operations.  
LinkedLists also consume more memory than ArrayLists. 