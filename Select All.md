Query all columns (attributes) for every row in the __CITY__ table.

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
-- This query retrieves all columns from the CITY table
SELECT *
FROM city;
```

**Explanation of the Query:**
- SELECT * : This query indicates that you want to retrieve all columns from the selected rows. It includes all available information about each city.
