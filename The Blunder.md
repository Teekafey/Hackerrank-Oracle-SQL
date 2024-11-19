Samantha was tasked with calculating the average monthly salaries for all employees in the __EMPLOYEES__ table, but did not realize her keyboard's **0** key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.

Write a query calculating the amount of error (i.e.: _**actual - miscalculated**_ average monthly salaries), and round it up to the next integer.

__Input Format__

The __EMPLOYEES__ table is described as follows:


|Column        | Type                     
|------------  | ---------
|ID            | Integer
|Name          | String
|Salary        | Integer

__Note:__ Salary is per month.

__Constraints__

**1000 < Salary << $`10^5`$.**

--------------------------------------------

__Sample Input__

|ID            | Name      | Salary                     
|------------  | --------- | -------
|1             | Kristen   | 1420
|2             | Ashley    | 2006
|3             | Julia     | 2210
|4             | Maria     | 3000


__Sample Output__

```
2061
```

__Explanation__

The table below shows the salaries without zeros as they were entered by Samantha:

|ID            | Name      | Salary                     
|------------  | --------- | -------
|1             | Kristen   | 142
|2             | Ashley    | 26
|3             | Julia     | 221
|4             | Maria     | 3

Samantha computes an average salary of **98.00**. The actual average salary is **2159.00**.

The resulting error between the two calculations is **2159.00 - 98.00 = 2061.00**. Since it is qual to the integer **2061**. It does not get rounded up.

------------------------------------------

Here is the query:
```SQL
SELECT
    CEIL(
         AVG(salary) - AVG(REPLACE(salary, 0, ''))
        )
FROM employees;
```
**Explanation of the Query:**

- SELECT: We’re querying the database to calculate a single value: the difference between the actual average salary and the miscalculated average salary, rounded up.

- AVG(salary): This calculates the *__actual__* average salary of all employees in the employees table.

- REPLACE(salary, 0, ''): For each salary, this removes all zeros. For example:
    - If a salary is 10500, it becomes 155.
    - If a salary is 7000, it becomes 7.
    - This simulates the error Samantha made due to her broken 0 key.

- AVG(REPLACE(salary, 0, '')): This calculates the __*miscalculated average*__ salary based on the salaries with zeros removed.

- AVG(salary) - AVG(REPLACE(salary, 0, '')): Subtracts the __*miscalculated average*__ from the actual average to find the error (the difference Samantha wants to know).

- CEIL(. . .): Rounds the difference up to the nearest integer, as instructed in the question.

- FROM employees: Specifies the table (employees) from which to retrieve the salary data.

------------------------------

The query helps Samantha by calculating the amount of error in her average salary calculation. It accounts for the fact that she unknowingly excluded zeros, finds the difference between the actual and miscalculated averages, and rounds the result up to the nearest integer.
