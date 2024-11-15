Query a list of __CITY__ and __STATE__ from the __STATION__ table.
The __STATION__ table is described as follows:

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
SELECT city,
       state
FROM station;
```

**Explanation of the Query:**
- SELECT city, state: Specifies that you want to retrieve the city and state fields, so only the names of cities and their corresponding states are returned.

- FROM station: Indicates that the STATION table is the source of data.
