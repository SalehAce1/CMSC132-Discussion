11/29 Heap Wksheet 
==================

Reminders
^^^^^^^^^

    * Quiz 4 this Wednesday!

Materials
^^^^^^^^^

    * `Heap exercise <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/labs/Week14/HeapExercise.pdf>`_

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
    t.join() // Stop current thread until thread t terminates 

Approach 2 to thread (preferred)
********************************
.. code-block:: Java

    // Implement the Runnable interface and give it to the thread
    Thread t = new Thread(() -> 
    {
        // Thread code
    });
    t.start(); // Begin thread
    t.join() // Stop current thread until thread t terminates 

Scheduler
~~~~~~~~~
The **scheduler** determines which **runnable** thread to run when **context switching** occurs.
**Non-preemptive scheduling** is a more manual type of thread management where context switching happens 
when a thread ends or volunteers to stop. **Preemptive** scheduling does thread management via the scheduler. 

:code:`t2.join()` causes the current thread to wait for the thread t2 to end before continuing. 

Use :code:`t2.interrupt()` to terminate thread t2, note that this only tells t2 that it should stop, t2 has to decide
when to stop on its own. 

Synchronization
~~~~~~~~~~~~~~~
A **Data Race** can occur when multiple threads concurrently attempt to access the same resource and
at least one of them tries to write to it. For example, if one thread is writing to a file but in the 
middle of writing, the thread is switched to another thread that wants to read the file, then this
new thread will not be reading the updated file. 

We use **synchronization** to protect sensitive parts of our code (**critical section**) from data races.
The :code:`synchronized(Object obj) {}` code block should be given an object that is shared
across the threads we want to sync. If a thread is inside the sync then other threads cannot
access the code in the sync until the thread leaves the sync block. 

.. code-block:: Java

    // this can be any object, in this case I used static to ensure
    // the lock is shared between all threads 
    static Object lockObj = new Object();

    public void run()
    {
        // non-sync part of code

        synchronized(lockObj)
        {
            // locked code where we access some resource
        }

        // non-sync part of code
    }

    // an entire method can be synchronized

    public synchronized void run()
    {
        // everything here is synced
    }

Overview of synchronization issues
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

    * Not sharing a lock object between threads 

    * Not covering the entirety of the critical section with a sync block

    * Locking a thread in a code block that requires another thread to do a certain action which cannot be done without the second thread getting into the code block as well (called a deadlock)

Heap Worksheet
^^^^^^^^^^^^^^
We went through the heap worksheet.