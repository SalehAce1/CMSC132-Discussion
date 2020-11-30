11/30 Reflections
=================

Reminders
^^^^^^^^^

    * Project 7 due this Tuesday

    * Quiz this Wednesday

Materials
^^^^^^^^^

    * `Notes on Java Reflections <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week14/JavaReflections.pdf>`_

    * `Java Reflections example files <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week14/ReflectionLab.zip>`_


Review
^^^^^^

More Threads
~~~~~~~~~~~~

Volatile
********
When values are being processed, they can be copied into a cache for quicker recovery. 
While multithreading, a thread may try to use the old copy stored in the cache when 
another thread may have updated the real value in memory. To ensure this does not happen,
use the **volatile** keyword when declaring a variable. 

Wait and Notify
***************
When in a synchronization block, a thead can call **wait()** to release the lock and wait 
until another thread notifies that it can proceed. This notification can be done through
**lockObj.notify()** or **lockObj.notifyAll()** depending on whether we want to notify 
a single thread or all threads that are waiting on that lock object. 

Thread-safe
***********
**Thread-safe** code will handle synchronization for you and ensure that if multiple 
threads try to access and write to the code block, a data race will not occur. 


Java's Reflections
^^^^^^^^^^^^^^^^^^
We went through the powerpoint and example code found in the materials section. 

