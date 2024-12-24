Consider __$`P_1 (a, c)`$__ and __$`P_2 (b, d)`$__ to be two points on a 2D plane where (a, b) are the respective minimum and maximum values of Northern Latitude (LAT_N) and (c, d) are the respective minimum and maximum values of Western Longitude (LONG_W) in  __STATION__.

Query the [Euclidean Distance](https://en.wikipedia.org/wiki/Euclidean_distance) between points $`P_1`$ and $`P_2`$ and round it to a scale of **4** decimal places.

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

**_In a plane with $`P_1`$ at (a, c) and $`P_2`$ at (b, d), the Euclidean distance is $`\sqrt{(a - c)^2 + (b - d)^2}`$ ._**

**Here's the Query:**

```SQL
SELECT ROUND(
             SQRT(POWER((MIN(lat_n)- MAX(lat_n)), 2) + POWER((MIN(long_w)- MAX(long_w)), 2))
             ,4) 
FROM  station;
```

**Explanation of the Query**

- SELECT ROUND(. . . , 4): Rounds the result to 4 decimal places, ensuring the output is precise to 4 decimal digits.

- SQRT(. . . ): Returns the squareroot of the calculation

- POWER(. . . , 2) + POWER(. . . , 2): Calculates the 2nd power of each of the two operations and adds them together.

- MIN(lat_n) and MAX(lat_n): These find the minimum and maximum northern latitude values, respectively.

- MIN(long_w) and MAX(long_w): These find the minimum and maximum western longitude values, respectively.

- POWER((MIN(lat_n)- MAX(lat_n)), 2): Calculates the difference between the minimum and maximum northern latitude values and raises them to the second power. It results a positive number becasue it is squared.

- POWER((MIN(long_w)- MAX(long_w)), 2): Calculates the difference between the minimum and maximum western longitude values and raises them to the second power. It results a positive number becasue it is squared.

- FROM station: Specifies the STATION table as the source of data.
