# Project 1: Data Modeling with Postgres Introduction  

## Summary
* [Schema definition](#Schema-definition)
* [How to run](#How-to-run)
* [Project structure](#Project-structure)
* [Example queries](#Example-queries)
--------------------------------------------


#### Schema definition
This is the schema of the database

Fact table: 

songplays
* songplay_id: primary key <br>
* fields: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent<br>

Dimensions tables:

users
* user_id: primary key<br>
* Fields: first_name, last_name, gender, level <br>

songs
* song_id primary key<br>
* fields: title, artist_id, year, duration <br>

artists
* artist_id primary key<br>
* fields: name, location, latitude, longitude <br>

time
* start_time primary key<br>
* hour, day, week, month, year, weekday <br>


The songplays table is the core of this schema, is it our fact table and it contains foreign keys to four tables;
* start_time REFERENCES time(start_time)
* user_id REFERENCES time(start_time)
* song_id REFERENCES songs(song_id)
* artist_id REFERENCES artists(artist_id)

--------------------------------------------

#### How to run
First of all, install PostgresSQL (pgAdmin4) <br>
[Link:](https://www.postgresql.org/download/) for you preferred operating system <br>

Install Python [Python](https://www.python.org/downloads/) <br>

<b> Note: </b><br>
Create custom user called `student` with password `student` and create a database called `sparkifydb`

<I> Firstly we need to run this which will create our tables </I> <br>
`` python create_tables.py`` <br>

<I> And this file will execute our ETL process </I> <br>
`` python etl.py`` <br>

----------------------------

#### Project structure
Resource is a folder (we can download the source od JSON file directly from the http://millionsongdataset.com/)

* <b> /data </b> - contains source files for the project. 
  * <b> /log_data </b> - A folder that contains files of log files in JSON format generated by this [event simulator](https://github.com/Interana/eventsim) based on the songs in the dataset above. These simulate app activity logs from a music streaming app based on specified configurations.
  * <b> /song_data </b> -  Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID
* <b> etl.ipynb </b> - It is a notebook that helps to know step by step what etl.py does
* <b> test.ipynb </b> - It is a notebook that helps to know if tables are created and data are ingested correctly 
* <b> create_tables.py </b> - This script will drop old tables (if exist) ad re-create new tables
* <b> etl.py </b> - This script will read JSON every file contained in /data folder, parse them, build relations though logical process and ingest data 
* <b> sql_queries.py </b> - This file contains variables with SQL statement in String formats, partitioned by CREATE, DROP, INSERT statements plus a FIND query
* <b> README.md provides discussion on your project.

----------------------------