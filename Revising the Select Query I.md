Query all columns for all American cities in the __CITY__ table with populations larger than 100000. The __CountryCode__ for America is USA.

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
-- for cities located in the United States (CountryCode = 'USA')
-- with a population greater than 100,000.
SELECT *
FROM city
WHERE countrycode = 'USA'  -- Filters for cities in the USA
AND population > 100000;    -- Filters for cities with populations exceeding 100,000

```
**Explanation of the Query:**
- SELECT * : This part of the query indicates that you want to retrieve all columns from the selected rows. It includes all available information about each city.

- FROM city: Specifies that the data is being selected from the CITY table.

- WHERE countrycode = 'USA': This condition filters the results to include only cities that are located in the United States. The CountryCode for the USA is specified as 'USA'.

- AND population > 100000: This additional condition further filters the results to include only those cities with populations greater than 100,000, ensuring that only larger cities are returned.
