11/1 Quiz 3 Practice
=====================

Reminders
^^^^^^^^^

* Quiz 3 this Wednesday.

Material
^^^^^^^^

* `Quiz file. <http://www.cs.umd.edu/class/fall2021/cmsc132-030X/projects/zipFiles/lab/LLlab.zip>`_

* `Quiz description. <http://www.cs.umd.edu/class/fall2021/cmsc132-030X/labs/Week10/LLlab.pdf>`_


Last Week Review
^^^^^^^^^^^^^^^^
We learned about IO.

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


Quiz Review
~~~~~~~~~~~
We worked on the example quiz as practice for the upcoming quiz.
