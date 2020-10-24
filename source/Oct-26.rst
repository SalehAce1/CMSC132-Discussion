10/26 Networking
================

Reminders
^^^^^^^^^

* Project 4 is due tomorrow.

Material
^^^^^^^^

* `Networking Slides <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week9/Networking.pdf>`_

* `Packet Switching Video <https://youtu.be/vSlcoQowe9I>`_

* `Networking Project File <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week9/NetworkingCode.zip>`_

Last Week Review
^^^^^^^^^^^^^^^^
We learned about IO and and hashing last week.

Java IO
~~~~~~~
Files can be encapsulated using the **File** class: :code:`File f = new File("file_path");`

Read from the file using:

* **FileReader**: read() reads a character or -1 if at the end of stream.

* **BufferedReader**: readLine() reads a line from the file.

* **Scanner**: Seperates file by whitespaces, use next(), nextInt(), and others to read through it. 

Write to the file using:

* **FileWriter**: write(int c) writes a character into the file.

* **BufferedWriter**: write(String str) writes a string into the file efficiently.

**Standard I/O**: :code:`System.in`, :code:`System.out`, and :code:`System.err` give
us access to the standard input and output streams. We use System.out to print to the
output stream and System.in to take input from the input stream using the Scanner class. 

Hashing
~~~~~~~
Hashing allows us to access a value in a list at O(1) time by using a **Hash Function**
to ideally turn each of the values of our list into a unique number. Depending on the hash
function, not all values will get a unique hash code, in which case, a **collision** occurs.
The best hash functions minimize collisions but in cases where they do happen, there are several
approaches that can be taken. 

A few approaches for handling collisions:

* **Open Addressing**: Look for another open spot on the table.

    * Linear probing: Place the value into the next open spot.

    * Quadratic probing: If at index k = j, go to index k + j^2, this prevents clustering.

* **Separate Chaining**: Each element can store multiple values. 

**Java's Hash Code Contract**: :code:`a.equals(b) => a.hashCode() == b.hashCode()` but the inverse and converse are not true. 


Networking
^^^^^^^^^^
We went over the networking slides and the example project. To run the example, be sure to 
run WisdomServer before WisdomClient otherwise the client doesn't have anything to connect to. 

.. note:: 
    If the error :code:`java.net.BindException: Address already in use: bind` occurs, the port
    you are trying to use is already in use. 
