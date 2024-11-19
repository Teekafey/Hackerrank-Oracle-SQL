Query the difference between the maximum and minimum populations in __CITY__.

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
SELECT
    MAX(POPULATION) - MIN(POPULATION) AS pop_diff
FROM city;
```
**Explanation of the Query:**

- SELECT MAX(POPULATION) - MIN(POPULATION): Calculates the difference between the maximum "MAX(POPULATION)" and minimum population "MIN(POPULATION)" values in the city table.

- AS pop_diff: The result of the calculation is aliased as pop_diff, making it easier to reference in the output.

- FROM city: Specifies that the data is being retrieved from the CITY table.
