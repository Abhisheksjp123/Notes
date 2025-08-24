*Please note: Below syntax are for MySQL, for POSTGRE SQL (which is another popular SQL language) refer [[POSTGRE SQL syntax]]*
# String based
1. `LEFT(string, number_of_characters)`
To get the first letter of a person's name from a `users` table, you could use:
```
SELECT LEFT(Name, 1) FROM users;
```
Similarly we've RIGHT(string, number_of_characters)

2. **`SUBSTRING(string, start_position, length)`**: Extracts a substring of a specified length from a given starting position.
- **Example:** `SELECT SUBSTRING('SQL Practice', 5, 8);` would return `'Practice'`.

2. **`LENGTH(string)`**: Returns the length of the string in characters.
- **Example:** `SELECT LENGTH('Hello');` would return `5`.
# Date based
1. MONTH(date) #scaler