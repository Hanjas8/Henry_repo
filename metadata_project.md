# Project Process

<img src="Metadata project flow chart.png" style="height: 800px; width:1000px;"/>

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

Use MongoDB to store metadata. This is because there are several advantages to using it compared to its alternatives:  
- Flexability. MongoDB is a key-value database which stores data in Binary JSON documents. These documents have a flexible schema which is needed when new values (which might have different data types) are added regularly.
- Scalability. MongoDB has a horizontal scaling architecture which is achieved through built-in sharding. This makes MongoDB reliable, efficient and able to handle large amounts of data.
  
- Extensive queries with rich language. MongoDB supports dynamic queries on documents using a document-based query language that's nearly as powerful as SQL.

- Free


## Weekly Update of Database

This will happen once 7 days since the previous update has passed.  

Download all datasets available. 
For each dataset:  
If the database already contains metadata about it, update the metadata depending on if the dataset has changed.   
Otherwise generate metadata and add metadata to the database.

