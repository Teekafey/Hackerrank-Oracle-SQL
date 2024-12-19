Given the __CITY__ and __COUNTRY__ tables, query the names of all cities where the CONTINENT is 'Africa'.

__Note__: CITY.CountryCode and COUNTRY.Code are matching key columns.

__Input Format__

The CITY and COUNTRY tables are described as follows:


  __CITY__     
|Field        | Type                     
|------------ | ---------
|ID           | NUMBER
|NAME         | VARCHAR2(17)
|COUNTRYCODE  | VARCHAR2(3)
|DISTRICT     | VARCHAR2(20)
|POPULATION   | NUMBER

  __COUNTRY__     
|Field           | Type                     
|--------------- | ----------
|CODE            | VARCHAR2(3)
|NAME            | VARCHAR2(44)
|CONTINENT       | VARCHAR2(13)
|REGION          | VARCHAR2(25)
|SURFACEAREA     | NUMBER
|INDEPYEAR       | VARCHAR2(5)
|POPULATION      | NUMBER
|LIFEEXPECTANCY  | VARCHAR2(4)
|GNP             | NUMBER
|GNPOLD          | VARCHAR2(9)
|LOCALNAM        | VARCHAR2(44)
|GOVERNMENTFORM  | VARCHAR2(44)
|HEADOFSTATE     | VARCHAR2(32)
|CAPITAL         | VARCHAR2(4)
|CODE2           | VARCHAR2(2)



**Here is the query**:
```SQL
SELECT ci.name AS city_names
FROM city ci
JOIN country co
ON ci.countrycode = co.code
WHERE co.continent = 'Afrcia';
```

**Explanation of the Query:**

- SELECT ci.name AS city_names: Retrieves all names in te city table for all rows that match the specified condition. It also uses the _"ci"_ alias to refer to the **CITY** table, since we are using a JOIN.

- FROM city ci INNER JOIN country co: Combines the __CITY__ and __COUNTRY__ tables with alias _"ci"_ and _"co"_ respectively. It also uses the joined table as the source table.

- ON ci.countrycode = co.code: Defines the condition for the join; the __countrycode__ column in the city table must match the __code__ column in the country table. This ensures that each city is matched with the corresponding country.

- WHERE co.continent = 'Asia': Filters the results to include only those rows where the continent column in the country table is equal to "Africa".

