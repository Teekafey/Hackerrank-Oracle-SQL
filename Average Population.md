Query the average population for all cities in __CITY__, rounded down to the nearest integer.

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
SELECT FLOOR(AVG(population))
FROM city;
```

**Explanation of the Query:**

- SELECT FLOOR(AVG(population)):

  AVG(population): Calculates the average population of all the cities in the CITY table.
  
  FLOOR(): Rounds the result of the AVG(population) down to the nearest whole number.

- FROM city: Specifies that the data is being retrieved from the CITY table.
