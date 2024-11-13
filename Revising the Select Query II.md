Query the __NAME__ field for all American cities in the __CITY__ table with populations larger than 120000. The CountryCode for America is USA.

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
-- This query retrieves all  cities from the CITY table
-- for cities located in the United States (CountryCode = 'USA')
-- with a population greater than 120,000.
SELECT name  -- Selects the NAME field from the results
FROM city  -- Specifies the CITY table as the source of data
WHERE countrycode = 'USA'  -- Filters for cities in the USA
AND population > 120000;    -- Further filters for cities with populations greater than 120,000
```

**Explanation of the Query:**
- SELECT name: This part of the query indicates that you want to retrieve only the NAME field (i.e., the names of the cities) from the resulting rows.

- FROM city: Specifies that the data is being selected from the CITY table.

- WHERE countrycode = 'USA': This condition filters the results to include only cities that are located in the United States. The CountryCode for the USA is specified as 'USA'.

- AND population > 120000: This additional condition filters the results to include only those cities with populations greater than 120,000, ensuring that only larger cities are returned.
