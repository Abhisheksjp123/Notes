Type: interview drive, lots of candidates came for the position
Lunch and refreshment was offered.
Goodies: t shirt, diary, pen

---
Round 1: Test
4 questions, 1 hour given, 2 SQL, 1 Python Data manipulation, 1 Behavioural
==TIP==: Always have your watch with you, even though they don't ask you to put away your phone, watching time on phone is rude.

Q1: SQL
Given Order ID data of the format
> [!This table was unique on order id]

| Order id | User id | Date | Item id | Item | price | units | discount code |
| -------- | ------- | ---- | ------- | ---- | ----- | ----- | ------------- |
|          |         |      |         |      |       |       |               |
|          |         |      |         |      |       |       |               |

Problem: calculate rolling 7 day revenue for each day for a user

> [! I mentioned that my primary language is Python and continued the code in Python, I applied window function but was not able to remember all the syntax]
> This was the first question on first page and interviewer never moved past it, so not in my favour

Q2: SQL 
Given Session details of a user

| Event id | Time | User id | Session | Event | Revenue |
| -------- | ---- | ------- | ------- | ----- | ------- |
|          |      |         |         |       |         |
|          |      |         |         |       |         |
>[! Table was unique at Event id with each session having multiple events for a user ]

Problem 1: calculate the session conversion rate
Problem 2: Total time per checkout

Q3: Python
Given a Nike user run table, unique at a user date level. Run is only accounted when a user goes for a run.

| User id | Date | Run |
| ------- | ---- | --- |
|         |      |     |

Problem: Calculate continuous max streak per user
>[!Solved Approach]
>Created a for loop first for a user and then one more where I iterated with the dates for user
>my approach as an log n^2 time complexity, search for a better solution


Q4: Behavioural
First time user after purchasing a product does not come back back to the platform, suggest 5 KPIs which can track the experience of the user and help Ebay solve this problem.

>[!  I think i solved did problem fair enough]
>but do check the soution by an LLM


==Verdict, I did't had a great test as itt was a paper based test and i was not very good with the SQL part, but somehow I got to the secong Round==


---
Round 2: Technical Interview(Seemed more like Behavioural one)

Interviewer: Amit (did,t know the full name of the interviewer, next time ask it)

Amit: Shukla ji! kaise hain aap
Me: All good sir(shakes hand)
Amit: have a seat, kahan se hai aap
Me: Bhopal, MP
Amit: Bhopal mein kahan se?
Me: Nearby bhopal Shujalpur
==Next time when you say Bhopal say it with conviction, remember the whole nearby address of sonu bhaiyas place ==
Amit: Kahan kaam krte hain
Me: Fratal
Amit: Fractal to acchi company hai?
Me: Yes it is,
==Here I whould have answers, Yes Fractal is a company with good work culture==
Amit: Phir chod kyon rahe ho?
==This is a very important HR Question need to  be prepared for it==
[[Q1-Why do you want to leave your current company?]]
Me: I've been in Fractal for 5 years, and my peers have started better pay then me.
also last project that i worked on was on VBA which is not a very good language, and because that project was a success, I am rn working on another such project.

==Terrible answer both of these, kabhi paise aur kaam ki burai nahi karni, expecially intechinical intervirew==
Amit: Aap to kafi straight forward ho shukla ji (that was sarcastic)
Amit: You don't work on SQL, I do work on SQL but my work is limited to checking the data with few select and where queries. For analysis we use python and pyspark language
"here he might have a role which is SQL dependent hence we was trying to my hands on experience in it"


Amit: lets say you've an inventory of products, and a sells comes and gives you a photo that  he wants to add this product in the inventory.
how will you make sure that them model that identifies the product is working correctly?
Me: We should have a testing data set which have correct labels of the product identified matching with the inventory
from that dataset we can test our model with the help of several accuracy metrics, like for example for a particular product we can create a confusion matrix
Amit: ok you have a confusion matrix with lets say 70% recall, how will you fill the gap in this model.
I draw a confusion matrix to just recall the formula for recall, and came up with an incorrect formula, and i asked the interviewer weather it is the specificity. It was not, but he said yes.
then i said of so overall the issue is that we want to improve the model accuracy, what we can do is  may be improve our data quality, there should be some standardisation to the image/user uploads to the platform. also there might be some limitation of the  model that it can not process certain type of language. ok we can use better image classifiers like GPT 4 which are better at image classification.

==I need too get a better answer for this question

Amit: after this Amit did some cross questioning 
interview ends here--------------------xxx

Verdict::Rejected minutes later












