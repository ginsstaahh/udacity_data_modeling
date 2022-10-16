# Intro
Song database is a program used for the latest and greatest music app created by Sparkify that acts as a backend framework to store, insert, and provide you with songs, artist information, and albums.  It uses an ETL pipeline to transfer data from the root working folder into the Postgres database.  The program provides the essential information about Sparkify users' interests used for data analytics.

There are five tables in the Sparkify database used as a backend resource: songplays, users, time, songs, and artists.  Each database table contain their own data columns and primary keys using int, float, varchar, text, and bigint data types.  Songplays table differs from other tables because it includes data from two foreign tables (songs and artists).

## Database Schema
Here is a diagram based off of the star schema that gives an overview of the tables and their data columns
![alt text](/db_schema.png?raw=true)

The star schema shows several tables including:
songplays: a fact table that records log data associated with song plays
users: a dimension table containing data of the users of the app
songs: a dimension table containing data of songs in the database
artists: a dimension table containing artists in the database
time: a dimension table containing timestamps of records in songplays broken down into specific units

## Folders and Files in Repository
The data folder contains raw log and song datasets in their respective children folders.  The data in these datasets are retrieved and put into databases when the program is run.

sql_queries.py - creates and provides all the sql used for providing database table structure, deletion code and insertion statements
create_tables.py - used as middleware that takes sql code from sql_queries.py for the purposes of creation and deletion of the database used and its tables.
etl.py - contains the logic to process data insertion.

db_schema.png - star schema diagram of fact and dimension tables found in the project

The two Jupyter notebooks show the rough work done with it's examples and entries into the databases.  The methods of etl.py and sql_queries.py were developed from these Jupyter notebooks:
etl.ipynb - a Jupyter notebook used during project development to inserts data into the five tables.
test.ipynb - a Jupyter notebook which was used to check the validity of insertion of data

## Running Python Scripts
A terminal can be used to run the python files to generate tables.  Using the terminal, which can be found in the launcher tab, run create_tables.py in the root working directory to create the backend framework needed to assess the working code:
python create_tables.py

You can now use etl.py to insert data:
python etl.py

### Prerequisites
If you are on linux, you probably already have python installed
Check to see if your UNIX system has already has python by using the command in your terminal:
python --version

Python can be installed for ubuntu or debian linux using the command:
sudo apt-get install python