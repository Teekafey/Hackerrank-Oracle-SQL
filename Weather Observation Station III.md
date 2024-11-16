Query a list of __CITY__ names from __STATION__ for cities that have an even __ID__ number. Print the results in any order, but exclude duplicates from the answer.
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


Here is the query:
```SQL
SELECT DISTINCT(city)
FROM station
WHERE MOD(id, 2) = 0
ORDER BY city;
```

**Explanation of the Query:**
- SELECT DISTINCT city: Retrieves the city field, and the **DISTINCT** keyword ensures that only unique city names are returned, excluding duplicates.

- FROM station: Specifies the STATION table as the source of data.

- WHERE MOD(id, 2) = 0: Filters the results to include only rows where ID is even. The modulo operation (MOD(id, 2) = 0) checks if the ID number has no remainder "0" when divided by 2, meaning it’s even.
