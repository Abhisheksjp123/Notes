Cardinality of database relationship refers to the number of occurrences of entity in an  relationship with another entity. It defines the number of instances of one entity that can be associated with the single instance of related entity.

An entity is == anything real world== whose table can be created like students, employee, order etc so id will not be an entity

There are 3 types of relationships:

![[Screenshot 2025-08-16 at 8.39.55 PM.png]]

1. One to one :
   example
   Person -> Driving license
*these type of relationships can be created with one table*
2. One to Many:
   example
   Student -> Branch
*these type of relationship needs 2 tables to be created, one \[studentid, student] and second \[Branchid, branch]*
3. Many to Many
   Example
   Student -> Courses
*these type of relationship needs 3 table to be connected, First for students, 2nd for Courses and 3rd for showing relationship b/w these 2 like \[Studentid, Courseid, Date], as in which student enrolled on which course on which date*

