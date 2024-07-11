# Hands-on-Project-Basics-of-SQL-SELECT-Statement

This is an hands-on project to demostrate skills on writing basic SQL SELECT statements.

# Objectives

The objective this project are to:

1. Write SQL statements to query SanFranciscoFilmLocations database
2. Retrieve data records from the filmlocations table according to the specified criteria.
   
# Highlights
1. How does the syntax of a SELECT statement look?

SELECT column1, column2, ...
FROM table_name
WHERE condition
;

2. What do the keywords / clauses of a SQL statement shown above do?
The SELECT statement is used to select data from a database.
FROM: Specifies from which table to get the data. The clause can include optional JOIN subclauses to specify the rules for joining tables.
[Optional Clause] WHERE : Specifies which rows to retrieve.

3. Why is there a semicolon after the SQL statements?
Some database systems require a semicolon at the end of each SQL statement for execution. It is a standard way to separate one SQL statement from another which allows more than one SQL statement to be executed in the same call to the server. So, it is good practice to use a semicolon at the end of each SQL statement.

# Software Used in this Project

In this project, I used PgAdmin 4 (PostgreSQL 15)

# Database Used in this Lab

The database used in this project comes from the following dataset source: Film Locations in San Francisco under a PDDL: Public Domain Dedication and License.
Dataset id downloadable here: https://drive.google.com/file/d/1xzX-gZTRZBT3XHwSJ1L34DbnszwQzdxC/view?usp=sharing

# Project Phases

The project was conducted in Three (3) phases as detailed below:

# Phase 1: Creating the SanFranciscoFilmLocations Database and filmlocations Table in PgAdmin

The first phase of the project involved creating our SanFranciscoFilmLocations Database and filmlocations Table in PgAdmin, followed by loading the FilmLocations CSV file. I achieved this by going through the following steps:

# Step 1: Creating a Database

1. I opened PgAdmin on my local computer and connected to my PostgreSQL server,
2. Right-clicked on the "Databases" node in the Browser panel on the left-hand side,
3. Selected "Create" > "Database",
4. In the "New Database" window:
   a. I entered the name of my database, "SanFranciscoFilmLocations", 
   b. Selected the owner (usually your PostgreSQL username, e.g., ELITEBOOK 840),
   C. Clicked "Save" to create the database.

# Step 2: Creating a Table

1. I navigated to my new database named "SanFranciscoFilmLocations":
   a. Expanded the "Databases" node,
   b. Expanded the "SanFranciscoFilmLocations" node,
2. Right-clicked on the "Tables" node under my new database,
3. Selected "Create" > "Table",
4. In the "Create - Table" window:
   a. I entered the name of my table, "filmlocations",
   b. Navigated to the "Columns" tab,
5. Added columns to your table:
   a. Clicked the "+" button to add a new column.
   b. For each column, I entered the name and selected the data type (e.g., VARCHAR, INTEGER)
   b. Repeated for all columns as defined below:

![image](https://github.com/DSgbemisola/Hands-on-Lab-Basics-of-SQL-SELECT-Statement/assets/116846702/23551016-34a7-40d7-b53b-eb3096b7f7e9)

6. Clicked "Save" to create the table.

# Step 3: Load Data from CSV Using PgAdmin Import/Export Feature

1. I Right-clicked on the "filmlocations" table in PgAdmin.
2. Selected "Import/Export Data".
3. In the "Import/Export Data" dialog:
   a. Selected "Import".
   b. Chose the file path to my CSV file (C:\Users\ELITEBOOK 840\Documents\FilmLocations.csv).
   c. Set the Format to CSV.
   d. Ensured Header is checked since my CSV file includes headers.
   e. Clicked "Columns" tab and verify the table columns.
4. Clicked "OK" to import the data.

# Phase 2: Exploring the Database

After successfully loading my data, I first explored the SanFranciscoFilmLocations database.
   1. I right-clicked on the "FilmLocations" table and 
   2. Selected "View/Edit Data" > "First 100 Rows".

See screenshot of the resultset:
![image](https://github.com/DSgbemisola/Hands-on-Lab-Basics-of-SQL-SELECT-Statement/assets/116846702/333a5eb0-df5d-4aa2-b7f8-4d826a7781bb)

# Phase 3: Writing SQL statements to query and answer questions on SanFranciscoFilmLocations database

# Task 1: Retrieve details of all the films from the filmlocations table with the details of each film record containing all the film columns.

Solution: I retrieved all records with all columns from the filmlocations table  using the SQL statement below:
          
          SELECT * FROM filmlocations;
          
![image](https://github.com/DSgbemisola/Hands-on-Lab-Basics-of-SQL-SELECT-Statement/assets/116846702/dadec81b-7a1c-4de8-9b76-b0824488c4d4)

# Task 2: Retrieve selective details of all the film records; retrieve the names of all the films along with director names and writer names.

Solution: I retrieved the names of all films with director names and writer names using the SQL statement below:
         
          SELECT title as film_title, director as director_name,  writer as writer_name 
          FROM filmlocations;
          
![image](https://github.com/DSgbemisola/Hands-on-Lab-Basics-of-SQL-SELECT-Statement/assets/116846702/ce1608e4-4e80-4d7b-be60-6f2eb1adaed0)

# Task 3: Retrieve film names along with filming locations and release years, also restrict the output resultset to retrieve only the film records released in 2001 and onwards.

Solution: I retrieved the names of all films released in the 21st century and onwards (release years after 2001 including 2001), along with filming locations and release years  using the SQL statement below:

          SELECT title as film_title, locations as filming_location, releaseyear as year_of_release
          FROM filmlocations
          WHERE releaseyear >= 2001;
          
![image](https://github.com/DSgbemisola/Hands-on-Lab-Basics-of-SQL-SELECT-Statement/assets/116846702/a3781b8d-0ca9-414d-8272-d318206de5a4)

# Task 4: Retrieve the fun facts and filming locations of all films.

Solution: I retrieved the fun facts and location columns along with the film titles using the SQL statement below:

          SELECT title as film_title, funfacts as fun_facts, locations as filming_location
          FROM filmlocations;
          
![image](https://github.com/DSgbemisola/Hands-on-Lab-Basics-of-SQL-SELECT-Statement/assets/116846702/471b9d3e-b1c5-4bbf-9c8e-c0e5fc12b94b)

# Task 5: Retrieve the names of all films released in the 20th century and before (release years before 2000 including 2000) that, along with filming locations and release years.

Solution: I retrieved the names of all films released in the 20th century and before (release years before 2000 including 2000) that, along with filming locations and release years using the SQL statement below:

          SELECT title as film_title, locations as filming_location, releaseyear as year_of_release
          FROM filmlocatios
          WHERE releaseyear <= 2000;
          
![image](https://github.com/DSgbemisola/Hands-on-Lab-Basics-of-SQL-SELECT-Statement/assets/116846702/cc02ab6b-a6c8-43ad-973f-3ee7e4896661)

# Task 6: Retrieve the names, production company names, filming locations, and release years of the films which are not written by James Cameron.

Solution: I retrieved the title, production company names, filming locations, and release years of the films which are not written by James Cameron using the SQL statement below:
         
         SELECT title as film_title, productioncompany as production_company_name, 
         locations as filming_location, releaseyear as year_of_release
         FROM filmlocations
         WHERE writer <> 'James Cameron';   
         
![image](https://github.com/DSgbemisola/Hands-on-Lab-Basics-of-SQL-SELECT-Statement/assets/116846702/64101602-bfc4-411e-b974-bc999ef34964)

