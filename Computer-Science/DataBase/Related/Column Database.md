These databases store data in columns rather than rows, making them better suited for data warehousing. and analytical applications.
Popular Software: Amazon RedShift, Google BigQuery
   
Requirement of column database arrives from memory management, 
Relation database are row based database where each value is stored in form of a row.
Example: CGPA table with columns: Name, Branch, CGPA
each value in memory will be stored as
\[Nitish, E.E, 7.9] , \[Raghav, Mechanical, 7.5]
Now if we want to find the average CGPA, we'll have to access all the rows. 

This problem is solved by Column database, where values are stored in columns,
in this case 3 tables as 
\[SR No, Name], \[SR No, Branch]. \[SR No, CGPA]

this will improve memory management and computation.

# Column Database vs Relational Database

Relational database: OLTP, Row based, Generally used in websites

while

Column Database: OLAP, Column based, in Data warehousing, generally used for analysis
