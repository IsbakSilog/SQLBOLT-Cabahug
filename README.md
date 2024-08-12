# SQLBOLT-Cabahug

### Case 1
"List all the Canadian cities and their populations "
```
SELECT city, population 
FROM north_american_cities
WHERE COUNTRY = "Canada";
```

### Case 2
"Order all the cities in the United States by their latitude from north to south"
```
SELECT *
FROM north_american_cities
WHERE COUNTRY = "United States"
order by latitude desc;
```

### Case 3
"List all the cities west of Chicago, ordered from west to east"
```
SELECT CITY FROM north_american_cities
WHERE LONGITUDE < -87.629798
ORDER BY LONGITUDE ASC;
```

### Case 4
"List the two largest cities in Mexico (by population)"

```
SELECT city, population
FROM north_american_cities
WHERE country = "Mexico"
ORDER BY population DESC
LIMIT 2
```

### Case 5
"List the third and fourth largest cities (by population) in the United States and their population "
```
SELECT city, population FROM north_american_cities
WHERE country = "Mexico"
ORDER BY population DESC
LIMIT 2;
```
