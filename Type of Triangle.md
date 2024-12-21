Write a query identifying the type of each record in the __TRIANGLES__ table using its three side lengths. Output one of the following statements for each record in the table:

- __Equilateral__: It's a triangle with **3** sides of equal length.

- __Isosceles__: It's a triangle with **2** sides of equal length.

- __Scalene__: It's a triangle with **3** sides of differing lengths.

- __Not A Triangle__: The given values of A, B, and C don't form a triangle.
  
__Input Format__

The __TRIANGLES__ table is described as follows:

|Column       | Type                     
|------------ | ---------
|A            | Integer
|B            | Integer
|C            | Integer

Each row in the table denotes the lengths of each of a triangle's three sides.

__Sample Input__

|Column       | Type                     
|------------ | ---------
|A            | Integer
|B            | Integer
|C            | Integer


__Sample Output__

```
Isosceles
Equilateral
Scalene
Not A Triangle
```

__Explanation__

Values in the tuple __$(20, 20, 23)$__ form an Isosceles triangle, because __$`A \equiv B`$__. 

Values in the tuple __$(20, 20, 20)$__ form an Equilateral triangle, because __$`A \equiv B \equiv C`$__.

Values in the tuple __$(20, 21, 22)$__ form a Scalene triangle, because __$`A \neq B \neq C`$__.

Values in the tuple __$(13, 14, 30)$__ cannot form a triangle because the combined value of sides __A__ and __B__ is not larger than that of side __C__.
