# What is ActiveRecord?

## Objectives

1. Define ActiveRecord and understand why it is easier to use.
2. Compare ActiveRecord vs. SQL queries.

## What is ActiveRecord?

ActiveRecord is what is referred to as an Object-Relational Mapper (ORM). It's responsible for mapping exactly one row in a database to one object in Ruby. 

Essentially, ActiveRecord is a wrapper written in Ruby that allows us to interact with a database without having to go through the pain of writing long SQL queries. While SQL queries are still run in Sinatra applications, ActiveRecord abstracts the process, making it much easier for us developers to write clean, understandable code.

Going forward, you'll use ActiveRecord to create and retrieve data from your database, and use traditional Ruby methods and attribute assignments to interact with this data. Instead of composing a SQL query manually, filling in the search parameters, sending it off to a database API, running the query, examining and parsing the result and storing the result in either a hash or a database, you let ActiveRecord do all that for you by writing simple Ruby code.


## Advanced: Understanding ORMs

What do we mean when we say an ORM maps a database row to a Ruby object? In an ORM, classes are mapped to tables and instances of classes are table rows. In other words, if your application has a `Car` class that produces car objects, your database would have a 'Cars' table, where each row  represents an instance of the class in question.

The data stored in each table row isn't the Ruby object itself, but a representation of that object. When we instantiate a new instance of the Car class, we've done nothing more than create an instance of that class. When we use Active Record's #save method on that Car instance (more on that later), your program is collecting the attributes or characteristics of that individual car and storing them in a row in the Cars table as raw data. Later, when you want to retrieve that individual car from your database, ActiveRecord will go into the database, find the appropriate row and use the raw data there to re-create (or initialize again) an instance of the Car class with the appropriate data.

Think of it like playing with Legos. Let's say we have a Lego set for making a toy car. One day, we might assemble the Legos, as per the instructions, into a car. Then, we might put our toys away and disassemble the toy car, placing the individual Legos that make it up back into their box. The next day, when we're ready to play Legos again, we can go into the toy box (our database) and retrieve the Legos (our raw data) and re-assemble them into our toy car (our Ruby object).

Moving forward, Active Record will assist in all of these interactions. We won't really need to understand how it works, just that Active Record provides us with a way of connecting to the database, saving the data that represents Ruby objects, retrieving specific data sets, and using them to re-create those objects.


## ActiveRecord vs SQL 

| SQL | ActiveRecord |
|----	|----- |
|SELECT * FROM cats;| Cat.all|  
|SELECT name FROM cats;| Cat.pluck(:name)| 
|SELECT * FROM cats <br> WHERE name = "Maru";| Cat.where(name: 'Maru')|
|SELECT * FROM cats <br> WHERE age > 2;| Cat.where('age > 2')|
|UPDATE cats SET name = "Hana" <br> WHERE name = "Hannah";| hannah = Cat.where(name: 'Hana') <br> hannah.name = "Hannah" |
|DELETE * FROM cats <br> WHERE id = 3;| Cat.destroy(3)|

Notice how much cleaner and more straightforward ActiveRecord makes interacting with the database compared to SQL - you'll learn more about CRUD methods in ActiveRecord later in this unit.



<p data-visibility='hidden'>View <a href='https://learn.co/lessons/activerecord-intro' title='What is ActiveRecord?'>What is ActiveRecord?</a> on Learn.co and start learning to code for free.</p>
