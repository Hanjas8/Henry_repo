# Project Process


## Program Function

- Store metadata about all reliable, published datsets in a database. The client can then query the database, and retrieve datasets based on criteria.
- Update database on a regularly basis by adding metadata about new datasets and by updating metadata labels when needed.  
  
## Flow Chart

<img src="Metadata project flow chart_2.png" style="height: 500px; width:1000px;"/>

<br>

## Extract Data

From databases such as Openml or UCI, download datasets

## Generate metadata

Iterate through dataset and store metadata information:  
Name   
Task Type  
URL  
Description  
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

- Better than SQL Relational databases because of the lack of flexibility. In a relational database, there is a fixed schema which enforces the user to enter value for each metadata label for all of the datasets. Also, the datatype must be fixed for all the entries in a column which will be tricky to ensure. In comparison, MongoDB is a key-value database which stores data in documents which have a flexible schema. This is needed when new values (which might have different data types) are added regularly. If a field is not in the metadata, then not putting the key-value pair into the database for that entry saves a lot of time.

- In terms of storage space, not much storage space is required. For every dataset, the metadata storage is shown:   
Name (~15 bytes)  
Task Type  (~ 20bytes)  
URL  (~30 bytes)  
Description  ( ~100 bytes)  
Number of Rows  (~15 bytes)  
Number of Features (~15 bytes)  
Number of Classes  (~15 bytes)  
Date of when data was taken  (~10 bytes)  
Number of Missing Values  (~15 bytes)  
Target Attibute  (~20 bytes)  
Sector (~15 bytes)  
<br>  
Total - 270 bytes  
<br>
So if there are a million datasets which are extracted, then the database total storage will be around 270MB. This is not a lot of data therefore and so MongoDB will run effectively and trouble-free. 


- There are many other key-value databases as well. However popular options such as Redis or DynamoDB have limited querying options. MongoDB has a rich querying language which is almost as powerful as SQL.



