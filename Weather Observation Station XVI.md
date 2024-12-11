Query the smallest Northern Latitude (LAT_N) from __STATION__  that is greater than **37.7780**. Round your answer to **4** decimal places.

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

```SQL
SELECT ROUND(MIN(LAT_N), 4) as min_lat
FROM station
WHERE LAT_N > 38.7780;
```

