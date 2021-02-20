# Project Context
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.
We create an ETL pipeline by running queries given by the analytics team from Sparkify.

# Database Schema
The schema used is the Star Schema and why relational databases is a good choice here because since data is not much, data types are fixed and structured, we get data integrity. 

### Fact table: songplays (records related to song plays)

### Dimension tables: users, songs, artists and time.

# Running instructions
1. First run create_tables.py
3. Check etl.ipynb and then run etl.py
4. Test in the notebook tests.ipynb

