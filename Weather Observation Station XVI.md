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
**Explanation of the Query:**

- SELECT TRUNC(MAX(LAT_N), 4):
  - MAX(LAT_N): returns the maximum of all values in the LAT_N column that meet the conditions.

  - TRUNC(..., 4): truncates the result to 4 decimal places, ensuring the output is precise to 4 decimal digits without rounding. Read more about the TRUNC function [here.](https://docs.oracle.com/en/database/oracle/oracle-database/19/sqlrf/TRUNC-number.html)

- AS max_lat: Gives the result an alias (max_lat) for easier readability and access in the result set.
  
- FROM station: Specifies the STATION table as the source of data.

- WHERE **LAT_N < 137.2345**: Filters rows where the LAT_N column's values less than **137.2345**. Only these rows are considered for the max calculation.
