Consider __$`P_1 (a, b)`$__ and __$`P_2 (c, d)`$__ to be two points on a 2D plane.

- __$`a`$__ happens to equal the minimum value in Northern Latitude (LAT_N in __STATION__).
- __$`b`$__ happens to equal the minimum value in Western Longitude (LONG_W in __STATION__).
- __$`c`$__ happens to equal the maximum value in Northern Latitude (LAT_N in __STATION__).
- __$`d`$__ happens to equal the maximum value in Western Longitude (LONG_W in __STATION__).

Query the [Manhattan Distance](https://xlinux.nist.gov/dads/HTML/manhattanDistance.html) between points $`P_1`$ and $`P_2`$ and round it to a scale of **4** decimal places.

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

**_In a plane with $`P_1`$ at (a, b) and $`P_2`$ at (c, d), the Manhattan distance is $`|a - c| + |b - d|`$._**

**Here's the Query:**

```SQL
SELECT ROUND(
             ABS(MAX(lat_n)- MIN(lat_n)) + ABS(MAX(long_w)- MIN(long_w))
             ,4) 
FROM  station;
```

**Explanation of the Query**

- SELECT ROUND(. . . , 4): Rounds the result to 4 decimal places, ensuring the output is precise to 4 decimal digits.

- ABS(. . .) + ABS(. . .): Adds the two absolute differences to calculate the total Manhattan Distance.

- MAX(lat_n) and MIN(lat_n): These find the maximum and minimum northern latitude values, respectively.

- MAX(long_w) and MIN(long_w): These find the maximum and minimum western longitude values, respectively.

- ABS(MAX(lat_n) - MIN(lat_n)): Calculates the absolute difference between the maximum and minimum northern latitude values. This represents the distance in the latitude direction.

- ABS(MAX(long_w) - MIN(long_w)): Calculates the absolute difference between the maximum and minimum western longitude values. This represents the distance in the longitude direction.

- FROM station: Specifies the STATION table as the source of data.
