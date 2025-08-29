1. To fetch all the data from the table
```
SELECT * FROM campusx.smartphones
```

2. Filter selected columns
```
SELECT model, price,rating FROM campusx.smartphones
```

3. ALIAS or renaming columns
```
SELECT model, price AS 'price(INR)',rating FROM campusx.smartphones
```

4. mathematical expressions or calculations or feature/attribute creation

lets create PPI - pixel per inch which is 
$$
PPI = √(W² + H²) / diagonal\_size\_in\_inches
$$
```
SELECT model, SQRT(resolution_width*resolution_width + resolution_height*resolution_height)/screen_size 
FROM campusx.smartphones
```

5. Constant value column
```
SELECT model, 'smartphone' as 'type' FROM campusx.smartphones
```

this will create a new column type with constant value smartphone

6. DISTINCT or unique values in a column
```
SELECT DISTINCT(brand_names) as 'all_brands' FROM campusx.smartphones
```

Distinct combinations

```
SELECT DISTINCT brand_name , processor_brand FROM campusx.smartphones
```

7. Filtering rows based on WHERE clause
```
SELECT * FROM FROM campusx.smartphones WHERE brand_name = 'samsung'

also
SELECT * FROM FROM campusx.smartphones WHERE price > 50000
```

these =, > are known as operators, some other popular SQL specific operators
[[SQL operators]]

8. Sorting values with ==ORDER BY==

Ex. find top 5 smart phones by Samsung with the highest price
```
SELECT model, price
FROM campusx.smartphones
WHERE brand = 'samsung'
ORDER BY price DESC LIMIT 5
```

==LIMIT== is used to display top n rows just like head function in pandas
a very good question on limit [[SQL Practice Question bank]] Q1

We can also Sort by multiple columns as
```
SELECT model, brand, price
FROM campusx.smartphones
ORDER BY brand ASC, price DESC
```

9. ==GROUP BY==
ex. Group smartphones by brand and get count, average price, max rating, avg screen_size and 
```
SELECT count(*) AS 'count', avg(price) AS 'average_price',
max(ratings) AS 'max_rating', avg(screen_size) AS 'average_screen_size'
FROM campusx.smartphones
GROUP BY brand_name
```

Groupby with multiple columns
```
SELECT count(*) AS 'count', avg(price) AS 'average_price',
max(ratings) AS 'max_rating', avg(screen_size) AS 'average_screen_size'
FROM campusx.smartphones
GROUP BY brand_name, processor_brand
```

Note count(), max(), SUM() these are [[Aggregate sql function]], used to do several additive tasks
10. HAVING
What WHERE is for SELECT, HAVING is the same for GROUP BY 
ex. find out average ratings of brands which have more than 20 phones

```
SELECT brand_name, count(*) AS 'count', AVG(rating) AS 'ratings'
FROM campusx.smartphones
GROUP BY brand_name
HAVING count>=20
```

11. CASE WHEN function
These are conditional function that create a column based on a condition

ex: find the rows where X,Y,Z can create a triagle
```
SELECT x, y, z,
    CASE
        WHEN GREATEST(x,y,z) < (x + y + z - GREATEST(x,y,z)) THEN 'Yes'
        ELSE 'No'
    END AS triangle
FROM Triangle
```