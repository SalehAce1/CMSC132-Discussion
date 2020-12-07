12/7 Review I
=============

Last Week Review
^^^^^^^^^^^^^^^^

Graphs
~~~~~~
Graphs are a data structure that connect multiple **nodes**/**vertices** together through **edges**.
Edges can be directional or not directional. A graph with **cycles** has a path that returns to 
connects a vertex to itself at one point. 

**Weighted** edges are edges that have some cost 
associated to them. Every vertex in a **connected** graph has a path to reach every other vertex.

Breadth First Search
********************
From some starting vertex A, visit all of A's neighbors then once done, visit each of A's neighbors' neighbors, and so on. 

Depth First Search
******************
From some starting vertex, go through a path of vertices until you reach the end, then backtrack
until we reach a second path. Repeat until done. 

Tips for Traversal
******************

    * Avoid revisiting nodes by keeping a HashSet of all visited nodes. 

    * For BFS, use a queue data structure to keep track of which vertex you should visit next.  

    * For DFS, use a stack data structure to keep track of which vertex you should visit next. 


Graph Implementation
********************

One approach is through an **adjacency matrix** which is a 2D array of booleans which tell us
whether two nodes have an edge. This is faster when we have dense graphs.

Another approach is the **adjacency list** which is a list of all the vertices where each element
is a list of that node's neighbors. This is faster when we have sparser or less dense graphs. 


Dijkstras' Algorithm
~~~~~~~~~~~~~~~~~~~~

Given a directed, weighted graph, **Dijkstras' algorithm** allows us to find the shortest path
from some starting vertex to any other node. The powerpoint visualizes how this algorithm works
very well so look at that. 

Final Review
^^^^^^^^^^^^

    * Linear Data Structures

        * Linked Lists: Objects that linearly connect to each other

            Doubly-Linked lists, dummy nodes, and circular linked list. 

        * Stacks: Lists that add/remove to the end

        * Queues: Lists that add to the end and remove from the front

    * `Hashing <https://salehace1.github.io/CMSC132-Discussion/Oct-26.html?highlight=hash#hashing>`_

    * `Sets and Maps <https://salehace1.github.io/CMSC132-Discussion/Nov-18.html#sets-maps>`_

    * `Trees <https://salehace1.github.io/CMSC132-Discussion/Nov-2.html?#trees>`_

        * `Heaps <https://salehace1.github.io/CMSC132-Discussion/Nov-11.html#heaps>`_
    
        * Priority Queues

    * `Multithreading <https://salehace1.github.io/CMSC132-Discussion/Nov-16.html#threads>`_

        * `Synchronization <https://salehace1.github.io/CMSC132-Discussion/Nov-23.html#threads>`_

        * `More Threads <https://salehace1.github.io/CMSC132-Discussion/Nov-30.html#more-threads>`_
