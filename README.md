# Udacity-Sparkify-Redshift

## Project Purpose and Description

Sparkify has been doing excellent and has grown their user base and song database exponentially in the past few months!  Their main goal at the moment is to move their processes and data to the cloud.  Their data is housed in an S3 bucket on Amazon Web Services.  The information is in a directory of JSON logs on user activity on the app,  as well as a directory with JSON metadata on the songs in their app.  In this project, I built an ETL Pipeline that extracts the data from S3, stages them into Redshift, and then transforms the data into a set of several dimensional tables as well as a songplay fact table.  


## Tools (all using Python and its various libraries)
   - Python
   - PostgreSQL
   - S3
   - Amazon Redshift
   
## Data

The data is in the form of JSON metadata on songs and JSON logs on user activity.  


## Table Goals
 
This star schema contains 1 fact table, songplays, and 4 dimension tables, artists, users, time, and songs.  (Both staging events and staging songs tables are displayed as well)   
 
## Repo Files

**dwh.cfg** - This configuration file contains the information for your cluster, ARN and S3 to connect to Redshift. 

**sql_queries.py** -  This file contains all of the create, insert and select statements for your tables.  

**create_tables.py** - Running this script in the terminal will drop the tables if it already exists and create your fact and dimension tables for the star schema in Redshift. 

**etl.py** - This file will load data from S3 into staging tables on Redshift and then process that data into analytics tables on Redshift.

## How to Run

NOTE:  In order to simulate this project, you will need to launch a cluster on on Amazon Redshit and connect to it.  

 - The first thing you need to do is add the cluster, arn, and S3 information to your config file. 
 - Next, you will run the create_tables.py file in the terminal.  Eg,  `python create_tables.py`
 - Then, run etl.py to load staging tables from S3 to Redshift and insert the data into the proper fact and dimension tables. 
 - Lastly, have fun querying!
 
