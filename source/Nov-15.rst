11/15 LL/Hashing Wks
====================

Reminders
^^^^^^^^^

    * Exam 3 this Friday.

Materials
^^^^^^^^^

    * `Today's Slides <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/labs/Week12/PolymorphicListsTrees.pdf>`_

    * `Today's Worksheet <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/labs/Week12/HashingListsSetWorksheet.pdf>`_

Review
^^^^^^

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

Complete Binary Trees
~~~~~~~~~~~~~~~~~~~~~
Complete Binary Trees are binary trees that have fullness in the internal nodes, and the leaves are as far left as possible.

Heaps
~~~~~
Heaps are Complete Binary Trees that can either be a **Minheap** or a **Maxheap**.

* **Minheap** is a heap where the value at the current node is less than or equal to the values in both subtrees.

* **Maxheap** is a heap where the value at the current node is greater than or equal to the values in both subtrees.

Heaps are **balanced trees**. This means that they minimize the height of the tree, where the height of the tree is **O (log n)**.

For Heap operations, reference `these slides. <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/lectures/Week11/HeapsPriorityQueues.pdf>`_

Polymorphic BST
^^^^^^^^^^^^^^^
A binary search tree where instead of indicating the ends of the tree using null,
we use a class. This allows us to not have to check for null. While this isn't
the most efficient way of implementing a BST, it is a good way to learn about 
polymorphism.

We start out with a **Tree** interface that requires the implementation of typical tree methods
such as **insert()**. We will have an **EmptyTree** and a **NonEmptyTree** class that implement the
**Tree** interface. The implementation of the two classes will be different. For example, the **EmptyTree** 
won't have a left and right node as instance variables since it is empty but the **NonEmptyTree** will. 

.. note::
    Since our **EmptyTree** only ever needs a single instance, we can define and use single final instance
    of it as a **Singleton**.  


Class Worksheet
^^^^^^^^^^^^^^^
We split into groups and did the worksheet from the materials section. 