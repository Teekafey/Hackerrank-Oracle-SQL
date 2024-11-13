Query all attributes of every Japanese city in the __CITY__ table. The __COUNTRYCODE__ for Japan is JPN.

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
SELECT *
FROM city
WHERE countrycode = 'JPN';
```
**Explanation of the Query:**
- SELECT * : This part of the query indicates that you want to retrieve all columns from the selected rows. It includes all available information about each city.

- FROM city: Specifies that the data is being selected from the CITY table.

- WHERE countrycode = 'JPN': This condition filters the results to include only cities that are located in Japan. The CountryCode for the Japan is specified as 'JPN'.
