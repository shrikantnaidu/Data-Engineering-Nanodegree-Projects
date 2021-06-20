# Data Lake

This is the Data Lake Project as part of the Udactiy Data Engineer Nanodegree.

# Context

A music streaming startup, Sparkify, has grown their user base and song database even more and want to move their data warehouse to a data lake. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.


The objective is to build an ETL pipeline that extracts their data from S3, processes them using Spark, and loads the data back into S3 as a set of dimensional tables. This will allow their analytics team to continue finding insights in what songs their users are listening to.


# Database schema


#### Table Overview

| Table | Description |
| --- | --- | 
| songplays | Table for the songs played |
| users | Table for the user data |
| songs | Table for the songs data |
| artists | Table for the artists data |
| time | Table for time-related data |


####  Fact Table
- songplays - records in event data associated with song plays i.e. records with page NextSong.  

`songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent`

#### Dimension Tables
- users - users in the app.  

`user_id, first_name, last_name, gender, level`
- songs - songs in music database. 

`song_id, title, artist_id, year, duration`
- artists - artists in music database.

`artist_id, name, location, lattitude, longitude`
- time - timestamps of records in songplays broken down into specific units. 

`start_time, hour, day, week, month, year, weekday`


# Project Structure
Files used on the project:

1. **etl.py** - reads and processes files from song_data and log_data and loads them into your tables.
2. **dl.cfg** - contains the credentials to use cloud resources.
3. **README.md** - documentation of the process, provides execution information on the project.

### Process Overview


1. Read the data from the S3 bucket.

- Song data: s3://udacity-dend/song_data

- Log data: s3://udacity-dend/log_data

2. Process data using spark.

   The script reads song_data and load_data from S3 and transforms the data in the S3 bucket to create five different tables listed below :

   Fact Table:
   
    - songplays : records in log data associated with song plays i.e. records with page NextSong

   Dimension Tables:
   
    - users : users in the app Fields 

    - songs : songs in music database Fields 

    - artists : artists in music database Fields 

    - time : timestamps of records in songplays broken down into specific units Fields 

3. Load the data back to the S3 bucket.

   Writes the data in parquet format to different table directories in the S3 bucket.
