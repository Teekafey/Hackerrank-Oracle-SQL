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
SELECT
    TRUNC(SUM(LAT_N), 4) AS sum_lat
FROM station
WHERE LAT_N > 38.7880
AND LAT_N < 137.2345;
```
**Explanation of the Query:**

- SELECT TRUNC(SUM(LAT_N), 4):
  - SUM(LAT_N): calculates the sum of all values in the LAT_N column that meet the conditions.

  - TRUNC(..., 4): truncates the result to 4 decimal places, ensuring the output is precise to 4 decimal digits without rounding. Read more about the TRUNC function [here.](https://docs.oracle.com/en/database/oracle/oracle-database/19/sqlrf/TRUNC-number.html)

- AS sum_lat: Gives the result an alias (sum_lat) for easier readability and access in the result set.
  
- FROM station: Specifies the STATION table as the source of data.

- WHERE **LAT_N > 38.7880** AND **LAT_N < 137.2345**: Filters rows where the LAT_N column's values are greater than **38.7880** **_AND_** less than **137.2345**. Only these rows are considered for the sum calculation.
