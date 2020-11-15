11/16 RegEx
===========

Reminders
^^^^^^^^^

    * Your third exam is this Friday. 

    * Project 6 is due this Wednesday.

Materials
^^^^^^^^^

    * `Notes on RegEx <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week12/RegularExpressions.pdf>`_

    * `RegEx example files <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week12/RegularExpressionsExample.zip>`_


Review
^^^^^^

Threads
~~~~~~~
**Threading** is a technique used to give the illusion of parallelism such that it appears multiple processes are
being done at the same time. In reality there is a proccess called the **scheduler** that 
keeps track of the context of the task being processed and switches between different tasks to create multitasking.

Approach 1 to threading
***********************
.. code-block:: Java

    public class MyThread extends Thread
    {
        public void run()
        {
            // Thread task
        }
    }
    // ...
    MyThread t = new MyThread();
    t.start(); // Begin thread
    t.wait() // Stop current thread until thread t terminates 

Approach 2 to thread (preferred)
********************************
.. code-block:: Java

    // Implement the Runnable interface and give it to the thread
    Thread t = new Thread(() -> 
    {
        // Thread code
    });
    t.start(); // Begin thread
    t.wait() // Stop current thread until thread t terminates 

Regular Expressions
^^^^^^^^^^^^^^^^^^^
We went through the powerpoint and example linked at the start of this page. 