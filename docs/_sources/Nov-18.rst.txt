11/18 Exam Review
=================

Reminders
^^^^^^^^^

    * Project 6 is due **TONIGHT**.

    * Third Exam is on Friday 11/20.

Exam Logistics
^^^^^^^^^^^^^^

    * Find Exam info page `here. <http://www.cs.umd.edu/class/fall2020/cmsc132/exams/exam3/>`_

    * Exam will be posted on Friday at 9 AM and will be due 5 PM.

    * No lecture video will be posted for Friday.

    * TAs will hold normal OH on Friday, but questions about the exam **WILL NOT** be accepted.

    * The exam is open note.

Exam Review
^^^^^^^^^^^

* Revisit 10/21 and 9/23 discussion notes to look over concepts from prior exams

Recursion
~~~~~~~~~

* Recursion is an approach to solve a problem by creating a method that has a call to itself within the body of the method.

* **All** iterative solutions can be rewritten as recursive solutions because iteration is simply a special case of recursion: **tail recursion**.

    * **Tail recursion** occurs when the method has a recursive call as its final action and no additional processing.

.. code-block:: Java

    // Example of a tail recursive method
    int factorial(int n, int partialResult)
    {
        if (n == 0)
        return partialResult;
        return factorial(n - 1, n * partialResult);
    }

    // Written iteratively
    int factorial(int n, int partialResult) 
    { 
        while (n!= 0)
        {
            partialResult = n * partialResult; n = n - 1;
        }
        return partialResult;
    }

Memory Maps
~~~~~~~~~~~

* These maps have a space for the stack and a space for the heap.

* We can look at some examples.

Linear Data Structures
~~~~~~~~~~~~~~~~~~~~~~

* These data structures include Linked Lists, Stacks, Queues, etc.

* Let's look at the slideset to review `Linked Lists <https://www.cs.umd.edu/class/fall2020/cmsc132/lectures/Week6/LinearDataStructures.pdf>`_

* You want to know how to make iterative and recursive methods for Linked Lists.

* Iterative solutions will use references to previous/current Node(s) to move through the Linked List.

.. code-block:: Java

    // Suppose you only need to modify one element
    public void methodX(T targetData)
    {
        Node curr = head;

        while (curr.data != targetData && curr.next != null)
        {
            curr = curr.next;
        }

        // Process node here
    }

    // Suppose you want to delete an element. In that case, you need to also keep track of the previous Node.
    public void methodY(T targetData)
    {
        Node curr = head;
        Node prev = null;

        while (curr.data != targetData && curr.next != null)
        {
            prev = curr;
            curr = curr.next;
        }

        // Process node here
    }

* Recursive solutions will often times utilize auxiliary methods that take in an additional parameter representing the head of the current section of the Linked List.

.. code-block:: Java

    public void methodZ(T targetData)
    {
        methodZAux(head, targetData);
    }

    private void methodZAux(Node headAux, T targetData)
    {
        if (headAux.data = targetData)
        {
            // Process node here
        }
        else
        {
            methodZAux(headAux.next, targetData);
        }
    }

* Some tips for writing recursive solutions for Linked Lists:
    
    * Be deliberate about what your return types are, these can make the solution easier.

    * Keep track of what the possible base cases are. **MAKE SURE THERE IS NO INFINITE RECURSION**.

    * Begin writing your solution as if the recursive method already performs the correct work. This can simplify the thought process and make it clear what code needs to be written.

Hashing
~~~~~~~
Collision Handling:

* **Open Addressing**: Look for another open spot on the table.

    * Linear probing: Place the value into the next open spot.

    * Quadratic probing: If at index k = j, go to index k + j^2, this prevents clustering.

* **Separate Chaining**: Each element can store multiple values. 

**Java's Hash Code Contract**: :code:`a.equals(b) => a.hashCode() == b.hashCode()` but the inverse and converse are not true. 

Sets/Maps
~~~~~~~~~

* **Sets**: 

    * Sets are collections of elements without duplicates.

    * They do not have ordering. The order in which elements are added does not matter either.

    * Sets offer the ability to quickly find and remove elements quickly. (Ideally does not require searching through all the elements)

    * Concrete Sets Classes: 
    
        * :code:`HashSet`, where elements must implement the :code:`hashCode()` method.
        
        * :code:`LinkedHashSet`, which is a :code:`HashSet` supporting the insertion order of elements.
        
        * :code:`TreeSet`, which requires elements to be :code:`Comparable` or provide a :code:`Comparator`. This data structure ensures the elements are in sorted order.

* **Maps**:

    * Maps are an unordered collection of keys, and each key has an associated value.

    * The keys are used to retrieve the associated values.

    * You can think of Maps as arrays that are indexed by any key instead of incrementing integers.

    * Concrete Maps Classes:

        * :code:`HashMap`, where elements must implement the :code:`hashCode()` method.
        
        * :code:`LinkedHashMap`, which is a :code:`HashSet` supporting the insertion order of elements.
        
        * :code:`TreeMap`, which requires elements to be :code:`Comparable` or provide a :code:`Comparator`. This data structure ensures the elements are in sorted order.

    * Methods you should know:

        * :code:`void put(K key, V val)`

        * :code:`V get(Object key)`

        * :code:`int size()`

        * :code:`boolean containsKey(Object key)`

        * :code:`boolean containsValue(Object val)`

        * :code:`Set<K> keySet()`

        * :code:`Collection<V> values()`