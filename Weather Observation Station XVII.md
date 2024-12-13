Query the Western Longitude (LONG_W)where the smallest Northern Latitude (LAT_N) in __STATION__ is greater than **37.7780**. Round your answer to **4** decimal places.

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
SELECT
    ROUND(LONG_W, 4) AS long_min_lat
FROM station
WHERE LAT_N =
             (SELECT MIN(LAT_N) AS min_lat
              FROM station
              WHERE LAT_N > 38.7780);
```


**Explanation of the Query:**

- SELECT ROUND(LONG_W, 4): rounds the result to 4 decimal places, ensuring the output is precise to 4 decimal digits.

- AS long_min_lat: Gives the result an alias (long_min_lat) for easier readability and access in the result set.
  
- FROM station: Specifies the STATION table as the source of data.

- WHERE LAT_N = (SELECT MIN(LAT_N) AS min_lat FROM station WHERE LAT_N > 38.7780):

  This part of the query is a subquery, which is a query nested within another query.

  - SELECT MIN(LAT_N): This part finds the minimum value of the LAT_N column from the station table.
  
  - WHERE LAT_N > 38.7780: This filters the results to only include rows where the LAT_N value is greater than 38.7780.

  - WHERE LAT_N = ...: This part takes the result of the subquery (the minimum LAT_N value) and filters the main query to only include rows with that exact LAT_N value.

-----------------------------------------

**Why use a Subquery, you may ask?**

_I used a subquery because you needed to find the specific minimum latitude value first, and then use that value to filter the rest of your data. It's like finding the shortest person in a room and then asking for their shoe size. You have to identify the shortest person first before you can ask about their shoes. The subquery helps you identify that minimum latitude value, making the main query more focused and efficient_.
