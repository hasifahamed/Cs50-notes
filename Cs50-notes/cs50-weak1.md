1 - C

- There are a few guiding lights when writing code: correctness, design,
  style.

\"hello, world\" in C is:

\#include \<stdio.h\>

int main(void)

{

printf(\"hello, world\");

}

- For a computer to understand this code, it needs to be converted from
  source code to machine code. A compiler is a programme designed to do
  this.

- You need to type make hello to compile your code and ./hello to run
  it.

- A function is a programmed version of an algorithm. They take in
  arguments and can have side effects or return values.

string answer = get_string(\"What\'s your name? \");

printf(\"hello, %s\n\", answer);

- Header files are programmes written in C with a .h file extension.
  stdio.h is the standard input output programme in C.

- Comments should convey the purpose/intention of your code, not
  describe what it is literally doing.

1 .2 Header file  
The statement at the start of the code \#include \<stdio.h\> is a very
special command that tells the compile that you want to use the
capabilities of a *library* called stdio.h, a *header file*. This allows
you, among many other things, to utilize the printf function.  
A *library* is a collection of code created by someone. Libraries are
collections of pre-written code and functions that others have written
in the past that we can utilize in our code.  
You can read about all the capabilities of this library on the [Manual
Pages](https://manual.cs50.io/). The Manual Pages provide a means by
which to better understand what various commands do and how they
function.  
It turns out that CS50 has its own library called cs50.h. There are
numerous functions that are included that provide *training wheels*
while you get started in C:  
get_char

get_double

get_float

get_int

get_long

get_strig

1.3Types

In C you have access to many data types: bool, char, double, float, int,
long, string.

Each of these data types only have a finite number of bits.

Integers only use 32 bits. This can support 4 billion total values and
lets you count from -2 billion to 2 billion. To work with larger numbers
you\'d need a long.

When working with formatted strings, you can use the following format
codes:

- %c - single character

- %f - floating point value

- %i - integer

- %li - long

- %s - string

C supports a number of mathmatical operators: +, -, \*, /, %.1.4

- 1.4 Conditional

- Another building block you utilized within Scratch was *conditionals*.
  For example, you might want to do one thing if x is greater than y.
  Further, you might want to do something else if that condition is not
  met

- We look at a few examples from Scratch.

- In C, you can compare two values as follows:  
  *// Conditionals that are mutually exclusive*

- 

- **if** (x \< y)

- {

- printf(\"x is less than y**\n**\");

- }

- **else**

- {

- printf(\"x is not less than y**\n**\");

- }

- Notice how if x \< y, one outcome occurs. If x \< y, then another
  outcome occurs.

- Similarly, we can plan for three possible outcomes:  
  *// Conditional that isn\'t necessary*

<!-- -->

- **if** (x \< y)

- {

- printf(\"x is less than y**\n**\");

- }

- **else** if (x \> y)

- {

- printf(\"x is greater than y**\n**\");

- }

- **else** if (x == y)

- {

- printf(\"x is equal to y**\n**\");

- }

- Notice that not all these lines of code are required. How could we
  eliminate the unnecessary calculation above?

- You may have guessed that we can improve this code as follows:  
  *// Compare integers*

- 

- **if** (x \< y)

- {

- printf(\"x is less than y**\n**\");

- }

- **else** if (x \> y)

- {

- printf(\"x is greater than y**\n**\");

- }

- **else**

- {

- printf(\"x is equal to y**\n**\");

- }  
    
  Let's use this library in your program.

1.5 operator

- *Operators* refer to the mathematical operations that are supported by
  your compiler. In C, these mathematical operators include:

- \+ for addition

- \- for subtraction

- \* for multiplication

- / for division

- % for remainderWe will use all of these operators in this course.

1.6 Variable

- In C, you can assign a value to an int or integer as follows:  
  int counter = 0;

<!-- -->

- Notice how a variable called counter of type int is assigned the value
  0.

- C can also be programmed to add one to counter as follows:  
  counter = counter + 1;

- Notice how 1 is added to the value of counter.

- This can be also represented as:  
  counter = counter++;

- Notice how 1 is added to the value of counter. However, the ++ is used
  instead of counter + 1.

- You can also subtract one from counter as follows:  
  counter = counter\--;

- Notice how 1 is removed to the value of counter.

1.7 loops

**Loop** allows you to execute a block of code multiple times, which is
very useful for tasks like iterating over arrays, performing repeated
calculations, or processing data until a condition is met. There are
three types of loops in C:

1.  **For loop**

2.  **While loop**

3.  **Do-while loop**

**1. For Loop**

The for loop is typically used when the number of iterations is known
beforehand. It has three parts:

\#include \<stdio.h\>

int main() {

for (int i = 1; i \<= 5; i++) {

printf(\"%d\n\", i); // Prints numbers from 1 to 5

}

return 0;

}

2.while loop

A while loop runs as long as a condition is true. The condition is
checked before every iteration.

\#include \<stdio.h\>

int main() {

int i = 1;

while (i \<= 5) {

printf(\"%d\n\", i); // Prints numbers from 1 to 5

i++; // Increment counter

}

return 0;

}

3\. Do while loop

A do-while loop is similar to a while loop, but it always executes at
least once because the condition is checked **after** the block of code.

\#include \<stdio.h\>

int main() {

int i = 1;

do {

printf(\"%d\n\", i); // Prints numbers from 1 to 5

i++; // Increment counter

} while (i \<= 5);

return 0;

}

1.8 Abstraction

Abstraction is a computer programming principle where you can simplify
otherwise more complicated detials.

A function lets you abstract its implementation details by just calling
it by its name.

By convention, you write your custom functions after your main function.
But C won\'t understand this since you\'ll be calling the function
before you define it. To remedy this, place the prototype above the main
function.

\#include \<stdio.h\>

// Prototype

void meow(void)

int main(void)

{

for (int i = 0; i \< 3; i++)

{

meow();

}

}

void meow(void)

{

printf(\"meow\n\");

}

void refers the absence of input or output. If a function doesn\'t have
a return value or arguments, mark it with void.

void meow(int n)

{

for (int i = 0; i \< n; i++)

{

printf(\"meow\n\");

}

}

A do while loop is like a while loop but will do an action at least one
time before checking a condition.

\#include \<cs50.h\>

\#include \<stdio.h\>

// Prototype

int get_positive_int(void)

int main(void)

{

int i = get_positive_int();

printf(\"%i\n\", i);

}

int get_positive_int(void)

{

int n;

do

{

n = get_int(\"Positive Integer: \");

}

while (n \< 2);

return 0;

}

When you declare a variable inside curly braces you run into the issue
of scope. The scope of a variable is the lines of code in which that
variable exists and you can use it.

This is why you need to declare n outside the do while loop above.

1.9 Comments

- Comments are fundamental parts of a computer program, where you leave
  explanatory remarks to yourself and others who may be collaborating
  with you regarding your code

- All code you create for this course must include robust comments.

- Typically, each comment is a few words or more, providing the reader
  an opportunity to understand what is happening in a specific block of
  code. Further, such comments serve as a reminder for you later when
  you need to revise your code.

- Comments involve placing // into your code, followed by a comment.
  Modify your code as follows to integrate comments:  
  *// Helper function*

- 

- \#include *\<stdio.h\>*

- 

- void print_row(int width);

- 

- int main(void)

- {

- **const** int n = 3;

- 

- *// Print n rows*

- **for** (int i = 0; i \< n; i++)

- {

- print_row(n);

- }

- }

- 

- void print_row(int width)

- {

- **for** (int i = 0; i \< width; i++)

- {

- printf(\"#\");

- }

- printf(\"**\n**\");

- }

- Notice how each comment begins with a //.

1.10 Basic Data Types

In C, variables must be a specified data type and they need format
specifiers to be printed.

| Data Type | Size         | Description                                        |
|-----------|--------------|----------------------------------------------------|
| int       | 2 or 4 bytes | stores whole numbers                               |
| float     | 4 bytes      | stores fractional numbers up to 7 decimal digits   |
| double    | 8 bytes      | stores fractional numbers up to 15 decimal digits  |
| char      | 1 byte       | a single character / letter / number / ASCII value |
| long      | 8 bytes      | stores whole numbers, can go higher than int       |
| bool      | 2 bytes      | stores \'true\' or \'false\' values                |

1.11 Truncation

Another issue that can arise when using data types includes
truncation.  
*// Division with ints, demonstrating truncation*

\#include *\<cs50.h\>*

\#include *\<stdio.h\>*

int main(void)

{

*// Prompt user for x*

int x = get_int(\"x: \");

*// Prompt user for y*

int y = get_int(\"y: \");

*// Divide x by y*

printf(\"%i**\n**\", x / y);

}

An integer divided by an integer will always result in an integer in C.
Accordingly, the above code will often result in any digits after the
decimal being thrown away.

This can be solved by employing a float:  
*// Floats*

\#include *\<cs50.h\>*

\#include *\<stdio.h\>*

int main(void)

{

*// Prompt user for x*

float x = get_float(\"x: \");

*// Prompt user for y*

float y = get_float(\"y: \");

*// Divide x by y*

printf(\"%.50f**\n**\", x / y);

}

Notice that this solves some of our problems. However, we might notice
imprecision in the answer provided by the program.

*Floating point imprecision* illustrates that there are limits to how
precise computers can calculate numbers.

As you are coding, pay special attention to the types of variables you
are using to avoid problems within your code.

We examined some examples of disasters that can occur through
type-related errors.

1\. 12Floating Point Imprecision

Floating Point Imprecision is the inability for computers to represent
all possible real numbers with a finite number of bits, like 32 bits for
a float. So, computers have to store the closest value it can, leading
to imprecision. This problem is present even in a higher level language
such as Python.

To see this, we\'ll change the number of decimals displayed by specifing
the number in the *print* statement.

Example

\#include \<cs50.h\>

\#include \<stdio.h\>

int main(void)

{

float x = get_float(\"x: \");

float y = get_float(\"y: \");

float z = x / y;

printf(\"%.50f\n\", z);

}

Result:

x: 2

y: 3

0.66666668653488159179687500000000000000000000000000

(Or)

You can control how many decimal places printf will print printf(%.10\n,
x / y) but you may run into floating-point imprecision.

Computers only have finite memory. If you only have a finite number of
bits you can count pretty precisely but not infinitely high or low.

After a certain point the computer will have to approximate and you\'ll
run into problems like 1 / 10 equaling 0.100000001490116119384\...\.....

1.13 Integer Overflow

Even integers have limitations. Integers are only 32 bit. If the
calculation needs more than this then the result becomes inaccurate. If
you need to carry a number but run out of space it gets dropped.

This is the same principle behind the Y2K scare. Any system storing
years as two digits would go from 99 to 00 and interpret 2000 as 1900.

The Unix Epoch counds the seconds since 1 January 1970. Any programme
that is keeping track of this using 32 bits will run into problems once
it reaches 4 billion seconds, on 19 January 2038.

Eg :Hello world

\#include \<stdio.h\>

int main(void)

{

printf(\"hello, world\");

}
