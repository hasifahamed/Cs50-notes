1\. Data Structures

Data Structures are forms of organization of data in memory so that it
can be accessed and updated efficiently. It is also used for processing,
retrieving, and storing data.

There are different basic and advanced types of data structures that are
used in almost every program or software system that has been developed.

Arrays

Say you have an array with three elements and you want to add one more
but the adjacent space in memory is already occupied by another value
that\'s currently in use.

You could create a new, larger array and copy the values into it.

The running time of inserting into an array like this has an upper bound
of O(n) and a lower bound of Ω(1).

realloc works like malloc but takes two arguments: the address of a
chunk of memory you\'ve already allocated and the size of the memory you
want to allocate to the new value. It copies the old values into the new
space in memory.

int main(void)

{

int \*list = malloc(3 \* sizeof(int));

if (list == NULL)

{

return 1;

}

list\[0\] = 1;

list\[1\] = 2;

list\[2\] = 3;

int \*tmp = realloc(list, 4 \* sizeof(int));

if (tmp == NULL)

{

free(list);

return 1;

}

tmp\[3\] = 4;

free(list);

list = tmp;

for (int i = 0; i \< 4; i++)

{

printf(\"%i\n\", list\[i\]);

}

free(list);

}

Classification of Data Structures

Linear Data Strucutres are structures where data elements are arranged
*sequentially* or *linearly*, and where each element is attached to its
previous and next adjacent element.

Examples: arrays, stacks, queues, linked lists, etc.

Non-linear Data Structures are structures where data elements are not
placed *sequentially* or *linearly*. In this type of structure we can\'t
traverse all the elements in a single run only.

Examples: trees, graphs.

Queues

Queues are specific properties, namely FIFO or *first in, first out*.
You can imagine yourself in a line for a ride at an amusement park. The
first person in the line gets to go on the ride first. The last person
get to go on the ride last.

Queues have specific actions associated with them. An item can be
enqueued, meaning that item can join the line or queue, or an item can
be dequeued, meaning it can leave once it reaches the front of the line.

Stacks

Stacks have properties that are different than a queue: LIFO or *last
in, first out*. Just like stacking trays in a cafeteria, a tray that is
placed in a stack last is the first to be picked.

Linked Lists

Linked Lists can store a list of values in different parts of memory.

- we have the values 1, 2 and 3, each stored in some address memory,
  like 0x123, 0x456 and 0x789.

- this is different than an array since our values are no longer next to
  one another in memory.

- we can use whatever locations in memory that are free.

When inserting a new value to a linked list, we allocate enough memory
for both the value we want to store and the address next to the value.

- next to value 1, for example, we also store a pointer, 0x456 to the
  next value and pointer.

- for the last group, we have the null pointer, 0x0, since there\'s no
  next group.

We can also visualize these addresses as just pointers, since we don\'t
need to know what the addresses actually are.

With a linked list, we have the tradeoff of needing to allocate more
memory for each value and pointer, in order to spend less time adding
values.

The next group of boxes with a value and a pointer are called a node, a
component of a data structure that encapsulates some information. Nodes
can be implemented with a struct.

Binary Search Tree

Binary Search Trees are another data structure that can be used to store
data more efficiently such that it can be searched and retrieved.

- the value that\'s in the center becomes the top of the tree. Values
  that are less than the center are placed to the left and values that
  are more are placed to the right.

- pointers can be used to point to the correct location of each area of
  memory such that each of these nodes can be connected.

Dictionaries

Dictionaries are actual book-form dictionaries that have a word and a
definition - a *key* and a *value*.

Hash Tables

Hash Tables are a combination of both arrays and linked lists. When
implemented in code, a hash table is an *array of pointers to nodes*.

Hashing is the idea of taking a value and being able to output another
value that becomes a shortcut to it later. For example, the name *Aaron*
can be hashed as value 1, *Ben*, as 2, and so on for the whole alphabet.
While not ideal in terms of design, ultimately, putting all *a*\'s in
one bucket, illustrates how you can use this concept.

Hash function is an algorithm that reduces a larger value to something
small and predictable. Generally, this function takes in an item you
with to add to your hash table and returns an integer representing the
array index in which the item should be placed.

Tries

Tries are always searchable in *constant time*. One downside of tries is
that they tent to take up a large amount of memory.
