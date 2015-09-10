# What is ActiveRecord?

## Objectives

1. Define ActiveRecord and understand why it is easier to use.
2. Compare ActiveRecord vs. SQL queries.

## What is ActiveRecord?

ActiveRecord is what is referred to as an Object-Relational Mapper (ORM). It's responsible for mapping exactly one row in a database to one object in Ruby. 

Essentially, ActiveRecord is a wrapper written in Ruby that allows us to interact with a database without having to go through the pain of writing long SQL queries. While SQL queries are still run in Sinatra applications, ActiveRecord abstracts the process, making it much easier for us developers to write clean, understandable code.

Going forward, you'll use ActiveRecord to create and retrieve data from your database, and use traditional Ruby methods and attribute assignments to interact with this data. Instead of composing a SQL query manually, filling in the search parameters, sending it off to a database API, running the query, examining and parsing the result and storing the result in either a hash or a database, you let ActiveRecord do all that for you by writing simple Ruby code.



## ActiveRecord vs SQL 

| SQL                                   | ActiveRecord          |
|----					                       |-----                  |
|SELECT * FROM cats;                    | Cat.all              |  
|SELECT name FROM cats; 		           | Cat.pluck(:name)       | 
|SELECT * FROM cats <br> WHERE name = "Maru";| Cat.where(name: 'Maru')|
|SELECT * FROM cats <br> WHERE age > 2;      | Cat.where('age > 2')|
|UPDATE cats SET name = "Hana" <br> WHERE name = "Hannah";| hannah = Cat.where(name: 'Hana') <br> hannah.name = "Hannah" |
|DELETE * FROM cats <br> WHERE id = 3;        | Cat.destroy(3)|

Notice how much cleaner and more straightforward ActiveRecord makes interacting with the database - you'll learn more about CRUD methods in ActiveRecord later in this unit.


