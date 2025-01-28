1.Memory

Hexadecimal is a base-16 system using 0-9 and A-F.

So 0F = 16 and 10 = 17 and FF = 255.

Conveniently, one hexadecimal digit is equivalent to four binary digits.

By convention, hexademcial digits are represented with a 0x prefix -
0x48 or 0x21 - to distinguish them from binary digits.

Hexadecimal is is the basis of RGB. That\'s why \#000000 is black, the
absence of colour and \#FFFFFF is white, the complete saturation of
colour.

- Pixel Art  
  Pixels are squares, individual dots, of color that are arranged on an
  up-down, left-right grid.

- You can imagine as an image as a map of bits, where zeros represent
  black and ones represent white.

- *RGB*, or *red, green, blue*, are numbers that represent the amount of
  each of these colors. In Adobe Photoshop, you can see these settings
  as follows:

- Notice how the amount of red, blue, and green changes the color
  selected.

- You can see by the image above that color is not just represented in
  three values. At the bottom of the window, there is a special value
  made up of numbers and characters. 255 is represented as FF. Why might
  this be?

<!-- -->

- Hexa decimal

- *Hexadecimal* is a system of counting that has 16 counting values.
  They are as follows:  
  0 1 2 3 4 5 6 7 8 9 a b c d e f

- Notice that F represents 15.

- Hexadecimal is also known as *base-16*.

- When counting in hexadecimal, each column is a power of 16.

- The number 0 is represented as 00.  
  The number 1 is represented as 01.  
  The number 9 is represented by 09  
  The number 10 is represented as 0A.  
  The number 15 is represented as 0F.  
  The number 16 is represented as 10.

- The number 255 is represented as FF, because 16 x 15 (or F) is 240.
  Add 15 more to make 255. This is the highest number you can count
  using a two-digit hexadecimal system.  
  Hexadecimal is useful because it can be represented using fewer
  digits. Hexadecimal allows us to represent information more
  succinctly.

Addresses

When a variable is created in C, a memory address is assigned to that
variable. The address is the location of where the variable is stored on
the computer.

To access the address of the variable, the reference operator (&) is
used.

\#include \<stdio.h\>

int main(void)

{

int age = 30;

printf(\"%p\n\", &age);

}

It will return the address in hexadecimal form (0x\...) which is just a
numbering system with base 16.

Pointers

Pointers store the memory address of a variable as its value. To print
it, use the %p format specifier. Pointers give you the ability to
manipulate data in the computer\'s memory which can reduce the code and
improve the performance.

They point to a *data type* of the same type, and is created with the \*
operator.

\#include \<stdio.h\>

int main(void)

{

int age = 30;

int \*pointer = &age;

// prints out the value of age

printf(\"%i\n\", age);

// prints out the memory address of age

printf(\"%p\n\", &age);

// prints out the memory address of age with the pointer

printf(\"%p\n\", pointer);

}

In the example above, the pointer variable was used to get the memory
address of a variable (used together with the & reference operator).

There\'s also the possibility to get the value of the variable the
pointer points to with the \* operator, also known as the dereference
operator.

\#include \<stdio.h\>

int main(void)

{

int age = 30;

int \*pointer = &age;

// prints out the memory address of age with the pointer

printf(\"%p\n\", pointer);

// prints out the value of age with the pointer

printf(\"%p\n\", \*pointer);

}

- When the \* sign is used in declaration int\* pointer, it creates a
  pointer variable.

- When not used in declaration, it acts as a dereference operator.

Pointer Arithmetic

Pointer arithmetic is the process of applying mathematical operation to
pointers, using them just like numbers.

\#include \<stdio.h\>

int main(void)

{

int numbers\[\] = {4, 6, 8, 2, 7, 5, 0};

printf(\"%i\n\", \*numbers);

printf(\"%i\n\", \*(numbers + 1));

printf(\"%i\n\", \*(numbers + 2));

printf(\"%i\n\", \*(numbers + 3));

printf(\"%i\n\", \*(numbers + 4));

printf(\"%i\n\", \*(numbers + 5));

printf(\"%i\n\", \*(numbers + 6));

}

We add only 1 to the address of numbers instead of 4 (ints are 4 bytes
in size), since the compiler already knows that the type of each value
in numbers is 4 bytes. With +1 we\'re telling the compiler to move the
next value in the array, not the next byte.

Also, numbers is an array, but we can use it as a pointers with
\*numbers.

Compare & Copy

When comparing two integers with the same values, the program works as
expected.

\#include \<stdio.h\>

int main(void)

{

int n = 50;

int m = 50;

if (n == m)

{

printf(\"Same!\n\");

}

else

{

printf(\"Different!\n\");

}

}

When comparing two strings with the same inputs, the program will print
\'*Different!*\'.

\#include \<cs50.h\>

\#include \<stdio.h\>

int main(void)

{

char \*s = get_string(\"s: \");

char \*t = get_string(\"t: \");

if (s == t)

{

printf(\"Same!\n\");

}

else

{

printf(\"Different!\n\");

}

}

This happens because each string is a pointer (char \*) to a different
location in memory, where the first character of each string is stored.
So even if the characters in the string are the same, this will always
print \'*Different!*\'.

The get_string() function has been returning just a char \*, or a
pointer to the first character of a string from the used. Since we
called get string() twice, we got two different pointers back.

This problem can be solved by using the strcmp() function from the
string.h library, which wll to to each string and compare them character
by character.

When trying to copy a string, then capitalize the first letter in the
copied one, we see that in both strings the first letter is capitalized.

\#include \<cs50.h\>

\#include \<ctype.h\>

\#include \<stdio.h\>

\#include \<string.h\>

int main(void)

{

string s = get_string(\"s: \");

string t = s;

t\[0\] = toupper(t\[0\]);

printf(\"s: %s\n\", s);

printf(\"t: %s\n\", t);

}

Since we set s and t to the same value, or the same address, they\'re
both pointing to the same character, and so we capitalized the same
character in memory.

Arrow Operator

In C, the arrow operator (-\>) allows the access to elements inside
Structures and Unions. It is used with a *pointer variable pointing to a
structure or union*.

\#include \<stdio.h\>

\#include \<stdlib.h\>

// create the structure

struct car {

char brand\[\];

char color\[\];

int year;

};

// create the structure object

struct car\* firstCar = NULL;

int main(void)

{

// assign memory to struct variable

firstCar = (struct car\*)

malloc(sizeof(struct car));

// assign value to age variable using the arrow operator

firstCar-\>year = 2012;

// print the assigned value

printf(\"%i\n\", firstCar-\>year);

}

Memory Allocation

To actually make a copy of a string, and solve the problem above, we
have to copy each character in s to somewhere else in memory. For that,
the function malloc() is used to allocate some number of bytes in
memory. After we\'re done with it, we\'ll use free() to mark the memory
as usable for something else. Also, we\'ll use the strcpy() from
string.h library to copy the string.

\#include \<cs50.h\>

\#include \<ctype.h\>

\#include \<stdio.h\>

\#include \<stdlib.h\>

\#include \<string.h\>

int main(void)

{

char \*s = get_string(\"s: \");

char \*t = malloc(strlen(s) + 1);

// exit if \'t\' is equal to NULL, meaning the computer is out of memory
and there is not an address to point to

if (t == NULL)

{

return 1;

}

strcpy(t, s);

// check that \'t\' has a length before capitalizing

if (strlen(t) \> 0)

{

t\[0\] = toupper(t\[0\]);

}

printf(\"s: %s\n\", s);

printf(\"t: %s\n\", t);

free(t);

}

Memory Layout

The data types that need to be stored for our program are organized into
different sections.

- the machine code section is the compiled program\'s binary code. When
  running the program, the code is loaded into memory.

- the global variables declare within the program occupy the next
  section of memory.

- the heap section is an empty area where malloc() can get free memory
  for our program to use.

- the stack section is used by functions and local variables as they are
  called.

If we call malloc() for too much memory, we will have a heap overflow
since we end up going past our heap. If we call too many functions
without returning from them, we will have a stack overflow, where our
stack has too much memory allocated as well.

Garbage Values

A garbage value occurs when allocating a memory for your variable, but
you don\'t assign a value to it. The memory of the variable may still
have a value from the previous program.

\#include \<stdio.h\>

\#include \<stdlib.h\>

int main(void)

{

int scores\[3\];

for (int i = 0; i \< 3; i++)

{

printf(\"%i\n\", scores\[i\]);

}

}

In the example above, we declared an array named scores, but didn\'t
initialize it with any values. The values in the array are garbage
values, whatever unknown values that were in memory from whatever
program was running on the computer before.

If we try to go to an address that\'s a garbage value, our program is
likely to crash from a segmentation fault.

String

Strings can be manipulated via their addresses. Since a string is an
array of contiguous characters and ends in \0, you just need to know the
address of the first character and you can find the rest of the string.

string s = \"HI!\";

printf(\"%p\n\", &s\[0\]);

printf(\"%p\n\", &s\[1\]);

printf(\"%p\n\", &s\[2\]);

// 0x4006b4

// 0x4006b5

// 0x4006b6

Valgrind

Valgrind is a tool for memory debugging, helping you to figure out where
you touched memroy you shouldn\'t have or putting in free when needed,
preventing a memory leak.

You should never trust the contents of your computer\'s memory if you
have not explicitly put the content there. Assume it\'s a \"garbage
value\".

Always initialize values before thinking of touching or reading them.

Scan f

scanf reads input from the user.

If you manually assign space in memory for the input, you need to be
aware that the user could enter more or less data, requiring more or
less space in memory.

int main(void)

{

char s\[4\];

printf(\"s: \");

scanf(\"%s\", s);

printf(\"s: %s\n\", s);

}

File I/O

If you put a programme in memory, as soon as the programme ends it\'s
contents are gone. Files allow for data to be saved long term.

You can open files in different ways: to read them, to (over)write them
or to append to them.

You need to tell C when you are opening and closing a file and while
mode you are working in.

int main(void)

{

FILE \*file = fopen(\"phonebook.csv\", \"a\");

if (file == NULL)

{

return 1;

}

char \*name = get_string(\"Name: \");

char \*number = get_string(\"Number: \");

fprintf(file, \"%s,%s\n\", name, number);

fclose(file);

}

You can often determine a file\'s type by looking at its first few
bytes. These \"magic numbers\" at the beginning of the files are
industry standards.

A jpeg will start with 0xff 0xd8 0xff.

- Overflow

- A *heap overflow* is when you overflow the heap, touching areas of
  memory you are not supposed to.

- A *stack overflow* is when too many functions are called, overflowing
  the amount of memory available.

- Both of these are considered *buffer overflows*.
