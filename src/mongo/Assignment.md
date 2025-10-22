# Assignment 3 - Mongo

## Part 1 (10 pts): Day 1 - Reading

1. Read Day 1 and work through the examples. Dump your database into a
    directory named data.

## Part 2 (10 pts): Day 1 - Find

Complete the "Find" homework in Day 1.

1. Bookmark the online MongoDB documentation and read up on something
    you found intriguing today. Provide the URL.
https://www.mongodb.com/docs/manual/

2. Look up how to construct regular expressions in Mongo. Provide the URL.

https://www.mongodb.com/docs/manual/reference/operator/query/regex/

3. Acquaint yourself with command-line db.help() and db.collections.help() output.
    Nothing to provide.

4. Find a Mongo driver in your programming language of choice (Ruby, Java,
    PHP, Go, Elixir, and so on). Provide URL to list of drivers/libraries for
    different languages.
https://www.mongodb.com/docs/drivers/?

## Part 3 (15 pts): Create and populate a database to hold library books and patrons.
For each of the steps below, provide the mongodb code that accomplishes this. Store your work in a folder called “Library”.

### Step 1: Create the Database

For this assignment, you will be working with the two collections described below. **Use the exact document and attribute names provided!**
* books - stores information about library books
    * Should use attributes of:  title, author, isbn, genre, publishedYear, copiesAvailable, and totalCopies
    * Make sure that some of your books are in the “Fiction” genre and some are in “Non-Fiction”
    * Make sure that at least two of your books have copies available to check out.
* patrons - stores information about library members
    * Should use attributes of:    name, email, membershipDate, booksCheckedOut (array of title and dueDate), and fines.
    * Make sure that at least one of your patrons has checked out more than one book.
    * Make sure that at least one of your patrons has an overdue fine.
    * Make sure that at least one of your patrons joined the library in 2004.

### Step 2: Insert Books into the Library
Insert six of your favorite books into the library.  Make sure that these are your favorite books, not randomly generated books.

### Step 3: Insert Patrons into the Library
Insert five of your friends as patrons into the library. Make sure that these are not randomly generated.

### Step 4: Queries
For each of the queries below, write the query and include the results.

1. Write a query to find the titles of all books that have at least one copy available for checkout.
"" db.books.find(  { copiesAvailable: { $gt: 0 } },     { title: 1, _id: 0 })""

2. Write a query to find the authors of all books in the "Fiction" genre.
""db.books.find({ genre: "Fiction" }, { author: 1, _id: 0 })""

3. Write a query to find the names of all patrons who owe fines (fines greater than $0).
""db.patrons.find({ fines: { $gt: 0 } }, { name: 1, _id: 0 })""

4. Write a query to find the names and membership date of all patrons who became members in the year 2024.
""db.patrons.find({ membershipDate: { $gte: new Date("01/01/2024"), $lt: new Date("01/01/2025") } }, { name: 1, membershipDate: 1, _id: 0 })""


Hint: Use $gte and $lt operators to specify a date range from January 1, 2024 to January 1, 2025.

## Part 4 (10 pts): Day 2 - Do

Complete the "Find" homework in Day 2.

1. Find a shortcut for admin commands. Write the shortcut here.
""db.adminCommand()""


2. Find the online documentation for queries and cursors. Write the URL here.
""https://www.mongodb.com/docs/manual/tutorial/query-documents/""


3. Find the MongoDB documentation for mapreduce. Write the URL here.
""https://www.mongodb.com/docs/manual/core/map-reduce/""


4. Through the JavaScript interface, investigate the code for three collections
    functions: help(), findOne(), and stats(). Past the code for each below.
    For each, write a one-sentence insight that you learned by looking at
    the code.
""db.help(): It helps me see what commands I can use in MongoDB
 findOne(): It helps me view one record quickly
stats(): It helps me check how big or active a collection is""
