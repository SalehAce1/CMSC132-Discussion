12/8 Final Review I
===================

Reminders
^^^^^^^^^

    * 25 minute quiz today!

    * Final exam on Dec. 16

Materials
^^^^^^^^^

    * `Notes on Regex <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/labs/Week15/RegularExpressions.pdf>`_

    * `Regex example files <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/labs/Week15/RegularExpressionsExample.zip>`_


Finishing Regex 
^^^^^^^^^^^^^^^

We went through the rest of the regex slides. 

Final Review I
^^^^^^^^^^^^^^

Exam I content
~~~~~~~~~~~~~~
`Link to page <https://salehace1.github.io/CMSC132-Discussion/Oct-20.html>`_

Exam II content 
~~~~~~~~~~~~~~~
`Link to page <https://salehace1.github.io/CMSC132-Discussion/Oct-20.html>`_

Algorithmic Complexity
~~~~~~~~~~~~~~~~~~~~~~
This is a topic that can be tricky, so let's go over it.

    * First step is to identify the **critical section** of the code. Keep in mind that there can be multiple critical sections.

    * Next, loop for any loops that enclose the critical section. This is then used to check how many times the critical section runs.

    * Be careful about loop increments, as this is what determines how many times the loop runs.

    * A few common loops:

        * 1 to n incremented by i + 1 => loop executes n times

        * 1 to n incremented by 2 * i => loop executes log(n) times

Recursion
~~~~~~~~~
To write recursive algorithms, we can follow a few tips:

    * First, write the recursive method as if the method already outputs the correct value. This abstraction can help to first get a skeleton
      of the solution.

    * Next, think about what the base case(s) is/are. It is important to cover all possible base cases to avoid infinite recursion.

    * Last tip is to make sure that the recursive call includes some changing variable. This is what allows progress in the algorithm and is what will typically
      lead to a base case.

Linear Data Structures
~~~~~~~~~~~~~~~~~~~~~~

    * Linear Data Structures

        * Linked Lists: Objects that linearly connect to each other

            Doubly-Linked lists, dummy nodes, and circular linked list. 

        * Stacks: Lists that add/remove to the end

        * Queues: Lists that add to the end and remove from the front
        
Hashing
~~~~~~~

    * `Link to hashing review. <https://salehace1.github.io/CMSC132-Discussion/Nov-17.html?highlight=hash#hashing>`_

