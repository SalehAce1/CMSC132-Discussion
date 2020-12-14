12/14 Review II
===============

Last Week Review
^^^^^^^^^^^^^^^^

Sorting Algorithms
~~~~~~~~~~~~~~~~~~
Let's look at the slides for `Sorting Algorithms. <https://www.cs.umd.edu/class/fall2020/cmsc132/lectures/Week15/Sorting.pdf>`_

Algorithm Stratigies
~~~~~~~~~~~~~~~~~~~~
Let's look at the slides for `Algorithm Strategies. <https://www.cs.umd.edu/class/fall2020/cmsc132/lectures/Week15/AlgorithmStrategies.pdf>`_

Effective Java
~~~~~~~~~~~~~~
Let's look at the slides for `Effective Java. <https://www.cs.umd.edu/class/fall2020/cmsc132/lectures/Week15/EffectiveJava.pdf>`_

Final Review
^^^^^^^^^^^^
Here is the `list of topics. <http://www.cs.umd.edu/class/fall2020/cmsc132/exams/final/>`_
Keep in mind, the exam will not heavily cover threading. Additionally, there will be emphasis on recursion, so practice writing recursive solutions and
review recursive problems from quizzes/projects.

Generics
~~~~~~~~
To define generic classes, make whatever variable can take on different types a generic type, and adjust methods/instance variables to reflect this.

Algorithmic Complexity
~~~~~~~~~~~~~~~~~~~~~~
This is a topic that can be tricky, so let's go over it.

    * First step is to identify the **critical section** of the code. Keep in mind that there can be multiple critical sections.

    * Next, loop for any loops that enclose the critical section. This is then used to check how many times the critical section runs.

    * Be careful about loop increments, as this is what determines how many times the loop runs.

    * A few common loops:

        * 1 to n incremented by i + 1 => loop executes n times

        * 1 to n incremented by 2*i => loop executes log(n) times

    * We can look back at the `slides <http://www.cs.umd.edu/class/fall2020/cmsc132/lectures/Week9/AlgorithmicComplexityII.pdf>`_ to practice.

Recursion
~~~~~~~~~
To write recursive algorithms, we can follow a few tips:

    * First, write the recursive method as if the method already outputs the correct value. This abstraction can help to first get a skeleton
      of the solution.

    * Next, think about what the base case(s) is/are. It is important to cover all possible base cases to avoid infinite recursion.

    * Last tip is to make sure that the recursive call includes some changing variable. This is what allows progress in the algorithm and is what will typically
      lead to a base case.

For other information on `recursion, look here. <https://salehace1.github.io/CMSC132-Discussion/Nov-18.html#Recursion>`_

Graphs
~~~~~~
This is a topic that wasn't covered on the last exam, so be prepared to get questions about graphs.

    * **Dijkstras Algorithm** - An algorithm for a weighted, directed graph that allows us to find the shortest path from any single vertex to all other (reachable) nodes.

    * **Breadth First Traversal** - A traversal technique that utilizes a queue data structure to keep track of nodes that need to be vistited.

    * **Depth First Traversal** - A traversal technique that utilizes a stack data structure to keep track of nodes that need to be vistited.

To look at traversal examples, open these `slides. <https://www.cs.umd.edu/class/fall2020/cmsc132/lectures/Week14/GraphsTraversal.pdf>`_
To look at Dijkstras Algorithm, open these `slides. <https://www.cs.umd.edu/class/fall2020/cmsc132/lectures/Week14/DijkstrasAlgorithm.pdf>`_
To look at a Dijkstras Algorithm example, open these `slides. <https://www.cs.umd.edu/class/fall2020/cmsc132/lectures/Week14/DijkstrasExample.pdf>`_

Other
~~~~~
For the rest of today's lab, we can cover any topics by looking at slides/previous notes pages.

    * `Exam 1 Topics <https://salehace1.github.io/CMSC132-Discussion/Sep-23.html>`_

    * `Exam 2 Topics <https://salehace1.github.io/CMSC132-Discussion/Oct-21.html>`_

    * `More Final Review <https://salehace1.github.io/CMSC132-Discussion/Dec-7.html>`_