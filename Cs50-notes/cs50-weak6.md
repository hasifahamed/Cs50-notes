## [**Python**](https://cs50.harvard.edu/x/2024/notes/6/#python)

> Humans, over the decades, have seen how previous design decisions
> could be improved upon.
>
> Python is a programming language that builds upon what you have
> already learned in C.
>
> Unlike in C, Python is an interpreted language, where you need not
> separately compile your program. Instead, you run your program in the
> *Python Interpreter*.

## [**Hello**](https://cs50.harvard.edu/x/2024/notes/6/#hello)

*\# A program that says hello to the world*  
  
print(\"hello, world\")

## [**Speller**](https://cs50.harvard.edu/x/2024/notes/6/#speller)

> To illustrate this simplicity, let's type 'code dictionary.py' in the
> terminal window and write code as follows:
>
> *\# Words in dictionary*  
> words = set()  
>   
>   
> **def** check(word):  
> \"\"\"Return true if word is in dictionary else false\"\"\"  
> **return** word.lower() **in** words  
>   
>   
> **def** load(dictionary):  
> \"\"\"Load dictionary into memory, returning true if successful else
> false\"\"\"  
> **with** open(dictionary) **as** file:  
> words.update(file.read().splitlines())  
> **return** True  
>   
>   
> **def** size():  
> \"\"\"Returns number of words in dictionary if loaded else 0 if not
> yet loaded\"\"\"  
> **return** len(words)  
>   
>   
> **def** unload():  
> \"\"\"Unloads dictionary from memory, returning true if successful
> else false\"\"\"  
> **return** True
>
> Notice that there are four functions above. In the check function, if
> a word is in words, it returns True. So much easier than an
> implementation in C! Similarly, in the load function the dictionary
> file is opened. For each line in that file, we add that line to words.
> Using rstrip, the trailing new line is removed from the added word.
> size simply returns the len or length of words. unload only needs to
> return True because Python handles memory management on its own.
>
> The above code illustrates why higher-level languages exist: To
> simplify and allow you to write code more easily.
>
> However, speed is a tradeoff. Because C allows you, the programmer, to
> make decisions about memory management, it may run faster than Python
> -- depending on your code. While C only runs your lines of code,
> Python runs all the code that comes under the hood with it when you
> call Python's built-in functions.
>
> You can learn more about functions in the [[Python
> documentation]{.underline}](https://docs.python.org/3/library/functions.html)

## [**CS50 Library**](https://cs50.harvard.edu/x/2024/notes/6/#cs50-library)

> As with C, the CS50 library can be utilized within Python.
>
> The following functions will be of particular use:
>
> get_float  
> get_int  
> get_string
>
> You also have the option of importing only specific functions from the
> CS50 library as follows:

## [**Strings**](https://cs50.harvard.edu/x/2024/notes/6/#strings)

*\# get_string and print, with format strings*  
  
**from** cs50 **import** get_string  
  
answer = get_string(\"What\'s your name? \")  
print(f\"hello, **{**answer**}**\")

## [**Variables**](https://cs50.harvard.edu/x/2024/notes/6/#variables)

> Variable declaration is simplified too. In C, you might have int
> counter = 0;. In Python, this same line would read counter = 0. You
> need not declare the type of the variable.
>
> Python favors counter += 1 to increment by one, losing the ability
> found in C to type counter++.

## [**Types**](https://cs50.harvard.edu/x/2024/notes/6/#types)

> Data types in Python do not need to be explicitly declared. For
> example, you saw how answer above is a string, but we did not have to
> tell the interpreter this was the case: It knew on its own.
>
> In Python, commonly used types include:
>
> bool  
> float  
> int  
> str
>
> Notice that long and double are missing. Python will handle what data
> type should be used for larger and smaller numbers.
>
> Some other data types in Python include:
>
> range  
> list  
> tuple  
> dict  
> set
>
> Each of these data types can be implemented in C, but in Python they
> can be implemented more simply.

## [**Conditionals**](https://cs50.harvard.edu/x/2024/notes/6/#conditionals)

**Difference b/w c and python in Conditional**

**C**

*// Conditionals, Boolean expressions, relational operators*  
  
\#include *\<cs50.h\>*  
\#include *\<stdio.h\>*  
  
int main(void)  
{  
*// Prompt user for integers*  
int x = get_int(\"What\'s x? \");  
int y = get_int(\"What\'s y? \");  
  
*// Compare integers*  
**if** (x \< y)  
{  
printf(\"x is less than y**\n**\");  
}  
**else** **if** (x \> y)  
{  
printf(\"x is greater than y**\n**\");  
}  
**else**  
{  
printf(\"x is equal to y**\n**\");  
}  
}

**PYTHON**

*\# Conditionals, Boolean expressions, relational operators*  
  
**from** cs50 **import** get_int  
  
*\# Prompt user for integers*  
x = get_int(\"What\'s x? \")  
y = get_int(\"What\'s y? \")  
  
*\# Compare integers*  
**if** x \< y:  
print(\"x is less than y\")  
**elif** x \> y:  
print(\"x is greater than y\")  
**else**:  
print(\"x is equal to y\")

## [**Object-Oriented Programming**](https://cs50.harvard.edu/x/2024/notes/6/#object-oriented-programming)

> Up until this point, our programs in this course have been linear:
> sequential.
>
> It's possible to have certain types of values not only have properties
> or attributes inside of them but have functions as well. In Python,
> these values are known as *objects*
>
> In C, we could create a struct where you could associate multiple
> variables inside a single self-created data type. In Python, we can do
> this and also include functions in a self-created data type. When a
> function belongs to a specific *object*, it is known as a *method*.
>
> For example, strs in Python have a built-in *methods*. Therefore, you
> could modify your code as follows:
>
> *\# Logical operators, using lists*  
>   
> **from** cs50 **import** get_string  
>   
> *\# Prompt user to agree*  
> s = get_string(\"Do you agree? \").lower()  
>   
> *\# Check whether agreed*  
> **if** s.lower() **in** \[\"y\", \"yes\"\]:  
> print(\"Agreed.\")  
> **elif** s.lower() **in** \[\"n\", \"no\"\]:  
> print(\"Not agreed.\")
>
> Notice how the old value of s is overwritten with the result of
> s.lower(), a built-in method of strs.
>
> In this class, we will only scratch the surface of Python. Therefore,
> the [[Python documentation]{.underline}](https://docs.python.org/)
> will be of particular importance as you continue.
>
> You can learn more about string methods in the [[Python
> documentation]{.underline}](https://docs.python.org/3/library/stdtypes.html#string-methods)

## [**Loops**](https://cs50.harvard.edu/x/2024/notes/6/#loops)

> In Python, this code appears as:
>
> *\# Demonstrates while loop*  
>   
> i = 0  
> **while** i \< 3:  
> print(\"meow\")  
> i += 1
>
> for loops can be implemented in Python as follows:
>
> *\# Better design*  
>   
> **for** i **in** range(3):  
> print(\"meow\")

## [**Abstraction**](https://cs50.harvard.edu/x/2024/notes/6/#abstraction)

> As we hinted at earlier today, you can further improve upon our code
> using functions and abstracting away various code into functions.
> Modify your earlier-created meow.py code as follows:
>
> *\# Abstraction*  
>   
> **def** main():  
> **for** i **in** range(3):  
> meow()  
>   
> *\# Meow once*  
> **def** meow():  
> print(\"meow\")  
>   
>   
> main()
>
> Notice that the meow function abstracts away the print statement.
> Further, notice that the main function appears at the top of the file.
> At the bottom of the file, the main function is called. By convention,
> it's expected that you create a main function in Python.
>
> Indeed, we can pass variables between our functions as follows:
>
> *\# Abstraction with parameterization*  
>   
> **def** main():  
> meow(3)  
>   
>   
> *\# Meow some number of times*  
> **def** meow(n):  
> **for** i **in** range(n):  
> print(\"meow\")  
>   
>   
> main()
>
> Notice how meow now takes a variable n. In the main function, you can
> call meow and pass a value like 3 to it. Then, meow utilizes the value
> of n in the for loop.
>
> Reading the above code, notice how you, as a C programmer, are able to
> quite easily make sense of the above code. While some conventions are
> different, the building blocks you previously learned are very
> apparent in this new programming language.

## [**Truncation and Floating Point Imprecision**](https://cs50.harvard.edu/x/2024/notes/6/#truncation-and-floating-point-imprecision)

> Recall that in C, we experienced truncation where one integer being
> divided by another could result in an inprecise result.
>
> You can see how Python handles such division as follows by modifying
> your code for calculator.py:
>
> *\# Division with integers, demonstration lack of truncation*  
>   
> *\# Prompt user for x*  
> x = int(input(\"x: \"))  
>   
> *\# Prompt user for y*  
> y = int(input(\"y: \"))  
>   
> *\# Divide x by y*  
> z = x / y  
> print(z)
>
> Notice that executing this code results in a value, but that if you
> were to see more digits after .333333 you'd see that we are faced with
> *floating-point imprecision*. Truncation does not occur.
>
> We can reveal this imprecision by modifying our codes slightly:
>
> *\# Floating-point imprecision*  
>   
> *\# Prompt user for x*  
> x = int(input(\"x: \"))  
>   
> *\# Prompt user for y*  
> y = int(input(\"y: \"))  
>   
> *\# Divide x by y*  
> z = x / y  
> print(f\"**{**z**:**.50f**}**\")
>
> Notice that this code reveals the imprecision. Python still faces this
> issue, just as C does.

## [**Exceptions**](https://cs50.harvard.edu/x/2024/notes/6/#exceptions)

> Let's explore more about exceptions that can occur when we run Python
> code.
>
> Modify calculator.py as follows:
>
> *\# Implements get_int*  
>   
> **def** get_int(prompt):  
> **return** int(input(prompt))  
>   
>   
> **def** main():  
>   
> *\# Prompt user for x*  
> x = get_int(\"x: \")  
>   
> *\# Prompt user for y*  
> y = get_int(\"y: \")  
>   
> *\# Perform addition*  
> print(x + y)  
>   
>   
> main()
>
> Notice that inputting the wrong data could result in an error.
>
> We can try to handle and *catch* potential exceptions by modifying our
> code as follows:
>
> *\# Implements get_int with a loop*  
>   
> **def** get_int(prompt):  
> **while** True:  
> **try**:  
> **return** int(input(prompt))  
> **except** ValueError:  
> print(\"Not an integer\")  
>   
>   
> **def** main():  
>   
> *\# Prompt user for x*  
> x = get_int(\"x: \")  
>   
> *\# Prompt user for y*  
> y = get_int(\"y: \")  
>   
> *\# Perform addition*  
> print(x + y)  
>   
>   
> main()
>
> Notice that the above code repeatedly tries to get the correct type of
> data, providing additional prompts when needed.

## [**Lists**](https://cs50.harvard.edu/x/2024/notes/6/#lists)

> lists are a data structure within Python.
>
> lists have built in methods or functions within them.
>
> For example, consider the following code:
>
> *\# Averages three numbers using a list*  
>   
> *\# Scores*  
> scores = \[72, 73, 33\]  
>   
> *\# Print average*  
> average = sum(scores) / len(scores)  
> print(f\"Average: **{**average**}**\")
>
> Notice that you can use the built-in sum method to calculate the
> average.
>
> You can even utilize the following syntax to get values from the user:
>
> *\# Averages three numbers using a list and a loop*  
>   
> **from** cs50 **import** get_int  
>   
> *\# Get scores*  
> scores = \[\]  
> **for** i **in** range(3):  
> score = get_int(\"Score: \")  
> scores.append(score)  
>   
> *\# Print average*  
> average = sum(scores) / len(scores)  
> print(f\"Average: **{**average**}**\")
>
> Notice that this code utilizes the built-in append method for lists.
>
> You can learn more about lists in the [[Python
> documentation]{.underline}](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range)
>
> You can also learn more about len in the [[Python
> documentation]{.underline}](https://docs.python.org/3/library/functions.html#len)

## [**Searching and Dictionaries**](https://cs50.harvard.edu/x/2024/notes/6/#searching-and-dictionaries)

> We can also search within a data structure.
>
> Consider a program called phonebook.py as follows:
>
> *\# Implements linear search for names using loop*  
>   
> *\# A list of names*  
> names = \[\"Carter\", \"David\", \"John\"\]  
>   
> *\# Ask for name*  
> name = input(\"Name: \")  
>   
> *\# Search for name*  
> **for** n **in** names:  
> **if** name == n:  
> print(\"Found\")  
> **break**  
> **else**:  
> print(\"Not found\")
>
> Notice how this implements linear search for each name.
>
> However, we don't need to iterate through a list. In Python, we can
> execute linear search as follows:
>
> *\# Implements linear search for names using \`in\`*  
>   
> *\# A list of names*  
> names = \[\"Carter\", \"David\", \"John\"\]  
>   
> *\# Ask for name*  
> name = input(\"Name: \")  
>   
> *\# Search for name*  
> **if** name **in** names:  
> print(\"Found\")  
> **else**:  
> print(\"Not found\")
>
> Notice how in is used to implement linear search.
>
> Still, this code could be improved.
>
> Recall that a *dictionary* or dict is a collection of *key* and
> *value* pairs.
>
> You can implement a dictionary in Python as follows:
>
> *\# Implements a phone book as a list of dictionaries, without a
> variable*  
>   
> **from** cs50 **import** get_string  
>   
> people = \[  
> {\"name\": \"Carter\", \"number\": \"+1-617-495-1000\"},  
> {\"name\": \"David\", \"number\": \"+1-617-495-1000\"},  
> {\"name\": \"John\", \"number\": \"+1-949-468-2750\"},  
> \]  
>   
> *\# Search for name*  
> name = get_string(\"Name: \")  
> **for** person **in** people:  
> **if** person\[\"name\"\] == name:  
> print(f\"Found **{**person\[\'number\'\]**}**\")  
> **break**  
> **else**:  
> print(\"Not found\")
>
> Notice that the dictionary is implemented having both name and number
> for each entry.
>
> Even better, strictly speaking, we don't need both a name and a
> number. We can simplify this code as follows:
>
> *\# Implements a phone book using a dictionary*  
>   
> **from** cs50 **import** get_string  
>   
> people = {  
> \"Carter\": \"+1-617-495-1000\",  
> \"David\": \"+1-617-495-1000\",  
> \"John\": \"+1-949-468-2750\",  
> }  
>   
> *\# Search for name*  
> name = get_string(\"Name: \")  
> **if** name **in** people:  
> print(f\"Number: **{**people\[name\]**}**\")  
> **else**:  
> print(\"Not found\")
>
> Notice that the dictionary is implemented using curly braces. Then,
> the statement if name in people searches to see if the name is in the
> people dictionary. Further, notice how, in the print statement, we can
> index into the people dictionary using the value of name. Very useful!
>
> Python has done their best to get to *constant time* using their
> built-in searches.
>
> You can learn more about dictionaries in the [[Python
> documentation]{.underline}](https://docs.python.org/3/library/stdtypes.html#dict)

## [**Command-Line Arguments**](https://cs50.harvard.edu/x/2024/notes/6/#command-line-arguments)

> As with C, you can also utilize command-line arguments. Consider the
> following code:
>
> *\# Prints a command-line argument*  
>   
> **from** sys **import** argv  
>   
> **if** len(argv) == 2:  
> print(f\"hello, **{**argv\[1\]**}**\")  
> **else**:  
> print(\"hello, world\")
>
> Notice that argv\[1\] is printed using a *formatted string*, noted by
> the f present in the print statement.
>
> You can print all the arguments in argv as follows:
>
> *\# Printing command-line arguments, indexing into argv*  
>   
> **from** sys **import** argv  
>   
> **for** i **in** range(len(argv)):  
> print(argv\[i\])
>
> Notice that the above will not present the word python if executed,
> and the first argument will be the name of the file you are running.
> You can think of the word python as being analogous to ./ when we were
> running programs in C.
>
> You can slice pieces of lists away. Consider the following code:
>
> *\# Printing command-line arguments*  
>   
> **from** sys **import** argv  
>   
> **for** arg **in** argv:  
> print(arg)
>
> Notice that executing this code will result in the name of the file
> you are running being sliced away.
>
> You can learn more about the sys library in the [[Python
> documentation]{.underline}](https://docs.python.org/3/library/sys.html)

## [**Exit Status**](https://cs50.harvard.edu/x/2024/notes/6/#exit-status)

> The sys library also has built-in methods. We can use sys.exit(i) to
> exit the program with a specific exit code:
>
> *\# Exits with explicit value, importing sys*  
>   
> **import** sys  
>   
> **if** len(sys.argv) != 2:  
> print(\"Missing command-line argument\")  
> sys.exit(1)  
>   
> print(f\"hello, **{**sys.argv\[1\]**}**\")  
> sys.exit(0)
>
> Notice that dot-notation is used to utilize the built-in functions of
> sys.

## [**Third-Party Libraries**](https://cs50.harvard.edu/x/2024/notes/6/#third-party-libraries)

> One of the advantages of Python is its massive user-base and similarly
> large number of third-party libraries.
>
> For example, David demoed the use of cowsay and qrcode libraries.
