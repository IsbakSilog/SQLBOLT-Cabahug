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
SELECT city
FROM north_american_cities
WHERE LONGITUDE < -87.629798
ORDER BY LONGITUDE ASC;
```

### Case 4
"List the two largest cities in Mexico (by population)"

```
SELECT city, population
FROM north_american_cities
WHERE country LIKE "Mexico"
ORDER BY population DESC
LIMIT 2;
```

### Case 5
"List the third and fourth largest cities (by population) in the United States and their population "
```
SELECT city, population FROM north_american_cities
WHERE country LIKE "United States"
ORDER BY population DESC
LIMIT 2 OFFSET 2;
```
## Lesson 12

### Case 1
"Find the number of movies each director has directed"
```
SELECT director, COUNT(id) as Directed
FROM movies
GROUP BY director;
```

### Case 2
"Find the total domestic and international sales that can be attributed to each director"
```
SELECT director, SUM(domestic_sales + international_sales) as TotalSales
FROM movies
    INNER JOIN boxoffice
        ON movies.id = boxoffice.movie_id
GROUP BY director;
```

## EXERCISE SQL PD

### Case 1
"A hacked site members' details have surfaced on a darknet forum. Please submit all members' details."

```
SELECT *
FROM members; 
```

### Case 2
"An illegal site's servers were seized in a recent operation. Please submit all users emails, first names and surnames' details."

```
SELECT Email, FirstName, Surname FROM users; 
```

### Case 3
"White hat hacker has sent SQLPD exposed subscribers' details of a shady site connected to various persons of interest. Please submit all subscribers mailing addresses, full names and usernames' details."

```
SELECT MailingAddress, FullName, Username FROM subscribers; 
```
### Case 4
"An illegal site's servers were seized in a recent operation. Please submit all users access times' details. Please make sure there are no duplicates."

```
SELECT DISTINCT Access_Time FROM USERS;
```

### Case 5
"An illegal site's servers were seized in a recent operation. Please submit all users' details sorted by last access times in ascending order."
```
SELECT *
FROM users
ORDER BY LastAccess; 
```

### Case 6
"A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit all records' details sorted by number of promotions sent in descending order"
```
SELECT * FROM mailing_list ORDER BY Promotions DESC;
```

### Case 7
"White hat hacker has sent SOLPD exposed members' details of a shady site connected to various persons of interest. Please submit all members usernames, number of purchases and names' details sorted by names in descending order. Please make sure there are no duplicates"
```
SELECT DISTINCT Username, Purchases, Name FROM members
ORDER BY Name DESC; 
```

### Case 8 
"An illegal site's servers were seized in a recent operation. Please submit all users number of posts, email addresses and last names' details sorted by email addresses in descending order and then by last names in descending order."

```
SELECT Posts, EmailAddress, LastName
FROM users
ORDER BY EmailAddress DESC, LastName DESC; 
```

### Case 9
"An illegal site's servers were seized in a recent operation. Please submit the top 5 users' details when sorted by first names in descending order and then by surnames in ascending order."
```
SELECT *
FROM users
ORDER BY FirstName DESC, Surname ASC
LIMIT 5;
```

### Case 10
"A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit the top 5 records email addresses, last names and first names' details when sorted by last names in ascending order and then by first names in ascending order. Please make sure there are no duplicates."

```
SELECT DISTINCT EmailAddress, LastName, FirstName FROM mailing_list
ORDER BY LastName ASC, FirstName ASC
LIMIT 5;
```
