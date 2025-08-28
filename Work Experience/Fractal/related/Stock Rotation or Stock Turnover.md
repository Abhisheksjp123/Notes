Example: Consider a General store, these are the shelves that the retailer have in them.![[Pasted image 20250828170256.png|400]]

So with this stock how much the retailer is able to earn?
```math
Store_Capacity = 300000
Margins_perc = 20%
Earnings = Store_Capacity*Margins_perc
# But Expenses: rent, salary, other expense
Expense = 25000 + 5000 + 5000
Final_earning = Earnings - Expense
```
This does not makes sense, And here comes the concept of stock rotation:

Lets take example of a smaller shelf to understand that:
#### First Principle approach
Stock Rotation approach
![[Pasted image 20250828171046.png]]

Total shelf size = 30

| Week of month | Unit sold |
| ------------- | --------- |
| 1             | 25        |
| 2             | 18        |
| 3             | 24        |
| 4             | 23        |
| Total         | 90        |
that is each retailer restocks the units, so his overall sale from this shelve becomes 90 which is 3 times the shelve size of 30

Revenue
```math
Shelf_Capacity = 30
Unit_sold = 90
Times_shelf_capacity = Unit_sold/Shelf_Capacity
Unit_cost = 80
Shelf_worth = Unit_cost*Shelf_Capacity
Revenue_from_shelf = Unit_cost*Unit_sold
Margin_20Perc = Revenue_from_shelf*.2
```
Can we further increase this profit
#### Second principle approach
lets sell larger SKU instead of smaller ones
![[Pasted image 20250828171922.png]]

> Note: even though item size has increased 4 times 50ml to 200ml, shelf size has only reduced by half why?
> Remember, whenever you sell Larger SKUs, they will take significantly less size because of multiple reason, like vertical shelf occupancy, reduced packaging size etc
> Example:
> ![[Pasted image 20250828172223.png|200]]

But as demand for Larger SKUs will also be less, as only loyal customers will buy it, no of unit sold will also decrease

| Week of month | Unit sold |
| ------------- | --------- |
| 1             | 13        |
| 2             | 9         |
| 3             | 12        |
| 4             | 11        |
| Total         | 45        |
Calculation
```math
Shelf_Capacity = 15
Unit_sold = 45
Times_shelf_capacity = Unit_sold/Shelf_Capacity
Unit_cost = 300
Shelf_worth = Unit_cost*Shelf_Capacity
Revenue_from_shelf = Unit_cost*Unit_sold
Margin_20Perc = Revenue_from_shelf*.2
```

But here again the margin has almost double from 1440 to 2700.

#### Final approach
But again here we are missing out on consumers whose want to buy smaller SKU

![[Pasted image 20250828172632.png]]

Even though demand remains the same, out capacity is fixed
capacity small = 15
capacity large = 8

| Week of month | Demand small | Demand large |
| ------------- | ------------ | ------------ |
| 1             | 25           | 13           |
| 2             | 18           | 9            |
| 3             | 24           | 12           |
| 4             | 23           | 11           |
| Total         | 90           | 45           |
Final calculation
```math
Shelf_Capacity = 15 + 8
Unit_sold = 60 + 32
Times_shelf_capacity = Unit_sold/Shelf_Capacity
Unit_cost = 300
Shelf_worth = 3600
Revenue_from_shelf = 14400
Margin_20Perc = Revenue_from_shelf*.2
```

So, we're further able to increase the earning.

So with this concept of Stock rotation and product mix, we can increase the profit of retailer