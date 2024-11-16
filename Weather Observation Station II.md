Query the following two values from the __STATION__ table:

1. The sum of all values in LAT_N rounded to a scale of 2 decimal places.
2. The sum of all values in LONG_W rounded to a scale of 2 decimal places.


The STATION table is described as follows:

  __STATION__     
|Field        | Type                     
|------------ | ---------
|ID           | NUMBER
|CITY         | VARCHAR2(21)
|STATE        | VARCHAR2(2)
|LAT_N        | NUMBER
|LONG_W       | NUMBER

where __LAT_N__ is the northern latitude and __LONG_W__ is the western longitude.

-----------------------------

__Output Format__

Your results must be in the form:

```
lat lon
```

where _lat_ is the sum of all values in LAT_N and _lon_ is the sum of all values in LONG_W. Both results must be rounded to a scale of 2 decimal places.

-------------------------------

Here is the query:
```SQL
SELECT ROUND(SUM(lat_n), 2) AS lat,
       ROUND(SUM(long_n), 2) AS lon
FROM STATION;
```

**Explanation of the Query:**

- SELECT ROUND(SUM(lat_n), 2) AS lat: This part calculates the sum of all values in the LAT_N column, which represents the latitude.

  The ROUND function rounds this sum to two decimal places.

  The result is given an alias lat to make it easy to identify in the output.

- ROUND(SUM(long_n), 2) AS lon: Similarly, this calculates the sum of all values in the LONG_W column, representing the longitude.

  The ROUND function rounds this sum to two decimal places.

  The result is given an alias lon.

- FROM STATION: Indicates that the STATION table is the source of data.
