Given the __CITY__ and __COUNTRY__ tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

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



Here is the query:

```SQL
SELECT co.Continent,
       FLOOR(AVG(ci.Population)) AS avg_citypop
FROM Country co
INNER JOIN City ci
ON co.Code = ci.Countrycode 
GROUP BY co.Continent;
```

**Explanation of the Query:**

- SELECT co.Continent, FLOOR(AVG(ci.Population)) AS avg_citypop:

  co.Continent: Retrieves the name of each continent from the Country table.

  FLOOR(AVG(ci.Population)): The FLOOR function rounds values down to the nearest integer. So this calculates the average population of cities within each continent (from the City table) and rounds it down to the nearest integer.

  AS  avg_citypop: Assigns an alias ( avg_citypop) to the calculated value.

FROM Country co:

- Specifies the Country table as the first table in the query and assigns it an alias (co) for reference.

INNER JOIN City ci:

- Combines the City table with the Country table using an inner join. It has an alias (ci).

ON co.Code = ci.Countrycode :

- With the ON clause, it connects rows from the Country table (co) with rows from the City table (ci) where the Code in the Country table matches the CountryCode in the City table.

GROUP BY co.Continent:
- Groups the data by each continent in the Country table (co.Continent), so the aggregate functions (like AVG) are calculated for each group (continent) independently.
