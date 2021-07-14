# Data Modeling 

This is the Data Modeling Project as part of the Udactiy Data Engineer Nanodegree.

## Context

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. 
The analytics team is particularly interested in understanding what songs users are listening to.Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

The ojective is to create a database schema and ETL pipeline for this data.

### Data
- **Song datasets**: all json files are nested in subdirectories under */data/song_data*. A sample of this files is:

```
{   
    'num_songs':1,
    'artist_id':"ARD7TVE1187B99BFB1",
    'artist_latitude':null,
    'artist_longitude':null,
    'artist_location':"California - LA",
    'artist_name':"Casual",
    'song_id':"SOMZWCG12A8C13C480",
    'title':"I Didn't Mean To",
    'duration':218.93179,
    'year':0
}
```

- **Log datasets**: all json files are nested in subdirectories under */data/log_data*. A sample of a single row of each files is:

```
{
    "artist":"Muse","auth":"Logged In",
    "firstName":"Jordan",
    "gender":"F",
    "itemInSession":3,
    "lastName":"Hicks",
    "length":259.26485,
    "level":"free",
    "location":"Salinas, CA",
    "method":"PUT",
    "page":"NextSong","registration":1540008898796.0,
    "sessionId":814,
    "song":"Supermassive Black Hole [Phones Control Voltage Remix]",
    "status":200,"ts":1543190563796,
    "userAgent":"\"Mozilla\/5.0 (Macintosh; Intel Mac OS X 10_9_4) AppleWebKit\/537.78.2 (KHTML, like Gecko) Version\/7.0.6 Safari\/537.78.2\"",
    "userId":"37"
    }
```

## Database Schema

The schema used for this exercise is the Star Schema: 
There is one main fact table containing all the measures associated to each event (user song plays), 
and 4 dimentional tables, each with a primary key that is being referenced from the fact table.


#### Fact Table

**songplays** - records in log data associated with song plays i.e. records with page NextSong
- songplay_id  
- start_time 
- user_id 
- level 
- song_id 
- artist_id 
- session_id 
- location 
- user_agent 


#### Dimension Tables
**users** - users in the app
- user_id
- first_name 
- last_name 
- gender 
- level 

**songs** - songs in music database
- song_id 
- title 
- artist_id 
- year
- duration 

**artists** - artists in music database
- artist_id 
- name
- location 
- lattitude 
- longitude 

**time** - timestamps of records in songplays broken down into specific units
- start_time 
- hour
- day 
- week 
- month 
- year 
- weekday 


## Project structure

Files used on the project:
1. **data** folder nested at the home of the project, where all needed jsons reside.
2. **sql_queries.py** contains all your sql queries, and is imported whenever needed.
3. **create_tables.py** drops and creates tables.Use this file to reset your tables before you run your ETL scripts.
4. **test.ipynb** displays the first few rows of each table to let you check your database.
5. **etl.ipynb** reads and processes a single file from song_data and log_data and loads the data into your tables. 
6. **etl.py** reads and processes files from song_data and log_data and loads them into your tables. 
7. **README.md** documentation of the process, provides execution information on the project.

### Steps to follow

1. Completing all the queries in sql_queries.py

2. Run in console to create the tables.
 ```
python create_tables.py
```
3. Follow the instructions and complete etl.ipynb Notebook to create the blueprint of the etl process.

4. Use test.ipynb Jupyter Notebook to verify the results of the above step.

5. After verifying the results, use the sames set of scripts and complete etl.py.

6. (Optional Step) Use step 2 to reset the tables.

7. Run etl file in console, and verify results:
 ```
python etl.py
```



