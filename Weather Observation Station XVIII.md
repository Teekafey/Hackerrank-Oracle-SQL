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

**Here's the Query:**

```SQL
