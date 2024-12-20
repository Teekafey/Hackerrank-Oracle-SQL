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

**Here's the Query:**
```SQL
SELECT ROUND(MIN(LAT_N), 4) as min_lat
FROM station
WHERE LAT_N > 38.7780;
```
**Explanation of the Query:**

- SELECT ROUND(MIN(LAT_N), 4):
  - MIN(LAT_N): returns the minimum of all values in the LAT_N column that meet the conditions.

  - ROUND(..., 4): rounds the result to 4 decimal places, ensuring the output is precise to 4 decimal digits. 

- AS min_lat: Gives the result an alias (min_lat) for easier readability and access in the result set.
  
- FROM station: Specifies the STATION table as the source of data.

- WHERE **LAT_N > 38.7780**: Filters rows where the LAT_N column's values greater than **38.7780**. Only these rows are considered for the min calculation.
