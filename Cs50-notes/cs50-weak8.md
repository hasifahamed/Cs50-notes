**SQL**

> Finally, we will be discussing *SQL* or *Structured Query Language*, a
> domain-specific way by which we can interact with and modify data.
>
> Overall, one of the goals of this course is to learn to program
> generally -- not simply how to program in the languages described in
> this course.

# 1. Flat-file Databases {#flat-file-databases}

A **flat-file database** is a **database** stored in a file called a
*flat file*. Records follow a uniform format, and there are no
structures for indexing or recognizing relationship between records.
Relationships can be inferred from the data in the **database**, but the
format of the **database** doesn\'t make those relationships explicit.

A flat file can be a **plain text file** (csv, tsv, txt) or a **binary
file**.

The **records** in the **database** are separated by delimiters such as
*tabs* or *commas* and each line holds only one record.

## 1.1. Advantages of Flat-file Databases {#advantages-of-flat-file-databases}

- all records are stored in one place;

- easy to understand and configure;

- an excellent option for small databases;

- requires less hardware and software components;

## 1.2. Disadvantages of Flat-file Databases {#disadvantages-of-flat-file-databases}

- they are harder to update;

- harder to change data format;

- poor in terms of complex queries;

- increased redundancy and inconsistency;

# 1. Relational Databases {#relational-databases}

A **relational database** is a type of **database** that stores and
provides access to data points that are *related to one another*.
**Relational databases** are based on the *relational model*, which is a
way of representing data in **tables**. Each row in the **table** is a
record with a unique ID called **key**. The columns of the **table**
hold attributes of the data, and each record usually has a value of each
attribute, making it easy to establish relationships among data points.

**SQL** or **Structured Query Language** is used to write and query data
in the **database**. **SQL** allows for four types of commands:
*create*, *read*, *update*, and *delete*, also known as *CRUD*.

Although **SQL** is the standard *ANSI*/*ISO*, there are different
versions of the language. Most of the **SQL** **database** programs have
their own proprietary extensions in addition to the SQL standard.

A **relational database management system** or **RDBMS** is a program
used to create, update and manage such **databases**.

## 1.1. Database Schema {#database-schema}

The **database schema** is the skeleton structure of the **database**
described in a *formal language* supported by the **database management
system**. The term *schema* refers to the organization of data as a
blueprint of how the database is constructed (divided into database
tables).

## 1.2. Relational Model {#relational-model}

The **relational database model** allows any table to be related to
another table using a common attribute. Instead of using hierarchical
structures to organize data, the data is stored, accessed and related in
tables without reorganizing the tables that contain them.

### 1.2.1. Types of Relational Models {#types-of-relational-models}

There are three types of relational models in **DBMS**.

1.  **One-to-Many Model**

In this type of relationship, one entity is related to multiple other
entities. The key feature of the model is that the relationship between
two entities is not reciprocal. For example, a customer can have
multiple orders on a website, but that order cannot have multiple
customers.

2.  **One-to-One Model**

The **one-to-one model** states that there is a direct and unique
relationship between two specific objects. In other words, each object
can only be related to one other object and vice versa. This type of
relationship is often used to represent relations between physical
things, such as people and their driver\'s license number.

3.  **Many-to-Many Model**

In a **many-to-many model**, each record in the primary table can be
linked to multiple records in the foreign table and vice versa. This
type of relationship is less common. One such example migh be between
students and courses. A student can take multiple courses and a course
can have multiple students enrolled.

## 1.3. Primary Key & Foreign Key {#primary-key-foreign-key}

The **primary key** constraint uniquely identifies each record in a
table. **Primary keys** must be *unique* and cannot contain *null
values*. A table can only have one **primary key** and the **key** can
consist of single or multiple columns (fields).

The **foreign key** constraint is used to prevent actions that would
destroy links between tables, so it\'s a field or a collection of fields
in one table, that refers to the **primary key** in another table.

The table with the **foreign key** is called the *child* table, and the
table with the **primary key** is the *referenced* or *parent* table.

## 1.4. Example {#example}

### **Employees Table**

| **PersonID** | **LastName** | **FirstName** | **Age** |
|--------------|--------------|---------------|---------|
| 1            | Halpert      | Jim           | 28      |
| 2            | Scott        | Michael       | 42      |
| 3            | Beesly       | Pam           | 26      |
| 4            | Schrute      | Dwight        | 34      |
| 5            | Malone       | Kevin         | 39      |

### **Sales Table**

| **SaleID** | **SaleNumber** | **PersonID** |
|------------|----------------|--------------|
| 1          | 4985           | 1            |
| 2          | 3455           | 4            |
| 3          | 2321           | 2            |
| 4          | 6752           | 1            |
| 5          | 8795           | 3            |

- the *PersonID* column in the **Sales Table** points to the *PersonID*
  in the **Employees Table**;

- the *PersonID* in the **Employees Table** is the **Primary Key** in
  the **Employees Table**;

- the *PersonID* in the **Sales Table** is the **Foreign Key** in the
  **Sales Table**;

- the relationship between the two is **one-to-many**, an employee can
  have multiple sales, but that sale cannot have multiple employees, in
  this case.

> Google, X, and Meta all use relational databases to store their
> information at scale.
>
> **Relational database**
>
> Relational databases store data in rows and columns in structures
> called *tables*.
>
> SQL allows for four types of commands:
>
> Create  
> Read  
> Update  
> Delete
>
> These four operations are affectionately called *CRUD*.
>
> We can create a database with the SQL syntax CREATE TABLE table
> (column type, \...);. But where do you run this command?
>
> sqlite3 is a type of SQL database that has the core features required
> for this course.
>
> We can create a SQL database at the terminal by typing sqlite3
> favorites.db. Upon being prompted, we will agree that we want to
> create favorites.db by pressing y.
>
> You will notice a different prompt as we are now using a program
> called sqlite.
>
> We can put sqlite into csv mode by typing .mode csv. Then, we can
> import our data from our csv file by typing .import favorites.csv
> favorites. It seems that nothing has happened!
>
> We can type .schema to see the structure of the database.
>
> You can read items from a table using the syntax SELECT columns FROM
> table.
>
> For example, you can type SELECT \* FROM favorites; which will print
> every row in favorites.
>
> You can get a subset of the data using the command SELECT language
> FROM favorites;.
>
> SQL supports many commands to access data, including:
>
> AVG  
> COUNT  
> DISTINCT  
> LOWER  
> MAX  
> MIN  
> UPPER
>
> For example, you can type SELECT COUNT(\*) FROM favorites;. Further,
> you can type SELECT DISTINCT language FROM favorites; to get a list of
> the individual languages within the database. You could even type
> SELECT COUNT(DISTINCT language) FROM favorites; to get a count of
> those.
>
> SQL offers additional commands we can utilize in our queries:
>
> **WHERE** *\-- adding a Boolean expression to filter our data*  
> **LIKE** *\-- filtering responses more loosely*  
> **ORDER** **BY** *\-- ordering responses*  
> **LIMIT** *\-- limiting the number of responses*  
> **GROUP** **BY** *\-- grouping responses together*
>
> Notice that we use \-- to write a comment in SQL.

## [**SELECT**](https://cs50.harvard.edu/x/2025/notes/7/#select)

> For example, we can execute SELECT COUNT(\*) FROM favorites WHERE
> language = \'C\';. A count is presented.
>
> Further, we could type SELECT COUNT(\*) FROM favorites WHERE language
> = \'C\' AND problem = \'Hello, World;. Notice how the AND is utilized
> to narrow our results.
>
> Similarly, we could execute SELECT language, COUNT(\*) FROM favorites
> GROUP BY language;. This would offer a temporary table that would show
> the language and count.
>
> We could improve this by typing SELECT language, COUNT(\*) FROM
> favorites GROUP BY language ORDER BY COUNT(\*);. This will order the
> resulting table by the count.
>
> Likewise, we could execute SELECT COUNT(\*) FROM favorites WHERE
> language = \'C\' AND (problem = \'Hello, World\' OR problem = \'Hello,
> It\'\'s Me\');. Do notice that there are two \'\' marks as to allow
> the use of single quotes in a way that does not confuse SQL.
>
> Further, we could execute SELECT COUNT(\*) FROM favorites WHERE
> language = \'C\' AND problem LIKE \'Hello, %\'; to find any problems
> that start with Hello, (including a space).
>
> We can also group the values of each language by executing SELECT
> language, COUNT(\*) FROM favorites GROUP BY language;.
>
> We can order the output as follows: SELECT language, COUNT(\*) FROM
> favorites GROUP BY language ORDER BY COUNT(\*) DESC;.
>
> We can even create aliases, like variables in our queries: SELECT
> language, COUNT(\*) AS n FROM favorites GROUP BY language ORDER BY n
> DESC;.
>
> Finally, we can limit our output to 1 or more values: SELECT language,
> COUNT(\*) AS n FROM favorites GROUP BY language ORDER BY n DESC LIMIT
> 1;.

## [**INSERT**](https://cs50.harvard.edu/x/2025/notes/7/#insert)

> We can also INSERT into a SQL database utilizing the form INSERT INTO
> table (column\...) VALUES(value, \...);.
>
> We can execute INSERT INTO favorites (language, problem) VALUES
> (\'SQL\', \'Fiftyville\');.
>
> You can verify the addition of this favorite by executing SELECT \*
> FROM favorites;.

## [**DELETE**](https://cs50.harvard.edu/x/2025/notes/7/#delete)

> DELETE allows you to delete parts of your data. For example, you could
> DELETE FROM favorites WHERE Timestamp IS NULL;. This deletes any
> record where the Timestamp is NULL.

## [**UPDATE**](https://cs50.harvard.edu/x/2025/notes/7/#update)

> We can also utilize the UPDATE command to update your data.
>
> For example, you can execute UPDATE favorites SET language = \'SQL\',
> problem = \'Fiftyville\';. This will result in overwriting all
> previous statements where C and Scratch were the favorite programming
> language.
>
> Notice that these queries have immense power. Accordingly, in the
> real-world setting, you should consider who has permissions to execute
> certain commands and if you have backups available!

## [**IMDb**](https://cs50.harvard.edu/x/2025/notes/7/#imdb)

> We can imagine a database that we might want to create to catalog
> various TV shows. We could create a spreadsheet with columns like
> title, star, star, star, star, and more stars. A problem with this
> approach is that it has a lot of wasted space. Some shows may have one
> star. Others may have dozens.
>
> We could separate our database into multiple sheets. We could have a
> shows sheet, a stars sheet, and a people sheet. On the people sheet,
> each person could have a unique id. On the shows sheet, each show
> could have a unique id too. On a third sheet called stars we could
> relate how each show has people for each show by having a show_id and
> person_id. While this is an improvement, this is not an ideal
> database.
>
> IMDb offers a database of people, shows, writers, stars, genres, and
> ratings. Each of these tables is related to one another as follows:
>
> ![six boxes that represent various sql tables arrows are drawn to each
> showing their many relationships with one
> another](/media/image.png){width="6.260415573053368in"
> height="3.5208333333333335in"}
>
> After downloading
> [[shows.db]{.underline}](https://cdn.cs50.net/2024/fall/lectures/7/src7/imdb/shows.db),
> you can execute sqlite3 shows.db in your terminal window.
>
> Let's zero in on the relationship between two tables within the
> database called shows and ratings. The relationship between these two
> tables can be illustrated as follows:
>
> ![two boxes one called shows and the other called
> ratings](/media/image2.png){width="6.260415573053368in"
> height="3.5208333333333335in"}
>
> To illustrate the relationship between these tables, we could execute
> the following command: SELECT \* FROM ratings LIMIT 10;. Examining the
> output, we could execute SELECT \* FROM shows LIMIT 10;.
>
> Examining shows and rating, we can see these have a one-to-one
> relationship: One show has one rating.
>
> To understand the database, upon executing .schema you will find not
> only each of the tables but the individual fields inside each of these
> fields.
>
> More specifically, you could execute .schema shows to understand the
> fields inside shows. You can also execute .schema ratings to see the
> fields inside ratings.
>
> As you can see, show_id exists in all of the tables. In the shows
> table, it is simply called id. This common field between all the
> fields is called a *key*. Primary keys are used to identify a unique
> record in a table. *Foreign keys* are used to build relationships
> between tables by pointing to the primary key in another table. You
> can see in the schema of ratings that show_id is a foreign key that
> references id in shows.
>
> By storing data in a relational database, as above, data can be more
> efficiently stored.
>
> In *sqlite*, we have five data types, including:
>
> BLOB *\-- binary large objects that are groups of ones and zeros*  
> INTEGER *\-- an integer*  
> NUMERIC *\-- for numbers that are formatted specially like dates*  
> REAL *\-- like a float*  
> TEXT *\-- for strings and the like*
>
> Additionally, columns can be set to add special constraints:
>
> NOT NULL  
> UNIQUE
>
> We can further play with this data to understand these relationships.
> Execute SELECT \* FROM ratings;. There are a lot of ratings!
>
> We can further limit this data down by executing SELECT show_id FROM
> ratings WHERE rating \>= 6.0 LIMIT 10;. From this query, you can see
> that there are 10 shows presented. However, we don't know what show
> each show_id represents.
>
> You can discover what shows these are by executing SELECT \* FROM
> shows WHERE id = 626124;
>
> We can further our query to be more efficient by executing:
>
> **SELECT** title  
> **FROM** shows  
> **WHERE** id **IN** (  
> **SELECT** show_id  
> **FROM** ratings  
> **WHERE** rating \>= 6.0  
> **LIMIT** 10  
> )
>
> Notice that this query nests together two queries. An inner query is
> used by an outer query.

## [**JOINs**](https://cs50.harvard.edu/x/2025/notes/7/#joins)

> We are pulling data from shows and ratings. Notice how both shows and
> ratings have an id in common.
>
> How could we combine tables temporarily? Tables could be joined
> together using the JOIN command.
>
> Execute the following command:
>
> **SELECT** \* **FROM** shows  
> **JOIN** ratings **on** shows.id = ratings.show_id  
> **WHERE** rating \>= 6.0  
> **LIMIT** 10;
>
> Notice this results in a wider table than we have previously seen.
>
> Where the previous queries have illustrated the *one-to-one*
> relationship between these keys, let's examine some *one-to-many*
> relationships. Focusing on the genres table, execute the following:
>
> **SELECT** \* **FROM** genres  
> **LIMIT** 10;
>
> Notice how this provides us a sense of the raw data. You might notice
> that one show has three values. This is a one-to-many relationship.
>
> We can learn more about the genres table by typing .schema genres.
>
> Execute the following command to learn more about the various comedies
> in the database:
>
> **SELECT** title **FROM** shows  
> **WHERE** id **IN** (  
> **SELECT** show_id **FROM** genres  
> **WHERE** genre = \'Comedy\'  
> **LIMIT** 10  
> );
>
> Notice how this produces a list of comedies, including *Catweazle*.
>
> To learn more about Catweazle, by joining various tables through a
> join:
>
> **SELECT** \* **FROM** shows  
> **JOIN** genres  
> **ON** shows.id = genres.show_id  
> **WHERE** id = 63881;
>
> Notice that this results in a temporary table. It is fine to have a
> duplicate table.
>
> In contrast to one-to-one and one-to-many relationships, there may be
> *many-to-many* relationships.
>
> We can learn more about the show *The Office* and the actors in that
> show by executing the following command:
>
> **SELECT** name **FROM** people **WHERE** id **IN**  
> (**SELECT** person_id **FROM** stars **WHERE** show_id =  
> (**SELECT** id **FROM** shows **WHERE** title = \'The Office\' **AND**
> year = 2005));
>
> Notice that this results in a table that includes the names of various
> stars through nested queries.
>
> We find all the shows in which Steve Carell starred:
>
> **SELECT** title **FROM** shows **WHERE** id **IN**  
> (**SELECT** show_id **FROM** stars **WHERE** person_id =  
> (**SELECT** id **FROM** people **WHERE** name = \'Steve Carell\'));
>
> This results in a list of titles of shows wherein Steve Carell
> starred.
>
> This could also be expressed in this way:
>
> **SELECT** title **FROM** shows, stars, people  
> **WHERE** shows.id = stars.show_id  
> **AND** people.id = stars.person_id  
> **AND** name = \'Steve Carell\';
>
> The wildcard % operator can be used to find all people whose names
> start with Steve C one could employ the syntax SELECT \* FROM people
> WHERE name LIKE \'Steve C%\';.

## [**Indexes**](https://cs50.harvard.edu/x/2025/notes/7/#indexes)

> While relational databases have the ability to be faster and more
> robust than utilizing a CSV file, data can be optimized within a table
> using *indexes*.
>
> Indexes can be utilized to speed up our queries.
>
> We can track the speed of our queries by executing .timer on in
> sqlite3.
>
> To understand how indexes can speed up our queries, run the following:
> SELECT \* FROM shows WHERE title = \'The Office\'; Notice the time
> that displays after the query executes.
>
> Then, we can create an index with the syntax CREATE INDEX title_index
> ON shows (title);. This tells sqlite3 to create an index and perform
> some special under-the-hood optimization relating to this column
> title.
>
> This will create a data structure called a *B Tree*, a data structure
> that looks similar to a binary tree. However, unlike a binary tree,
> there can be more than two child notes.
>
> ![one node at the top from which come four children and below that
> there are three children coming from one of the nodes and two from
> another two from another and three from
> another](/media/image3.png){width="6.260415573053368in"
> height="3.5208333333333335in"}
>
> Further, we can create indexes as follows:
>
> **CREATE** **INDEX** name_index **ON** people (name);  
> **CREATE** **INDEX** person_index **ON** stars (person_id);
>
> Running the query and you will notice that the query runs much more
> quickly!
>
> **SELECT** title **FROM** shows **WHERE** id **IN**  
> (**SELECT** show_id **FROM** stars **WHERE** person_id =  
> (**SELECT** id **FROM** people **WHERE** name = \'Steve Carell\'));
>
> Unfortunately, indexing all columns would result in utilizing more
> storage space. Therefore, there is a tradeoff for enhanced speed.

## [**Using SQL in Python**](https://cs50.harvard.edu/x/2025/notes/7/#using-sql-in-python)

> To assist in working with SQL in this course, the CS50 Library can be
> utilized as follows in your code:
>
> **from** cs50 **import** SQL
>
> Similar to previous uses of the CS50 Library, this library will assist
> with the complicated steps of utilizing SQL within your Python code.
>
> You can read more about the CS50 Library's SQL functionality in the
> [[documentation]{.underline}](https://cs50.readthedocs.io/libraries/cs50/python/#cs50.SQL).
>
> Using our new knowledge of SQL, we can now leverage Python alongside.
>
> Modify your code for favorites.py as follows:
>
> *\# Searches database popularity of a problem*  
>   
> **from** cs50 **import** SQL  
>   
> *\# Open database*  
> db = **SQL**(\"sqlite:///favorites.db\")  
>   
> *\# Prompt user for favorite*  
> favorite = input(\"Favorite: \")  
>   
> *\# Search for title*  
> rows = db.execute(\"SELECT COUNT(\*) AS n FROM favorites WHERE
> language = ?\", favorite)  
>   
> *\# Get first (and only) row*  
> row = rows\[0\]  
>   
> *\# Print popularity*  
> print(row\[\"n\"\])
>
> Notice that db = SQL(\"sqlite:///favorites.db\") provides Python the
> location of the database file. Then, the line that begins with rows
> executes SQL commands utilizing db.execute. Indeed, this command
> passes the syntax within the quotation marks to the db.execute
> function. We can issue any SQL command using this syntax. Further,
> notice that rows is returned as a list of dictionaries. In this case,
> there is only one result, one row, returned to the rows list as a
> dictionary.

## [**Race Conditions**](https://cs50.harvard.edu/x/2025/notes/7/#race-conditions)

> Utilization of SQL can sometimes result in some problems.
>
> You can imagine a case where multiple users could be accessing the
> same database and executing commands at the same time.
>
> This could result in glitches where code is interrupted by other
> people's actions. This could result in a loss of data.
>
> Built-in SQL features such as BEGIN TRANSACTION, COMMIT, and ROLLBACK
> help avoid some of these race condition problems.

## [**SQL Injection Attacks**](https://cs50.harvard.edu/x/2025/notes/7/#sql-injection-attacks)

> Now, still considering the code above, you might be wondering what the
> ? question marks do above. One of the problems that can arise in
> real-world applications of SQL is what is called an *injection
> attack*. An injection attack is where a malicious actor could input
> malicious SQL code.
>
> For example, consider a login screen as follows:
>
> ![harvard key login screen with username and password
> fields](/media/image4.png){width="6.260415573053368in"
> height="3.5208333333333335in"}
>
> Without the proper protections in our own code, a bad actor could run
> malicious code. Consider the following:
>
> rows = db.execute(\"SELECT COUNT(\*) FROM users WHERE username = ? AND
> password = ?\", username, password)
>
> Notice that because the ? is in place, validation can be run on
> favorite before it is blindly accepted by the query.
>
> You never want to utilize formatted strings in queries as above or
> blindly trust the user's input.
>
> Utilizing the CS50 Library, the library will *sanitize* and remove any
> potentially malicious characters.
