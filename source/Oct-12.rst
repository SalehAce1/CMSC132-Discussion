10/12 UML
=========
Material
^^^^^^^^

* Get this lesson's slides `from here. <https://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week7/UMLIntro.pdf>`_

Review of Two Weeks Ago
^^^^^^^^^^^^^^^^^^^^^^^

Lambda Expressions
~~~~~~~~~~~~~~~~~~
These allow us to create anonymous classes on the fly without needing large blocks of code. 

If I wanted to create a comparator that helped sort my list of integers in reverse order, I would normally have to do the following:

.. code-block:: Java

    Comparator comp = new Comparator()
    {
        public int compare(int a, int b)
        {
            return b - a;
        }
    };

    Collections.sort(myList, comp);

Lambda expressions allow me to simplify all of that down to a single line:

.. code-block:: Java

    Collections.sort(myList, (a,b) -> b - a);

.. note::
    Lambdas only work with **functional interfaces**, interfaces with only one method within them.


Asymptotic Analysis
~~~~~~~~~~~~~~~~~~~
By measuring time complexity, we can determine the speed of our algorithm based on the number of steps it takes per
amount of input size.

Big-O Notation
**************
Big-O represents an upperbound for the time complexity of our algorithm as shown in figure 1.

.. figure:: resources/oct12/1.png
    :scale: 75
    
    Figure 1: Image demonstrates how the O(n) is a continuous function that will 
    always be greater than f(n) past a certain constant input size.

In Big-O notation, we do not care about constants and other low order terms that do not affect the end behaviour
of our time complexity as we go to very large input sizes. 
For example, a time complexity of n^2 + 3n + 1 gets simplified down to O(n^2).

.. figure:: resources/oct12/2.png
   :scale: 75 %
   
   Figure 2: You should know the order of different asymptotic complexity categories based on how quickly they each grow.

Given a table of input sizes and an algorithm's resulting number of steps, we can determine
the time complexity of our algorithm. 

.. figure:: resources/oct12/3.png
   :scale: 75 %
   
   Figure 3: The time complexity is log base 2 of n because as our input size doubles, the number of steps only increase by 1.

Best/Worst/Average Case
***********************
**Best case** is the smallest number of steps our algorithm takes to complete.
In an algorithm that searches through an array for a value by going through each element one by one,
the best case is when the first index it looks at has that value.

**Worst case** is the largest number of steps our algorithm takes to complete.
In the same example as above, the worst case is when the target value is located at the last element.

.. warning::
    Worst case and Big-O are not the same thing. There can only be one worst case but there are many upperbounds. 

**Average case** is the usual number of steps it takes for our algorithm to complete. Calculating the 
average case requires looking at the probability of how our input is distributed. 

**Amortized analysis** looks at the distribution of work based on input size. For example,
an algorithm may do more work every 10th step when compared to its other steps. 
Amortized analysis has been used to determine that doubling the size of an array is more efficient
than increasing it by one everytime we need to make the array larger.

UML
^^^
We went through the UML slides linked in the materials section. 

Once done, we drew a UML diagram for the exercise in figure 4.

.. figure:: resources/oct12/4.png
   :scale: 75 %
   
   Figure 4: Draw a UML diagram for this description.

.. figure:: resources/oct12/5.png
   :scale: 75 %
   
   Figure 5: One solution to the above problem.

