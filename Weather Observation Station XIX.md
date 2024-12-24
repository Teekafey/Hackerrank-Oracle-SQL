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
