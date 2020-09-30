9/30 StringBuffer and Command Line
==================================

Reminders
^^^^^^^^^

* Project 2 is due **TONIGHT**.

* Project 3 will be released tomorrow.

* Debugging Quiz is next Monday/Wednesday.

    * Professor Sadeghian sent an email with specifics about the quiz.

    * You should have gotten an email from the TA that will test you with your quiz time.

    * **Have Driver.java in Eclipse open with the quiz project imported and be sure you are in the Java Perspective.**

    * **You may lose a lot of points if you do not have all of this done before the quiz starts.**

Material
^^^^^^^^

* Get the StringBuffer example code `from here. <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week5/TimeStrCode.zip>`_

* Get the Command Line Execution code `from here. <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week5/CommandLine.java>`_


String vs StringBuffer
^^^^^^^^^^^^^^^^^^^^^^
We are going to look at `TimeStrCode. <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week5/TimeStrCode.zip>`_
This is going to highlight the difference between Strings and StringBuffers, and show that StringBuffer is more efficient than String.

Command Line Execution
^^^^^^^^^^^^^^^^^^^^^^
We are going to now take a look at how to program in Java without using Eclipse.
Instead of Eclipse, we are going to use our command line.

To do this, download the file and then open up command line (Windows) or terminal (MacOS) or shell (Linux).

Basic Commands
~~~~~~~~~~~~~~

* **javac** is the command that compiles a .java file. This will create a .class file.

    * Format of the command : :code:`javac FILENAME.java`

* **java** is the command that runs the program.

    * Format of the command : :code:`java FILENAME args`

.. note::
    The FILENAME parameter does not include the file extension.
    Additionally, the args parameter is a list of arguments.
    (For CommandLine.java , args is a set of integers)
    Example: :code:`java CommandLine 1 2 3 4`

.. note::
    *args* represents the :code:`String[] args` in the main method header :code:`public static void main(String[] args)`

* **nano** is the command that opens a very basic editor to write code in your terminal.

    * Format of the command : :code:`nano FILENAME.java`
