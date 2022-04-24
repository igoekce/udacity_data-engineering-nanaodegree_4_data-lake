Tasks to be done:
- Read in song and log json files
- Structure the laoded json files to:
    - Fact Table
        - songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
    - Dimension Tables
        - users - users in the app
          user_id, first_name, last_name, gender, level
        - songs - songs in music database
          song_id, title, artist_id, year, duration
        - artists - artists in music database
          artist_id, name, location, lattitude, longitude
        - time - timestamps of records in songplays broken down into specific units
          start_time, hour, day, week, month, year, weekday


1. Discuss the purpose of this database in context of the startup, Sparkify, and their analytical goals.
- Sparkify want to build an ETL pipeline that extracts their data from S3, processes them using Spark, and loads the data back into S3 as a set of fact and dimensional tables. This will allow their analytics team to continue finding insights in what songs their users are listening to.
- In preprocessed form the analytical process will be much easier for the data analyst to get further insights from the data
- the ELT is designed to give freedom to the analyst to discover more options than in a data warehouse
- you could evenly distibute the data so spark could work more efficient
- Network load is heavily reduced by preprocessed data

2. State and justify your database schema design and ETL pipeline. (Goal: This will allow their analytics team to continue finding insights in what songs their users are listening to.)
- The fact table contains as also suposed by kimball only facts like numbers
- the dimension gives additional information
- schema for dimensional tables are separated into user, song, artist and time related information, which will make information extraction more comfortable