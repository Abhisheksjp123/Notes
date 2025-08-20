Window finction are a type of analytical function in SQL that performs calculations across a set of rows that are related to the current row, called a "window". A window function calculates a value for each row in the result set based on subset of the rows that are defiend by a window specification.

The window specification are defined using  the OVER() clause in SQL, which specifies the partitioning and ordering of the rows that the window function will operate on. The partitioning divides the row into groups based on a specific column or expression, while the ordering defines the order in which the rows are processed within each group.

# Intution for window function. 

Window functions work quite similar to the way GROUP BY function works
Consider a example of student table:

| student_id | name | branch | marks |
| :--- | :--- | :--- | :--- |
| 101 | Anjali Sharma | Computer Science | 88 |
| 103 | Priya Patel | Computer Science | 92 |
| 105 | Sneha Gupta | Computer Science | 79 |
| 107 | Neha Desai | Computer Science | 95 |
| 102 | Vikram Singh | Mechanical | 76 |
| 104 | Rohan Mehta | Mechanical | 81 |
| 106 | Amit Kumar | Mechanical | 85 |
| 108 | Sameer Joshi | Mechanical | 72 |

If I GROUP BY this on branch and calculate average marks
```
SELECT branch, AVG(marks) FROM students
GROUP BY branch
```

Result will be value provided for those 2 groups

| branch | AVG(marks) |
| :--- | :--- |
| Computer Science | 88.5 |
| Mechanical | 78.5 |

But instead if we do it though WINDOW function
```
SELECT *, AVG(marks) OVER(PARTITION BY branch) FROM students 
```

Result will be the same but instead of providing for a geoup it will do it for each row

| student_id | name          | branch           | marks | avg_marks_by_branch |
| :--------- | :------------ | :--------------- | :---- | :------------------ |
| 101        | Anjali Sharma | Computer Science | 88    | 88.5                |
| 103        | Priya Patel   | Computer Science | 95    | 88.5                |
| 105        | Sneha Gupta   | Computer Science | 79    | 88.5                |
| 107        | Neha Desai    | Computer Science | 95    | 88.5                |
| 102        | Vikram Singh  | Mechanical       | 76    | 78.5                |
| 104        | Rohan Mehta   | Mechanical       | 81    | 78.5                |
| 106        | Amit Kumar    | Mechanical       | 85    | 78.5                |
| 108        | Sameer Joshi  | Mechanical       | 72    | 78.5                |

==This small but unique properties let a do a lot of different analytical processes through window function==


# Function that are specifically useful with windows function

*SUM() is a aggregte function, it is not exactly for a window *, there are some other functions that are especially usefull on a window.
but we can still use window functions with additive functions like.
EX. Find all the students whose marks are greter than the branch average

```
SELECT * FROM 
(SELECT *, AVG(marks) OVER(PARTITION BY(branch) AS branch_avg) t
WHERE t.marks > t.branch_avg
```

1. RANK(), DENSE_RANK(), ROW_NUMBER()
- RANK() - Ranks the rows in the partition. In case there are multiple rows with same value, same values are assigned same rank and rest are adjusted accordingly. 
- DENSE_RANK() - Ranks the rows in the partition. In case there are multiple rows with same value, same values are assigned same rank and next rank continues from there.
- ROW_NUMBER() - Just gives a row number
Example

| student_id | name | branch | marks | RANK | DENSE_RANK | ROW_NUMBER |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 103 | Priya Patel | Computer Science | 95 | 1 | 1 | 1 |
| 107 | Neha Desai | Computer Science | 95 | 1 | 1 | 2 |
| 101 | Anjali Sharma | Computer Science | 88 | 3 | 2 | 3 |
| 105 | Sneha Gupta | Computer Science | 79 | 4 | 3 | 4 |
| 106 | Amit Kumar | Mechanical | 85 | 1 | 1 | 1 |
| 104 | Rohan Mehta | Mechanical | 81 | 2 | 2 | 2 |
| 102 | Vikram Singh | Mechanical | 76 | 3 | 3 | 3 |
| 108 | Sameer Joshi | Mechanical | 72 | 4 | 4 | 4 |

Syntax:
```
SELECT *, RANK() OVER(PARTITION BY branch ORDER BY marks DESC) FROM students
```

and same goes for DENSE_RANK() and ROW_NUMBER()

2. FIRST_VALUE(), LAST_VALUE(), NTH_VALUE()

- FIRST_VALUE() - Gives the first value in a partition
```
SELECT *, FIRST_VALUE(name) OVER(PARTITION BY branch ORDER BY marks DESC) FROM students
```

| student_id | name | branch | marks | first_value |
| :--- | :--- | :--- | :--- | :--- |
| 103 | Priya Patel | Computer Science | 95 | Priya Patel |
| 107 | Neha Desai | Computer Science | 95 | Priya Patel |
| 101 | Anjali Sharma | Computer Science | 88 | Priya Patel |
| 105 | Sneha Gupta | Computer Science | 79 | Priya Patel |
| 106 | Amit Kumar | Mechanical | 85 | Amit Kumar |
| 104 | Rohan Mehta | Mechanical | 81 | Amit Kumar |
| 102 | Vikram Singh | Mechanical | 76 | Amit Kumar |
| 108 | Sameer Joshi | Mechanical | 72 | Amit Kumar |

- ==LAST_VALUE== - Gives the last value in a partition. but seeing the output it does not seems right:

| student_id | name | branch | marks | last_value |
| :--- | :--- | :--- | :--- | :--- |
| 103 | Priya Patel | Computer Science | 95 | Priya Patel |
| 107 | Neha Desai | Computer Science | 95 | Neha Desai |
| 101 | Anjali Sharma | Computer Science | 88 | Anjali Sharma |
| 105 | Sneha Gupta | Computer Science | 79 | Sneha Gupta |
| 106 | Amit Kumar | Mechanical | 85 | Amit Kumar |
| 104 | Rohan Mehta | Mechanical | 81 | Rohan Mehta |
| 102 | Vikram Singh | Mechanical | 76 | Vikram Singh |
| 108 | Sameer Joshi | Mechanical | 72 | Sameer Joshi |
#FRAMES
Why?  Because of ==FRAMES== 
FRAMES - a frame in a window is a subset of rows within the partition that determines the scope of the window function calculation. The frame is defined with the combination of two clause within the window function: ROWS and BETWEEN

The ROWS clause specifies how many rows should be included in the frame relative to the current row. For example, ROWS 3 PRECEDING means that the frame includes the current row and the 3 rows that precede in the partition.

the BETWEEN clause specified the boundries of the frame.

Examples:

1. ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW: means that the fracme includes all the rows from the beginning of the partition upto and including the current row.
*This is the default selection, and this is the reason that output in case of FIRST_VALUE() came correct but LAST_VALUE() came incorrect*

2. ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING: This frame include the current row and the row immediate before and after it.
3. ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING: The frame include all rows in the partition.
*This should be used in case of FIRST_VALUE(), LAST_VALUE(), NTH_VALUE() for optimum results*
4. ROWS BETWEEN 3 PRECEDING AND 2 FOLLOWING : This frame include the current row and 3 row immediate before and 2 after it.

so for correct LAST_VALUE() output:

```
SELECT *, FIRST_VALUE(name) OVER(PARTITION BY branch
								ORDER BY marks DESC
								ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING)
FROM students
```

Example 2: ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING certainly makes the syntax long, and would be difficult in case of multiple windows.
consider this example:
Fine the name,  marks and branch of the topper in each branch
```
SELECT name,  branch, marks FROM 
(SELECT *, 
FIRST_VALUE(name) OVER w AS topper, 
FIRST_VALUE(marks) OVER w AS top_mark
FROM students
WINDOW w AS (PARTITION BY branch ORDER BY marks DESC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING)
) t
WHERE name = topper AND marks = top_mark
```


3. LAG() and LEAD()
- LAG() - gives the output by a lag of 1
- LEAD() - gives the output by a lead of 1

```
SELECT *, LAG() OVER(), LEAD() OVER()
FROM students
```

| student_id | name | branch | marks | lag | lead |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 101 | Anjali Sharma | Computer Science | 88 | null | 76 |
| 102 | Vikram Singh | Mechanical | 76 | 88 | 95 |
| 103 | Priya Patel | Computer Science | 95 | 76 | 81 |
| 104 | Rohan Mehta | Mechanical | 81 | 95 | 79 |
| 105 | Sneha Gupta | Computer Science | 79 | 81 | 85 |
| 106 | Amit Kumar | Mechanical | 85 | 79 | 95 |
| 107 | Neha Desai | Computer Science | 95 | 85 | 72 |
| 108 | Sameer Joshi | Mechanical | 72 | 95 | null |

EX: Find MOM growth for zomato

```
SELECT MONTHNAME(date), SUM(amount),
((SUM(amount) - LAG(SUM(amount)) OVER(ORDER BY MONTH(date)))/LAG(SUM(amount)) OVER(ORDER BY MONTH(date))
FROM orders
GROUP BY MONTHNAME(date)
ORDER BY MONTH(date) ASC
```