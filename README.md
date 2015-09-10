# What is ActiveRecord ?

## Objectives

1. Define ActiveRecord and understand why it is easier to use.
2. Compare ActiveRecord vs. SQL queries.

## ActiveRecord

ActiveRecord is what is referred to as an Object-Relational Mapping (ORM). It's responsible for mapping exactly one row in a database to one object in Ruby. 

What this means in practice is that you use ActiveRecord to create or retrieve your data and use traditional Ruby methods and attribute assignments to interact with this data. Instead of composing an SQL query manually, filling in the search parameters, sending it off to a database API, running the query, examining and parsing the result and storing the result in either a hash or a database, you let ActiveRecord do all that for you.

ActiveRecord is also responsible for handling all database interaction from the application level.


## ActiveRecord vs SQL 

| SQL                                   | ActiveRecord          |
|----					                       |-----                  |
|SELECT * FROM cats;                    | Cat.all              |  
|SELECT name FROM cats; 		           | Cat.all.name         | 
|SELECT * FROM cats WHERE name = "Maru";| Cat.where(name: 'Maru')|
|SELECT * FROM cats WHERE age > 2;      | Cat.where('age > 2')|
|UPDATE cats SET name = "Hana" WHERE name = "Hannah";| hannah = Cat.where(name: 'Hana') cat.name = "Hannah" |
|DELETE * FROM cats WHERE id = 3        | Cat.destroy(3)|

