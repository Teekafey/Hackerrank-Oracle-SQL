Query a count of the number of cities in __CITY__ having a Population larger than 100,000

The __CITY__ table is described as follows:

  __CITY__     
|Field        | Type                     
|------------ | ---------
|ID           | NUMBER
|NAME         | VARCHAR2(17)
|COUNTRYCODE  | VARCHAR2(3)
|DISTRICT     | VARCHAR2(20)
|POPULATION   | NUMBER

Here is the query:
```SQL
SELECT COUNT(name)
FROM city
WHERE population > 100000;
```

**Explanation of the Query:**

- SELECT COUNT(name): counts the number of non-null values in the name column, which effectively counts the number of cities that meet the criteria.

- FROM city: Specifies that the data is being queried from the CITY table.

- WHERE population > 100000: This condition filters the results to only include cities where the population is greater than 100,000.
