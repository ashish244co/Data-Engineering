# Project Context
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.
We create an ETL pipeline by running queries given by the analytics team from Sparkify.

# Database Schema
The schema used is the Star Schema and why relational databases is a good choice here because since data is not much, data types are fixed and structured, we get data integrity. 

### Fact table: 
#### songplays (records related to song plays)

| COLUMN  | TYPE  | CONSTRAINT  |
|---|---|---|
|   songplay_id| SERIAL  |   PRIMARY KEY| 
|   start_time|   timestamp|   NOT NULL| 
|   user_id|   int|   NOT NULL| 
|   level|   varchar |   | 
|   song_id|   varchar|   | 
|   artist_id|   varchar|   | 
|   session_id|   int|   | 
|   location|   varchar|   | 
|   user_agent|   varchar|   | 

### Dimension tables: 
#### users 
 | COLUMN  | TYPE  | CONSTRAINT  |
|---|---|---|
|   user_id| int  |   PRIMARY KEY| 
|   first_name|   varchar|  | 
|   last_name|   varchar|  | 
|   gender|   varchar|   | 
|   level|   varchar|   | 
#### songs
 | COLUMN  | TYPE  | CONSTRAINT   |
|---|---|---|
|   song_id| varchar  |   PRIMARY KEY| 
|   title|   varchar|  | 
|   artist_id|   varchar| NOT NULL  | 
|   year|   int |   | 
|   duration|   float|   | 
#### artists 
 | COLUMN  | TYPE  | CONSTRAINT   |
|---|---|---|
|   artist_id| varchar  |   PRIMARY KEY| 
|   name|   varchar|   | 
|   location|   varchar|   | 
|   latitude|   float|   | 
|   longitude|   float |   | 
#### time
 | COLUMN  | TYPE  | CONSTRAINT   |
|---|---|---|
|   start_time| timestamp  |   PRIMARY KEY| 
|   hour|   int|   | 
|   day|   int|   | 
|   week|   int|   | 
|   month|   int|   | 
|   year|   int|   | 
|   weekday|   varchar|   | 

# Files
### etl.py
1. Connect to the database.
2. Process the song files.
    1. First insert song data into songs table and artist data into artist table.
3. Process the logs.
    1. First insert timestamps in time table.
    2. Then insert user info in users table and songpplay records into songplays table.
    
### sql_queries.py

This have all the sql queries such as create tables, insert records and selecting songs.

### create_tables.py

Uses sql_queries.py to create tables with all the information.

# Running instructions
1. First run create_tables.py
3. Check etl.ipynb and then run etl.py
4. Test in the notebook tests.ipynb