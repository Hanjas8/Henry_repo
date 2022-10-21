# Project Process

<img src="Metadata project flow chart.png" style="height: 650px; width:1000px;"/>

## Extract Data

From databases such as Openml or UCI, download datasets

## Generate metadata

Iterate through dataset and store metadata information:  
Name
Task Type
URL
Number of Rows  
Number of Features  
Number of Classes  
Date of when data was taken  
Number of Missing Values  
Target Attibute  
Sector


Delete dataset when this step is complete.


## Store metadata

Use MongoDB to store metadata. This is because there are many advantages to using it compared to its alternatives: 

- Better than SQL Relational databases because of the lack of flexibility. In a relational database, there is a fixed schema which enforces the user to enter value for each metadata label for all of the datasets. Also, the datatype must be fixed for all the entries in a column which will be tricky to ensure. In comparison, MongoDB is a key-value database which stores data in Binary JSON documents. These documents have a flexible schema which is needed when new values (which might have different data types) are added regularly. If a field is not in the metadata, then not putting the key-value pair into the database for that entry saves a lot of time.

- There are many other key-value databases as well. However popular options such as Redis or DynamoDB have limited querying options. MongoDB has a rich querying language which is almost as powerful as SQL.

- MongoDB community database is free. Databases such as Oracle are not.



## Weekly Update of Database

This will happen once 7 days since the previous update has passed.  

Download all datasets available. 
For each dataset:  
If the database already contains metadata about it, update the metadata depending on if the dataset has changed.   
Otherwise generate metadata and add metadata to the database.


## Metadata label changes

This will happen if the user wants to add or delete some of the metadata labels, and the process is shwon in the flow chart.



