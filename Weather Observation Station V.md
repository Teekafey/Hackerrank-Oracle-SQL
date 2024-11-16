Query the two cities in __STATION__ with the shortest and longest __CITY__ names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
The __STATION__ table is described as follows:

  __STATION__     
|Field        | Type                     
|------------ | ---------
|ID           | NUMBER
|CITY         | VARCHAR2(21)
|STATE        | VARCHAR2(2)
|LAT_N        | NUMBER
|LONG_W       | NUMBER

where __LAT_N__ is the northern latitude and __LONG_W__ is the western longitude.

---------------------------------
__Sample Input__

For example, __CITY__ has four entries: __DEF__, __ABC__, __PQRS__ and __WXY__.

__Sample Ouput__

```
ABC 3
PQRS 4
```

__Explanation__

When ordered alphabetically, the __CITY__ names are listed as __ABC__, __DEF__, __PQRS__, and __WXY__, with lengths __3__, __3__, __4__, and __3__. The longest name is __PQRS__, but there are __3__ options for shortest named city. Choose __ABC__, because it comes first alphabetically.

__Note__

You can write two separate queries to get the desired output. It need not be a single query.

--------------------------------

Here is the query:

Shortest City Name Query:
```SQL
SELECT city,
       LENGTH(city) AS city_length
FROM station
ORDER BY LENGTH(city) ASC,
         city ASC
FETCH FIRST 1 ROWS ONLY; -- this is the new oracle syntax for limiting rows

/* FETCH FIRST 1 ROWS ONLY is not supported by Hackerrank
   ROWNUM is what is being used, as a subquery.
   This query should work. */

SELECT *
FROM
   ( SELECT city,
           LENGTH(city)
    FROM STATION
    ORDER BY LENGTH(city) ASC,
             city ASC )
WHERE ROWNUM = 1;
```

Longest City Name Query

```SQL
SELECT city,
       LENGTH(city) AS city_length
FROM station
ORDER BY LENGTH(city) DESC,
         city ASC
FETCH FIRST 1 ROWS ONLY; -- this is the new oracle syntax for limiting rows

/* FETCH FIRST 1 ROWS ONLY is not supported by Hackerrank
   ROWNUM is what is being used, as a subquery.
   This query should work. */

SELECT *
FROM
   ( SELECT city,
           LENGTH(city)
     FROM STATION
     ORDER BY LENGTH(city) DESC,
             city ASC )
WHERE ROWNUM = 1;
```


**Explanation of the Query:**

**1. Shortest City Name Query**
   
- SELECT city, LENGTH(city) AS city_length:
  
  This selects the city name and calculates the length of each city name using LENGTH(city).

  The AS city_length aliases the length column for easier readability.

- FROM station:
  
  Specifies the table station from which to retrieve the data.

- ORDER BY LENGTH(city) ASC, city ASC:

  Orders the results by the length of the city name in ascending order (LENGTH(city) ASC).

  If there are multiple cities with the same length, it orders them alphabetically (city ASC).

- FETCH FIRST 1 ROWS ONLY:

  Limits the result to the first row, returning only the city with the shortest name.

**2. Longest City Name Query**
   
- SELECT city, LENGTH(city) AS city_length:
  
  This selects the city name and calculates the length of each city name using LENGTH(city).

  The AS city_length aliases the length column for easier readability.

- FROM station:
  
  Specifies the table station from which to retrieve the data.

- ORDER BY LENGTH(city) DESC, city ASC:

  Orders the results by the length of the city name in descending order (LENGTH(city) DESC), which brings the longest names to the top.

  If there are multiple cities with the same length, it orders them alphabetically (city ASC).

- FETCH FIRST 1 ROWS ONLY:

  Limits the result to the first row, returning only the city with the longest name.

-------------------------------------------

**Explanation of the Subquery:**

**1. Shortest City Name**

Inner Query:

- SELECT city, LENGTH(city) AS city_length:

  Selects the city name and calculates its length with LENGTH(city), aliasing it as city_length.

- FROM station:

  Specifies station as the source table.

- ORDER BY LENGTH(city) ASC, city ASC:

  Orders cities by their name length in ascending order (LENGTH(city) ASC), meaning shortest names are first.

  If there are cities with the same length, it orders alphabetically (city ASC).

Outer Query:

- WHERE ROWNUM = 1:

  Limits the results to the first row, returning only the city with the shortest name from the ordered list.


**2. Longest City Name**

Inner Query:

- SELECT city, LENGTH(city) AS city_length:

  Selects the city name and calculates its length with LENGTH(city), aliasing it as city_length.

- FROM station:

  Specifies station as the source table.

- ORDER BY LENGTH(city) DESC, city ASC:

  Orders cities by their name length in ascending order (LENGTH(city) DESC), meaning longest names are first.

  If there are cities with the same length, it orders alphabetically (city ASC).

Outer Query:

- WHERE ROWNUM = 1:

  Limits the results to the first row, returning only the city with the longest name from the ordered list.

This approach is compatible with environments that do not support FETCH FIRST.
