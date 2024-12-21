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

-------------------------------

__Sample Input__

|A       |B      |C                     
|------- |------ |------
|20      |20     |23
|20      |20     |20
|20      |21     |22
|13      |14     |30

__Sample Output__

```
Isosceles
Equilateral
Scalene
Not A Triangle
```
------------------------------------

__Explanation__

Values in the tuple __$(20, 20, 23)$__ form an Isosceles triangle, because __$`A \equiv B`$__. 

Values in the tuple __$(20, 20, 20)$__ form an Equilateral triangle, because __$`A \equiv B \equiv C`$__.

Values in the tuple __$(20, 21, 22)$__ form a Scalene triangle, because __$`A \neq B \neq C`$__.

Values in the tuple __$(13, 14, 30)$__ cannot form a triangle because the combined value of sides __A__ and __B__ is not larger than that of side __C__.

------------------------------------------

**Here's the Query**
```SQL
SELECT 
    (CASE 
         WHEN (A = B AND B = C AND C = A) THEN 'Equilateral'
         WHEN (A = B OR A = C OR B = C) AND (A + B > C AND B + C > A AND C + A > B) THEN 'Isosceles'
         WHEN (A != B AND B != C AND C != A) AND (A + B > C AND B + C > A AND C + A > B) THEN 'Scalene'
     ELSE 'Not A Triangle'
     END) AS Triangle_type
FROM TRIANGLES;
```

**Explanation of the Query**

- SELECT (CASE . . . END) : Starts the query to select data from the TRIANGLES table, begins the CASE statement, which evaluates a series of conditions to determine the type of triangle, then ends the case statement.

- WHEN (A = B AND B = C AND C = A) THEN 'Equilateral': An equilateral triangle has all three sides of equal length. It checks if all three sides are equal and returns 'Equilateral'.

- WHEN (A = B OR A = C OR B = C) AND (A + B > C AND B + C > A AND C + A > B) THEN 'Isosceles': Checks if any two sides are equal with the OR statement. It also verifies the triangle inequality rule: __A + B > C, B + C > A, C + A > B__. If true, the triangle is classified as 'Isosceles'. An isosceles triangle has at least two equal sides, but it must also form a valid triangle.

- WHEN (A != B AND B != C AND C != A) AND (A + B > C AND B + C > A AND C + A > B) THEN 'Scalene': Checks if all three sides are different. It also verifies the triangle inequality rule: __A + B > C, B + C > A, C + A > B__. A scalene triangle has all sides of different lengths and must form a valid triangle.

- AS Triangle_type: The result of the CASE statement is given an alias.

- FROM TRIANGLES: Specifies the source table (TRIANGLES) containing the data.
