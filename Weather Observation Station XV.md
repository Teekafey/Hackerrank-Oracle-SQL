Query the Western Longitude (LONG_W) for the largest Northern Latitudes (LAT_N) from __STATION__  less than **137.2345**. Truncate your answer to **4**  decimal places.

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
    ROUND(LONG_W, 4) AS long_max_lat
FROM station 
WHERE LAT_N =
             (SELECT MAX(LAT_N) AS max_lat
              FROM station
              WHERE LAT_N < 137.2345);
```

**Explanation of the Query:**

- SELECT ROUND(LONG_W, 4): rounds the result to 4 decimal places, ensuring the output is precise to 4 decimal digits.

- AS long_max_lat: Gives the result an alias (long_max_lat) for easier readability and access in the result set.
  
- FROM station: Specifies the STATION table as the source of data.

- WHERE LAT_N = (SELECT MAX(LAT_N) AS max_lat FROM station WHERE LAT_N < 137.2345):

  This part of the query is a subquery, which is a query nested within another query.

  - SELECT MAX(LAT_N): This part finds the maximum value of the LAT_N column from the station table.
  
  - WHERE LAT_N < 137.2345: This filters the results to only include rows where the LAT_N value is less than 137.2345.

  - WHERE LAT_N = . . . : This part takes the result of the subquery (the maximum LAT_N value) and filters the main query to only include rows with that exact LAT_N value.

-----------------------------------------

**Why use a Subquery, you may ask?**

_I used a subquery because you needed to find the specific maximum latitude value first, and then use that value to filter the rest of your data. It's like finding the tallest person in a room and then asking for their shoe size. You have to identify the tallest person first before you can ask about their shoes. The subquery helps you identify that maximum latitude value, making the main query more focused and efficient_.
