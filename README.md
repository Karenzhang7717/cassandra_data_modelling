# Data modelling with Cassandra

**Introduction**

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analysis team is particularly interested in understanding what songs users are listening to. Currently, there is no easy way to query the data to generate the results, since the data reside in a directory of CSV files on user activity on the app.

The project  defines a data model that will help to understand user activities. The NoSQL database, Apache Cassandra is used for modelling, and we need to understand informations that the data scientists would like to collect. 

**Queries**

One table is created for one query, as we will be using Apache Cassandra database.

*Query1:*

*Give me the artist, song title and song's length in the music app history that was heard during sessionId = 338, and itemInSession = 4*

Primary key: both sessionId and itemInSession are set to be primary keys to make the resulted query unique. In this case, sessionId is the partition key and itemInSession is the clustering key. sessionId is set to be partition key as this is the primary way that our data is being filtered in the query.



*Query2:*

*Give me only the following: name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182*

Primary key:

We are asked to filter data by userId and sessionId, itemInSession also needs to be sorted. To make the primary keys unique, we set userId, sessionId, itemInSession to be the primary key. The partition key is set to be userId as this is the primary way the data being filtered. Cluster keys are sessionId and itemInSession, and they are set to be ordered in descending order.

*Query3:*

*Give me every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'*

Primary key:

Song_title and userId are set to be primary key to make it unique. Song_title is the partition key as we are filtering by song_title.

