11/2 Maps
=========

Reminders
^^^^^^^^^

* Quiz 3 will occur on Wednesday and will be available from 9:00 am to 5:00 pm. A worksheet with more information can be found on the class webpage. 

Material
^^^^^^^^

* `Today's Worksheet <http://www.cs.umd.edu/class/fall2020/cmsc132/labs/Week10/MapsWorksheet.pdf>`_

Last Week Review
^^^^^^^^^^^^^^^^
We learned about maps, trees, and more algorithm complexity last week.

Maps
~~~~
**Maps** are a data structure that links a unique list of keys to different values,
allowing for O(1) access to these values. Think of a regular array and how it maps unique keys
(natural numbers) to values of our choice. Maps work the same way accept we choose the type of our keys. 
Since keys must be unique and can be unordered, we use the **Set** data structure to store them.

Like Sets, Maps come in three major types in Java as well. The **TreeMap** class holds a map 
with sorted keys, **LinkedHashMap** has its keys in insertion order, and **HashMap** has no order. 

Methods you should know:

    * :code:`void put(K key, V val)`

    * :code:`V get(Object key)`

    * :code:`int size()`

    * :code:`boolean containsKey(Object key)`

    * :code:`boolean containsValue(Object val)`

    * :code:`Set<K> keySet()`

    * :code:`Collection<V> values()`

Algorithm Complexity
~~~~~~~~~~~~~~~~~~~~
Given the following program, you should be able to state the time complexity and Big-O of the code.

.. code-block:: Java

    int i = 1;
    while (i < n)
    {
        someComputation();
        i = 2 * i; 
    }

T(n) = 1 + log(n) + log(n) => O(log(n))

Remember that **Big-O** is used to represent an upperbound of the time complexity, 
**Big-Omega** is used to represent the lowerbound, and finally, **Big-Theta** tells us that
our upperbound and lowerbound are equal asymtotically. 

Trees
~~~~~
**Trees** are a data structure made up of parents and children where every 
(parent) node can have several other (children) nodes coming out of it. 

Here's some terminology:

    * Root: The node that starts the tree (has no parent). 

    * Leaf or external: Nodes with no children.

    * Interior: Nodes with children.

    * Depth or level: Length of path from a node to the root. 

    * Height: Longest number of nodes to a leaf where the root is at height 0. 

**Binary Trees** are a special tree where every node can only have 2 or less node children.
There are a few types of them:

    * Degenerate: A tree where each interior node usually has only 1 child, turning the tree into a regular linked list. 

    * Balanced: A tree where each interior node usually has 2 children.

    * Full: A perfectly balanced tree where every interior node has 2 children. 

There are 4 major ways to go through a binary tree:

.. code-block:: Java

    // Gives nodes in order that lets us recreate exact tree
    void preorder(root)
    {
        // access root.data
        preorder(root.left)
        preorder(root.right)
    }

    // Gives nodes in order of values in a binary search tree
    void inorder(root)
    {
        inorder(root.left)
        // access root.data
        inorder(root.right)
    }

    // Good for deleting tree in language with no automatic garbage collection
    void postorder(root)
    {
        postorder(root.left)
        postorder(root.right)
        // access root.data
    }

    // Gives nodes in order of depth
    void depthorder(root) 
    {
        q.push(root)
        while (!q.isEmpty())
        {
            Node n = q.pop()
            q.push(n.left)
            q.push(n.right)
        }
    }

**Binary Search Trees** are trees where at each node, the left child is 
smaller than the parent and the right child is larger than the parent. 
This allows us to search for values in O(log(n)) time so long as the tree is balanced. 

The Rest of Class
^^^^^^^^^^^^^^^^^
We spent the rest of class working on the worksheet from the materials section. 