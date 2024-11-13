Query the total population of all cities in __CITY__ where District is California.

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
SELECT SUM(population)
FROM city
WHERE district = 'California';
```

**Explanation of the Query:**

- SELECT SUM(population): calculates the total population by adding up the population values for all rows that match the specified condition.

- FROM city: Specifies that the data is being retrieved from the CITY table.

- WHERE district = 'California': Filters the results to include only those rows where the district is "California".
