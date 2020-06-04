# Python pipeline - Cassandra

This project demonstrates how to build a Python pipeline to an Apache Cassandra on a Docker container.<br>
The goal is to demonstrate basic understanding of how one can <br>
*  set up a Docker container with Apache Cassandra installed on it. <br>
*  utilize Python to establish a data pipeline to Apache Cassandra.<br>


### Installation of the Apache Cassandra Docker Container
* The yaml file docker-compose.yaml can be utilized to deploy Apache Cassandra Docker container.


### Loading the Data into Apache Cassandra
* When extracting the data used this project, I extracted them into a Pandas Dataframe, which allows one to define the data types within each column in the dataframe. <br>
* Additionally, Pandas Dataframe make data transformations easier, especially when it comes to modifying certain (or all) records within a particular column. But most importantly, I find Pandas Dataframe extremely useful as it makes loading the data into the target tables much more seamless and helps keep the code cleaner. <br>
* When it comes to loading the data, the INSERT statement utilized for Apache Cassandra is very similar to the statements that one would use for other SQL-based databases, which makes the setup of the INSERT statements easy.
