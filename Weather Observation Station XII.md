Query the list of CITY names from __STATION__ that either do not start with vowels and do __not__ end with vowels. Your result cannot contain duplicates.

  __STATION__     
|Field        | Type                     
|------------ | ---------
|ID           | NUMBER
|CITY         | VARCHAR2(21)
|STATE        | VARCHAR2(2)
|LAT_N        | NUMBER
|LONG_W       | NUMBER

where __LAT_N__ is the northern latitude and __LONG_W__ is the western longitude.

Here is the query:
```SQL
SELECT DISTINCT(CITY)
FROM STATION 
WHERE SUBSTR(CITY, 1, 1) NOT IN ('A', 'E', 'I', 'O', 'U')
AND SUBSTR(CITY, -1, 1) NOT IN ('A', 'E', 'I', 'O', 'U');
```

**Explanation of the Query:**

- SELECT DISTINCT(CITY): This selects unique (__DISTINCT__) entries from the CITY column, which means any duplicate city names will only appear once in the results.

- FROM station: Indicates that the STATION table is the source of data.

- WHERE SUBSTR(CITY, 1, 1) NOT IN ('A', 'E', 'I', 'O', 'U'): This WHERE clause filters the results to include only cities where the first character of CITY is __not__ a vowel.

  SUBSTR(CITY, 1, 1): extracts the first character of the CITY name. Learn more about SUBSTR [here.](https://docs.oracle.com/en/database/oracle/oracle-database/21/sqlrf/SUBSTR.html)
   
  NOT IN ('A', 'E', 'I', 'O', 'U'): ensures that the first character is not one of the specified vowels.

- AND SUBSTR(CITY, -1, 1) NOT IN ('A', 'E', 'I', 'O', 'U'): Adds another condition to the WHERE clause, filtering the cities further to include only those where the last character is also __not__ a vowel.

  SUBSTR(CITY, -1, 1): extracts the last character of the CITY name. Learn more about SUBSTR [here.](https://docs.oracle.com/en/database/oracle/oracle-database/21/sqlrf/SUBSTR.html)
   
  NOT IN ('A', 'E', 'I', 'O', 'U'): ensures that the last character is not one of the specified vowels.
