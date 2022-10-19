# Project Process

<img src="Metadata project architecture.png" style="height: 500px; width:1000px;"/>

## Extract Data

From databases such as Openml or UCI, download datasets

## Generate metadata

Iterate through dataset and store metadata information:  
Number of Rows  
Number of Features  
Number of Classes  
Task Type  
Date of when data was taken  
Number of Missing Values  
Target Attibute  
Tags 

Delete dataset when this step is complete.


## Store metadata

Use MongoDB to store metadata. This is because there are several advantages to using it compared to its alternatives:  
- Flexability. MongoDB is a key-value database which stores data in Binary JSON documents. These documents have a flexible schema which is needed when new values (which might have different data types) are added regularly.
- Scalability. MongoDB has a horizontal scaling architecture which is achieved through built-in sharding. This makes MongoDB reliable, efficient and able to handle large amounts of data.
  
- Extensive queries with rich language. MongoDB supports dynamic queries on documents using a document-based query language that's nearly as powerful as SQL.

- Free





