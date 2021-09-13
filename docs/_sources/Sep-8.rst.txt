9/8 Debugging
=============

Reminders/Checkups
^^^^^^^^^^^^^^^^^^
* Can everyone access Piazza?

* Has everyone installed Eclipse?

* Quiz next week (Monday, the 13th of Sep)

    * 20 minutes long

    * At the beginning of discussion
    
    * You **must** go to your correct discussion to take the quiz

* Project questions?

Review
^^^^^^
* Abstraction: Give high level representation to user

    * Procedural: Hide algorithm detail behind action

    * Data: Hide how data is represented

* Classes versus Interfaces

    * Use interfaces to define a general template that you want shared across classes

    * Interface methods have only prototypes (with some exceptions)

* Generics --> List<T> lst

* Enumerated types

    * enum Color {Red, Green, Blue}

    * values(), valueOf(String s)

* boolean equals(Object other)

    1. Check if they share the same reference with ==

    2. Check if they are not the same type with instanceof

    3. Cast other to the correct type

    4. Compare

* Comparables

    * implements Comparable<ClassType>

    * int compareTo(T other)

    * Used in functions like Collections.sort()

    * In a.compareTo(b), function should return

        * Negative int if a < b

        * Positive int if a > b

        * 0 if a == b


Debugging
^^^^^^^^^

We went over the Debugging.zip file from the Schedule tab on the main site. 

Topics we covered were:

* Entering Eclipse's Debugging perspective

* Using step into, step over, and step return

* Setting breakpoints

* Seeing contents of variables after entering breakpoints

* Looking at the stack in the debugging menu

.. note::

    Quiz 2 (not the quiz 1 you are taking next week) will be on debugging in Eclipse.
