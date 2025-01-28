1\. Computer Science

**\'Computer Science\'** is fundamentally problem solving.

Problem solving can be thought as the process of taking some *input* (a
problem we want to solve) and generate some *output* (the solution to
our problem).

To begin doing that, we\'ll need a way to represent inputs and outputs,
so we can store and work with information in a standardized way.

1.1. Representing - Numbers

Unary - the system where each digit represents a single value.

Decimal - the system which uses ten digits (0 to 9) to count to higher
numbers.

Binary - the system computers use. It has only two digits (0 & 1).

For example:

-   to represent 0 in binary:\
    0 0 0

-   to represent 1 in binary:\
    0 0 1

-   to represent 2 in binary, we\'ll need to change another digit:\
    0 1 0

-   to represent 3, we\'ll add 1:\
    0 1 1

-   to represent 4:\
    1 0 0

-   to represent 5:\
    1 0 1

-   to represent 6:\
    1 1 0

-   to represent 7:\
    1 1 1

Each binary digit is also called a bit. Since computers run on
electricity, which can be turned on or off, we can simply represent a
bit by turning some switch on or off to represent a 0 or a 1.

Inside modern computers, there a billions of tiny switches called
transistors that can be turned on and off to represent different values.

The pattern to count in binary with multiple bits is the same as the
pattern in decimal with multiple digits. For example, we know the
following number in decimal represents one hundred and twenty-three.

1 2 3

The 3 is in the ones place, the 2 is in the tens place, and the 1 is in
the hundreds place. So 123 is 100×1 + 10×2 + 1×3 = 100 + 20 + 3 = 123.

To count higher than 7, we would need another bit to the left to
represent the number 8. Most computers use 8 bits at a time, like
00000011 for the number 3.

1.2. ASCII

There\'s a standard mapping of numbers to letters called ASCII
(*American Standard Code for Information Interchange*), which also
includes lowercase letters and punctuations.

Expanded map of ASCII values:

For example:

-   to represent \"A\", the number is 65, and in binary:

0 1 0 0 0 0 0 1

-   to represent \"B\", the number is 66, and in binary:

0 1 0 0 0 0 1 0

-   and so on.

Other characters, such as letters with accent marks, symbols, are part
of a standard called Unicode, which uses more than 8 bits for each
character, that ASCII uses.

When we receive an *emoji*, our computer is actually reveiving a number
in binary that it then maps to the image of the emoji based on the
Unicode standard. Also worth noting, companies that create software for
their devices will have slightly different images that represent each
emoji, because only the descriptions were standardized.

**1.3 Unicode**

-   As time has rolled on, there are more and more ways to communicate
    via text.

```{=html}
<!-- -->
```
-   Since there were not enough digits in binary to represent all the
    various characters that could be represented by humans, the
    *Unicode* standard expanded the number of bits that can be
    transmitted and understood by computers. Unicode includes not only
    special characters, but emoji as well.

```{=html}
<!-- -->
```
-   There are emoji that you probably use every day. The following may
    look familiar to you:

```{=html}
<!-- -->
```
-   While the pattern of zeros and one is standardized within Unicode,
    each device manufacturer may display each emoji slightly differently
    than another manufacturer.

```{=html}
<!-- -->
```
-   More and more features are being added to the Unicode standard to
    represent further characters and emoji.

```{=html}
<!-- -->
```
-   if you wish, you can learn more about
    [Unicode](https://en.wikipedia.org/wiki/Unicode).

```{=html}
<!-- -->
```
-   If you wish, you can learn more about
    [emoji](https://en.wikipedia.org/wiki/Emoji)

```{=html}
<!-- -->
```
-   **1.4 RGB**

-   Zeros and ones can be used to represent color.

-   \\Red, green, and blue (called RGB) is a combination of three
    numbers.

-   Taking our previously used 72, 73, and 33, which said HI! via text,
    would be interpreted by image readers as a light shade of yellow.
    The red value would be 72, the green value would be 73, and the blue
    would be 33.

-   The three bytes required to represent various colors of red, blue,
    and green (or *RGB*) make up each *pixel* (or dot) of color in any
    digital image. Images are simply collections of RGB values.

-   Zeros and ones can be used to represent images, videos, and music!

-   Videos are sequences of many images that are stored together, just
    like a flipbook.

-   Music can be represented similarly using various combinations of
    bytes

1.5 Algorithms

Now that we can represent *inputs* and *outputs*, we can work on problem
solving.

What stands between inputs(the problem) and outputs(the solution) are
algorithms, which basically means *step-by-step instructions for solving
our problems*.

Let\'s say we have an old-school phone book which contains names and
phone numbers.

-   We might open the book and start from the first page, looking for a
    name one page at a time. This algorithm is correct, since eventually
    we\'ll find the name if it\'s in the book.

-   We might flip through the book two pages at a time, but this
    algorithm would be incorrect since we might skip the page that
    contains the name.

-   Another algorithm would be opening the phone book in the middle,
    decide wether our name will be in the left half or right half of the
    book and reduce the size of our problem by half. We can repeat this
    until we find our name.

We can visualize the efficiency of each algorithms with this chart:

-   The first algorithm is represented by the red line. The \'*time to
    solve*\' increases linearly as the size of the problem increases.

-   The second algorithm is represented by the yellow line.

-   The third algoritm is represented by the green line. It has a
    different relationship between the *size of the problem* and the
    *time to solve it*.

1.6 Pseudocode

Pseudocode is a human-readable version of the code.

It\'s an important skill for many reasons.

-   First, when you *pseudocode* before creating the former code, it
    allows to thing through the logic of your problem in advance.

-   Secondly, you can later provide this information to others that are
    seeking to understand the decisions and how your code works.

The language within the pseudocode has some unique features.

-   some of the lines could begin with verbs such as: *pick up*, *open*,
    *close*, etc.

-   some lines include conditional statements, like *if*, or *else if*.

-   there are expressions that can be stated as *true* or *false*,
    called boolean expressions.

-   some lines have statements such as *go back to*, called loops.

Pseudocode is an algorithm implemented in human language:

1.  Pick up phone book

2.  Open to middle of phone book

3.  Look at page

4.  If person is on page

5.  \.....Call person

6.  Else if person is earlier in book

7.  \.....Open to middle of left half of book

8.  \.....Go back to line 3

9.  Else if person is later in book

10. \....Open to middle of right half of book

11. \....Go back to line 3

12. Else

13. \....Quit

-   1.6 Pseudocode\
    Consider how we can utilize the building blocks above to start
    creating our own artificial intelligence. Look at the following
    pseudocode:

-   If student says hello

Say hello

Else if student says goodbye

Say goodbye

Else if student asks how you are

Say well

Else if student asks why 111 in binary is 7 in decimal

...

-   Notice how just to program a handful of interactions, many lines of
    code would be required. How many lines of code would be required for
    thousands or tens of thousands of possible interactions?

-   Rather than programming conversational AI like the above, AI
    programmers train *large language models* (LLMs) on large datasets.

-   LLMs look at patterns in large blocks of language. Such language
    models attempt to create a best guess of what words come after one
    another or alongside one another.

-   As very useful in many avenues of life and work, we stipulate that
    the utilization of AI-based software other than CS50's own is *not
    reasonable*.

-   CS50's own AI-based software tool called [CS50.ai](https://cs50.ai/)
    is an AI helper that you can use during this course. It will help
    you, but not give away the entire answers to the course's problems.\
    You are not permitted to use any AI in this course except the
    [CS50.ai](https://cs50.ai/).

1\. 7 Scratch

-   Scratch is a graphical programming language developed at MIT\'s
    Media Lab.

```{=html}
<!-- -->
```
-   It contains the same features as more complex programming languages:
    variables, functions, loops, events.

-   Abstraction is when you and others agree take a complicated idea
    and, while you can implement it the more complex way, you will think
    about it on a simpler level.

-   Scratch utilizes the same essential coding building blocks that we
    covered earlier in this lecture.

-   Scratch is a great way to get into computer programming because it
    allows you to play with these building blocks in a visual manner,
    not having to be concerned about the syntax of curly braces,
    semicolons, parentheses, and the like
