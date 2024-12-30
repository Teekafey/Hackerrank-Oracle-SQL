A [median](https://en.wikipedia.org/wiki/Median) is defined as a number separating the higher half of a data set from the lower half. Query the median of the Northern Latitudes (LAT_N) from __STATION__ and round your answer to **4** decimal places.

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

**Here's the Query:**

```SQL
SELECT ROUND(MEDIAN(LAT_N), 4)
FROM STATION;
```

**Explanation of the Query**

- SELECT ROUND(MEDIAN(LAT_N), 4): Calculates the median of the set of lat_n values and then rounds the result to 4 decimal places, ensuring the output is precise to 4 decimal digits.

- FROM station: Specifies the STATION table as the source of data.
