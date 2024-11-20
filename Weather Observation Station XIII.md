Query the sum of Northern Latitudes (LAT_N) from __STATION__ having values greater than **38.7880** and less than **137.2345**. Truncate your answer to **4**  decimal places.

__Input Format__

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
SELECT TRUNC(SUM(LAT_N), 4) AS sum_lat
FROM station
WHERE LAT_N > 38.7880 AND LAT_N < 137.2345;
```
