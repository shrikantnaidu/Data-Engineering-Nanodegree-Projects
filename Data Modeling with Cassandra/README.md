# Data Modeling 

This is the Data Modeling Project as part of the Udactiy Data Engineer Nanodegree.

## Context

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app.The analytics team is particularly interested in understanding what songs users are listening to.Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

The objective is to create an Apache Cassandra database which can create queries on song play data to answer the questions from the analytics team.

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
