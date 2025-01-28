1\. Algorithms

Now that we can represent *inputs* and *outputs*, we can work on problem
solving.

What stands between inputs(the problem) and outputs(the solution) are
algorithms, which basically means *step-by-step instructions for solving
our problems*.

Let\'s say we have an old-school phone book which contains names and
phone numbers.

- We might open the book and start from the first page, looking for a
  name one page at a time. This algorithm is correct, since eventually
  we\'ll find the name if it\'s in the book.

- We might flip through the book two pages at a time, but this algorithm
  would be incorrect since we might skip the page that contains the
  name.

- Another algorithm would be opening the phone book in the middle,
  decide wether our name will be in the left half or right half of the
  book and reduce the size of our problem by half. We can repeat this
  until we find our name.

We can visualize the efficiency of each algorithms with this chart:

- The first algorithm is represented by the red line. The \'*time to
  solve*\' increases linearly as the size of the problem increases.

- The second algorithm is represented by the yellow line.

- The third algoritm is represented by the green line. It has a
  different relationship between the *size of the problem* and the *time
  to solve it*.

1.1 Searching

Searching represents how we solve the problem of finding information.

A simple problem has an input of some values, and an output of a bool,
whether or not a particular value is in the array.

To define searching algorithms, they are designed to check for an
element or retrieve it from any data structured it is stored in.

These algorithms are generally classified into two categories:

- sequential search: the array is traversed sequentially and every
  element is checked (linear search).

- interval search: designed for searching sorted data structures (binary
  search).

Linear Search

Linear Search is defined as a sequential search algorithm that starts at
one end and goes through each elements of a list until the desired
element is found, otherwise the search continues until the end of the
set.

- Worst-case performance - **O**(n)

- Best-case performance - **O**(1)

- Average performance - **O**(\$n\^2)

- Worst-case space complexity - **O**(1)

<!-- -->

- Representing \'Linear Search\' in ***pseudocode***:

for each door from left to right

if number is behind door

return True

return False

NOTE: the return False is outside the loop, since we only want to do
that after we\'ve looked behind all doors.

Binary Search

Binary Search find the position of a target value within a sorted list.
It compares the target value to the middle element of the array, if they
are not equal the half in which the target cannot be is eliminated and
the search continues in the remaining half, continuing until the target
value is found. If the search ends with the remaining half being empty,
the target is not in the list.

- Worst-case performance - ***O***(log n)

- Best-case performance - ***O***(1)

- Average performance - ***O***(log n)

- Worst-case space complexity - ***O***(1)

<!-- -->

- Representing \'Binary Search\' in ***pseudocode***:

if no doors

return False

if number behind middle door

return True

else if number \< middle door

search left half

else if number \> middle door

search right half

NOTE: remember to check whether there are no doors left, since that
means our number isn\'t behind any of them.

1.2 Structures

Structures also called structs are a way to group several related
variables into one place, each variable being known as a *member* of the
structure.

Unlike arrays, structures can contain different data types(int, float,
char, etc).

Creating a Structure in C using the CS50 Library:

typedef struct

{

string name;

string number;

}

person;

Assigning and accessing values:

person phonebook\[1\] = {\"David\", \"+1-949-468-2750\"};

printf(\"%s\n\", phonebook\[0\].name)

printf(\"%s\n\", phonebook\[0\].number)

1.3 Sorting

Sorting is used to rearrange a given array of list of elements according
to a comparison operator on the elements. The comparison operator is
used to decide the new order of elements in the structure.

Selection Sort

The selection sort algorithm sorts an array by repeatedly finding the
mininum element (considering ascending order) from the unsorted part and
putting it at the beginning.

The algorithm maintains two subarrays in a given array:

- the subarray which already sorted.

- the remaining unsorted array.

- 

Bubble Sort

The bubble sort algorithm is the simplest sorting algorithm. It works by
repeatedly swapping the adjacent elements if they are in the wrong
order.

This algorithm is not suitable for large arrays because its average and
worst-case time complexity are quite high.

Merge Sort

The merge sort algorithm is based on the *divide and conquer* paradigm.
The initial array is split into two equal halves and then combined in a
sorted manner.

Think of it as a recursive algorithm that continuously splits the array
in half until it cannot be further divided, meaning if the array becomes
empty or has one element left in it, the dividing will stop and it is
the base case to stop the recursion. If the array has multiple elements,
split the array into halves and recursively invoke the merge to sort on
each of the halves. Finally when both halves are sorted, the merge
operation is applied. Merge operation is the process of taking two
smaller sorted arrays and combining them to eventually make a larger
one.

1.4 Recursion

Recursion is the ability for a function *to call itself* directly or
indirectly. A recursive function solves a particular problem by calling
a copy of itself and solving smaller subproblems of the original
problems.

An important aspect of recursion is that we should provide a certain
case in order to terminate the recursion process.

Recursion in pseudocode as seen in the ***binary search*** pseudocode:

if no doors

return false

if number behind middle door

return true

else if number \< middle door

search left half

else if number \> middle door

search right half

We\'re using the same *search algorithm* for each half. This seems like
a cyclical process that will never end, but we\'re actually changing the
input to the function and dividing the problem in half each time,
stopping once there are no doors left.
