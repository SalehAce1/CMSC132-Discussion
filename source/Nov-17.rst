11/17 Exam 3 Review
===================

Reminders
^^^^^^^^^

    * Third Exam is on Friday 11/16.

Exam Logistics
^^^^^^^^^^^^^^

    * Find Exam info page `here. <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/exams/exam3/>`_

    * Also look at Piazza post @288 for the general format.

    * There will be an online study session held by some of the TAs on Wednesday

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

* Let's look at the slideset to review `Linked Lists <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/lectures/Week6/LinearDataStructures.pdf>`_

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

* Another TA, **Matthew Simmons**, was kind enough to make a bunch of examples to get us comfortable with Java's Abstract Data Types!

    * Stack Questions:

        Say we want to reverse a Stack (and don't care about modifying the original). It can be done like so:

        .. code-block:: Java

            public Stack<T> reverse(Stack<T> stack) {
                Stack<T> newStack = new Stack<T>();
                while (!stack.empty()) {
                    newStack.push(stack.pop());
                }
                return newStack;
            }

        Now, what if we wish to preserve the original?
        Double the Stack, then reverse one of them (with modifying)!

        .. code-block:: Java

            public Stack<T> reverse(Stack<T> stack) {
                Stack<T> newStack = new Stack<T>();
                Stack<T> tempStack = new Stack<T>();
                while (!stack.empty()) {
                    T value = stack.pop();
                    newStack.push(value);
                    tempStack.push(value);
                }
                while (!tempStack.empty()) {
                    stack.push(tempStack.pop()); // Reverse the reversed - back to normal!
                }
                return newStack;
            }

        Now, what if we want the size?
        Similar!

        .. code-block:: Java

            public int size(Stack<T> stack) {
                int count = 0;
                Stack<T> tempStack = reverse(reverse(stack)); // Fancy way to make a copy :)
                while (!tempStack.empty()) {
                    tempStack.pop();
                    count++;
                }

                return count;
            }

------------------------------------------------------------

    * Queue Questions:

        Let's try to get the size of a queue (pretend there's no size() method already)
        Idea: poll() until there's nothing left will give count - also ensure we don't modify queue!

        .. code-block:: Java

            public int size(Queue<T> queue) {
                int count = 0;
                Queue<T> tempQueue = new ArrayDeque<T>(); // Queue is an interface so we can't instantiate it - but an ArrayList is-a Queue!
                while(queue.peek() != null) {
                    tempQueue.add(queue.poll()); // Adds in order - FIFO still - tempQueue will be old queue!
                    count++;
                }
                queue = tempQueue; // Queue keeps its elements in order!
                return count;
            }

        Reversing is still cool - can we do that?  
        Looks weird, but sure! We must add beginning with the last element, then work backwards (sounds like recursion to me!)

        .. code-block:: Java

            public Queue<T> reverse(Queue<T> queue) {
                Queue<T> newQueue = new ArrayDeque<>();
                reverseAux(queue, newQueue);
                return newQueue;
            }

            private void reverseAux(Queue<T> oldQueue, Queue<T> reversedQueue) {
                if (oldQueue.peek() != null) {
                    T value = oldQueue.poll();
                    reverseAux(oldQueue, reversedQueue); // Same call as before - is this an infinite loop?
                    reversedQueue.add(value);
                }
            }

        Now, to do this without modifying the original (exercise for you - you'll need two helpers instead of two whiles in the Stack example)

------------------------------------------------------

    * How about Deques? (Pronounced Decks - I don't know why)

        Deques are a combination of a Stack and a Queue - so implementations as above work (changing method names) for size and reverse!
        If Queue is like a linked list, Deque is like a doubly-linked list! (next and prev Node)
        Makes things nice when you need both ends
        Ex: Swap the first and last values of a Queue, Stack, and Deque.
        Queue: Very sad iterations :( Same with Stack
        But Deque:

        .. code-block:: Java

            public void swapFirstLast(Deque<T> deque) { // Assume big enough to do this
                T first = deque.pollFirst();
                T last = deque.pollLast();

                deque.addFirst(last);
                deque.addLast(first);
            }

        Exercise: This can cause issues if there are too few elements. Fix it up!
        Here's something a little more deque-sized:
        Given a Deque, re-order it so we alternate 1, n, 2, n-1, ...
        Ex: 1, 2, 3, 4, 5 -> 1, 5, 2, 4, 3

        .. code-block:: Java

            // Recursion
            public Deque<T> reorder(Deque<T> deque) {
                Deque<T> newDeque = new ArrayDeque<>(); // LinkedList implements Deque
                reorderAux(deque, newDeque, true);
                return newDeque;
            }

        Idea: Boolean will alternate each call for if we poll from front or back!

        .. code-block:: Java

            private void reorderAux(Deque<T> oldDeque, Deque<T> newDeque, boolean fromFront) {
                if (oldDeque.size() > 0) {
                    if (fromFront) {
                        newDeque.addLast(oldDeque.pollFirst());
                    } else {
                        newDeque.addLast(oldDeque.pollLast());
                    }
                    reorderAux(oldDeque, newDeque, !fromFront); // Remember, oldDeque is already changed since pollFirst() /
                                                                // pollLast() removes one!
                }
            }

        .. code-block:: Java

            // Iteration
            public Deque<T> reorder(Deque<T> oldDeque) {
                Deque<T> newDeque = new ArrayDeque<>();
                boolean fromFront = true;
                while (oldDeque.size() > 0) {
                    if (fromFront) {
                        newDeque.addLast(oldDeque.pollFirst());
                    } else {
                        newDeque.addLast(oldDeque.pollFirst());
                    }
                    fromFront = !fromFront; // Flips direction each time
                }
                return newDeque;
            }

Hashing
~~~~~~~
Collision Handling:

* **Open Addressing**: Look for another open spot on the table.

    * Linear probing: Place the value into the next open spot.

    * Quadratic probing: If at index k = j, go to index k + j^2, this prevents clustering.

* **Separate Chaining**: Each element can store multiple values. 

* **Java's Hash Code Contract**: :code:`a.equals(b) => a.hashCode() == b.hashCode()` but the inverse and converse are not true.

* **Load factor**: = number of elements / table capacity (size of array) => tells us how full the table is.

* `Link to hashing just to be safe <https://www.cs.umd.edu/class/fall2021/cmsc132-030X/lectures/Week8/Hashing.pdf>`_

* Now we'll go through a more detailed example of handling collisions, created by another TA, **Matthew Simmons**:

    * Seperate Chaining:

        Slap a linked list into it! Our data structure will look like this:
        LinkedList<T>[] table = new LinkedList<T>[capacity]; // An array of linked lists!
        Instead of the hash index referring to the value, it points to a list with the value in it.
        Now, just iterate through this list! 
        Example:

        .. code-block:: Java 

            public void insert(T value) {
                int index = hashIndex(value); // hashIndex is a method in HashTable - does as described above.
                if(!table[index].contains(value)) { // Do nothing if value is already in list - is this "necessary"?
                    table[index].add(value);
                }
            }

        Where this method calls LinkedList.add(), which is what you implemented in your project (addToFront / addToEnd - doesn't matter which).
        Delete() and search() are similarly short.
        Pros:

        * Shorter code!

        * No "need" to resize the table! (It would still be good to)
        
        Cons: 

        * Slower Big-O (If everything is in one linkedlist, search is still O(n), not O(1))

        * Need to use Linked Lists

    * Open Addressing:

        In this case, we instead try inserting in a new spot!

        .. code-block:: Java

            T[] table = new T[capacity];
            public void insert(T value) {
                int index = hashIndex(value);
                int nextOpenIndex = nextOpen(index);
                table[nextOpenIndex] = value;
            }

        Here, search() and delete() are similarly short - see lecture for algorithms.
        However, how do we deal with collisions?
        The "easiest" method to do such a thing is called linear probing - we keep checking to the right for open spots.

        .. code-block:: Java 

            private int nextOpen(int index) {
                for(int i = 0; i < capacity; i++) {
                    if(table[(index + i) % capacity] == null) { // index + i % size - goes from index, index + 1, ... size - 1, 0, 1, ... index - 1.
                        return index + i;
                    }
                }
                // If we get here, there's no open spots - need to fix that!
                resize(); // Worst-case scenario to resize - it would be better to do this earlier (depending on load factor!)
                return nextOpen(index); // Now we can finally 
            }

        Here, we simply keep checking each spot until we reach a new spot! 
        What if there's no openings? We must increase the size!
        The most common way to do this is to just double the size, then put the value back in.

        .. code-block:: Java

            private void resize() {
                T[] temp = table;
                T[] newTable = new T[capcity * 2];
                table = newTable;
                int oldSize = capacity;
                capacity *= 2;
                for(int i = 0; i < oldSize; i++) { // We must put the values in the new hash!
                    insert(temp[i]); // Gets each old value and re-adds it with the new hash index.
                }  // NOTE: capacity and table are both updated, that is why insert() works.
            }

        Pros:

        * Fast!

        * No linked lists!
        
        Cons: 

        * Resizing is yucky

        * Dealing with collisions is lame

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
