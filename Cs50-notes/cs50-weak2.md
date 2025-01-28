- 1\. Reading level

- One of the real-world problems we will solve in this course is
  understanding reading levels.

- With the help of some of your peers, we presented readings at various
  reading levels

- We will be quantifying reading levels this week as one of your many
  programming challenges.

- 1\. 1 Compilling

A compiler is a programme that converts source code to machine code.
Clang is a popular compiler for C.

When all programmes had to be compiled, the default file produced was
a.out for assembly output.

Clang can be configured with command line arguments but these can become
long and verbose. Eventually you will want to automate the steps.

Sometimes when using a library it\'s not sufficient to include the
header file at the top of your code, you need to explicitly tell the
computer where to find the file.

When you comile your code there are a few steps involved:

- precompiling

- compiling

- assembling

- linking

First the computer preprocesses your code, looking for any lines
starting with \# and copying the contents of the referenced file into
your own code.

To compile your code means to convert it from source code to another
kind of source code, assembly code.

To assemble your code means to convert your code from assembly to
machine code, 0s and 1s.

Finally the 0s and 1s of your code need to be linked to the 0s and 1s of
any library you are using.

1\. 2 Debugging

Bugs are mistakes in programs that cause them to behave differently than
intended.

Debugging is the process of finding and fixing those bugs.

Print Statement Debugging

- the process in which we tell our application with printf or any other
  similar statements in other languages, to generate output while the
  program is executing.

- the output generated helps diagnose issues within the program.

Debugger

- is a tool built into VS Code, which will walk through the program
  *step-by-step*.

Rubber Duck Debugging

- the technique where we explain the code to a *rubber duck* or any
  other *inanimate* object.

- by talking through the code out loud, we might realize the mistake.

1.3 Memory

On a typical computer each data type in C is defined as taking up a
fixed amount of space. This varies, but for example:

- bool - 1 byte

- char - 1 byte

- double - 8 bytes

- float - 4 bytes

- int - 4 bytes

- long - 8 bytes

- string - ? bytes

It\'s in memory (RAM) that programmes are stored while running and files
are stored while open.

RAM is much faster than solid state storage but it\'s also volatile, it
requires electricity to maintain it.

Imagine your computer\'s memory as a grid of bytes. An int would take up
4 spaces. In those 4 spaces would be a pattern of 0s and 1s representing
the int.

1.4 Arrays

Arrays are used to store multiple values of the *same type*,
*back-to-back*, *contiguously*.

When declaring an array, the square brackets after the name indicates
how many values we want to store.

Declare an Array

int scores\[3\];

scores\[0\] = 72;

scores\[1\] = 73;

scores\[2\] = 33;

int scores\[3\] = {25, 50, 75, 100};

1\. 5 Strings

If you cast a character to an int, you can access its ASCII value.

Each char is stored in a single byte.

By default, C does not have a string datatype.

A string is an array of characters.

So the string \"HI!\" is equivalent to the array \[\'H\', \'I\',
\'!\'\].

You can access the individual characters of a string using \[\]
notation.

The computer\'s memory knows when strings begin and end because, under
the hood, the string uses one extra byte, \0 or NUL, to represent the
end of the string. For example, the string HI! uses 4 bytes, not 3.

string s = \"HI!\"

printf(\"%i %i %i %i\n\", s\[0\], s\[1\], s\[2\], s\[3\]);

// 72 73 33 0

One dangerous aspect of C is that you can access values from other parts
of memory. If you accessed s\[4\] you would get whatever value is in
this adjacent spot in memory.

If you want to loop to the end of a string and then stop, you could set
your loop to break when it reaches \0 or use the strlen() function from
\<string.h\>.

int main(void)

{

string s = get_string(\"Input: \");

printf(\"Output: \");

for (int i = 0, n = strlen(s); i \< n; i++)

{

printf(\"%c\", s\[i\]);

}

printf(\"\n\");

}

1.6 Array of string

You can have an array of strings. And since a string is itself an array,
this is an array of arrays.

string words\[2\];

words\[0\] = \"HI!\";

words\[1\] = \"BYE!\";

You can use multiple \[\] to access values from nested arrays.

words\[0\]\[0\]

// \'H\'

words\[1\]\[1\]

// \'Y\'

The ASCII values of uppercase and lowercase letters are always 32 apart.
You could uppercase a lowercase letter by subtracting 32 from it. Or you
could just use the toupper() function from \<ctype.h\>. toupper()
expects a character as input; you cannot pass a word to it. To make a
string uppercase you would need to loop over every character in the
string.

1.7 Command-Line Arguments

Programs can also take arguments or inputs given in the command we use
to run it.

The main function has to be changed from void so it can take arguments
as:

\#include \<stdio.h\>

\#include \<cs50.h\>

int main(int argc, string argv\[\])

{

printf(\"Hello, %s\n\", argv\[1\]);

}

Now when running the program, we need to pass an argument: ./argv David.

The main function also returns an integer value called an exit status.
By default the main function returns 0 to indicate nothing went wrong,
but we can write a program to return a different value.

\#include \<stdio.h\>

\#include \<cs50.h\>

int main(int argc, string argv\[\])

{

if (argc != 2)

{

printf(\"Missing command-line argument!\n\");

return 1;

}

printf(\"Helo, %s\n\", argv\[1\]);

return 0;

}

- A *non-zero* exit status indicates some error to the system that runs
  our program. Once we run return 1;, our program will exit early with
  an exit status of 1.

- C will automatically return 0 if the program ran as expected so we
  don\'t really need to write it in the code.

1\. 8 Exit status

Programmes often return an int to show what has happened. 0 indicates
that nothing as gone wrong. This is why in C you set up main to return
an int.

int main(int argc, string argv\[\])

{

if (argc != 2)

{

printf(\"missing command-line argument\n\");

return 1;

}

printf(\"hello, %s\n\", argv\[1\]);

return 0;

}

1.9 Cryptography

- Cryptography is the art of ciphering and deciphering a message.

- plaintext and a key are provided to a cipher, resulting in ciphered
  text.

<!-- -->

- The key is a special argument passed to the cipher along with the
  plaintext. The cipher uses the key to make decisions about how to
  implement its cipher algorithm.

- A cipher is an algorithm that scrambles its input so as to produce an
  output that a third party can\'t understand. That algorithm is a
  reversible process so that you can decipher the text and read it.

- Ciphers use a key to determine how to encrypt and decrypt the input.
