Query all columns for a city in __CITY__ with the ID 1661.

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
WHERE ID = 1661;
```


**Explanation of the Query:**
- SELECT * : This part of the query indicates that you want to retrieve all columns from the selected rows. It includes all available information about each city.

- FROM city: Specifies that the data is being selected from the CITY table.

- WHERE ID = 1661: This condition filters the results to include only city/cities with ID as 1661.
