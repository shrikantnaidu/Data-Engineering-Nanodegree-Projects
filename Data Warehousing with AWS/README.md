# Data Warehouse

This is the Data Warehouse Project as part of the Udactiy Data Engineer Nanodegree.

# Context

A music streaming startup, Sparkify, has grown their user base and song database and want to move their processes and data onto the cloud. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

The objective is to build an ETL pipeline that extracts their data from S3, stages them in AWS Redshift, and transforms data into a set of dimensional tables for their analytics team to continue finding insights in what songs their users are listening to.

# Database schema

#### Table Overview

| Table | Description |
| --- | --- | 
| staging_events | Staging table for events data |
| staging_songs | Staging table for songs data|
| songplays | Table for the songs played |
| users | Table for the user data |
| songs | Table for the songs data |
| artists | Table for the artists data |
| time | Table for time-related data |


#### Staging Tables
- staging_events
- staging_songs

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

1. **create_tables.py** - drops and creates tables.Use this file to reset your tables before you run your ETL scripts.
2. **etl.py** - reads and processes files from song_data and log_data and loads them into your tables.
3. **sql_queries.py**  - contains all your sql queries, and is imported whenever needed.
4. **create_cluster.ipynb** - sets up the various cloud resources needed for the execution also cleans up all the resources used in the project. 
5. **dwh.cfg** - contains the credentials to use cloud resources.
6. **README.md** - documentation of the process, provides execution information on the project.

### Steps to follow

1.
