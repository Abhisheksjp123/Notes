Resume based questions
	Asked about Adstock

Machine learning based questions
1. QQ plot and KDE
2. Adjusted R square
Python
SQL
Table A: Customer table
CustomerID, Joining_Date, Region  
Sample:  
ABC, 04-01-2024, Bihar  
DEF, 05-01-2024, Assam

Table B: Call records table

CustomerID, Call_Date, Call_Time, Duration

  

Schema:  
CustomerID, Call_Date, Call_Time, Duration  

String, Date, Date Time, Integer

  

Sample:  

ABC, 04-01-2024, 04-01-2024 08:00 HRS, 30  

ABC, 04-01-2024, 04-01-2024 09:00 HRS, 45  

ABC, 04-01-2024, 04-01-2024 011:30 HRS, 30

  

ABC, 05-01-2024, 05-01-2024 07:00 HRS, 30  

ABC, 05-01-2024, 05-01-2024 09:00 HRS, 45  

DEF, 02-01-2024, 02-01-2024 08:00 HRS, 30  

DEF, 02-01-2024, 02-01-2024 09:00 HRS, 45  

DEF, 03-01-2024, 03-01-2024 011:30 HRS, 30

  

DEF, 03-01-2024, 03-01-2024 07:00 HRS, 30  

DEF, 03-01-2024, 03-01-2024 09:00 HRS, 45

  

  

  

Objective:  
Take records from table B having all the following conditions:  

1.Customers belonging to region name letter starting “B”

Select * from TableA

Where Region like “B*”

2.Customers joined after Jan 2021  
Select * from TableA

Where Joining_Date> “01-01-2025”

  

3. Only those call records that are the 2nd last call record for each day for each customer

  

# Df = TableB

Tables

Tablets = TableB.groupby(["CoustomerID,Call_Date”]).rank

  

  

——coding question

mylist = [10,3,1,5,8,4] #prices off product in sm on a week

  

For 10

P = -2. 

4th value

  

Dict = {}

For i in mylist:

profit = 0

max_profit   = 0

for j in range(I , len(mylist):

# profit for the diff

profit=mylist[j]-mylist[I]




# Puzzle based logical question
Q. let day you've 25 horses and you can run 5 at a time. you can just get first 2nd 3rd from this process. You want to get 3 fastest horses from 25. how many min races you need to do.
Ans is 7
>[!Ans]-
>This is a classic puzzle. Let me work through it step by step.
**Goal:** Find the 3 fastest horses from 25 horses **Constraints:** Can only race 5 horses at a time, only get positions 1st, 2nd, 3rd from each race
**Solution:**
**Step 1: Initial races (5 races)** Divide 25 horses into 5 groups of 5. Race each group.
>- Race 1: A1, A2, A3 (top 3)
>- Race 2: B1, B2, B3 (top 3)
>- Race 3: C1, C2, C3 (top 3)
>- Race 4: D1, D2, D3 (top 3)
>- Race 5: E1, E2, E3 (top 3)
**Step 2: Race the group winners (1 race)** Race A1, B1, C1, D1, E1 to determine the fastest horse overall. Let's say the result is: A1, B1, C1, D1, E1
Now we know:
>- A1 is the fastest horse overall (1st place confirmed)
>- The 2nd and 3rd fastest must come from: A2, A3, B1, B2, C1
**Step 3: Final race (1 race)** Race A2, A3, B1, B2, C1 The top 2 finishers are the 2nd and 3rd fastest horses overall.
**Answer: 7 races minimum**
