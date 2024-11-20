We define an employee's total earnings to be their monthly *__salary $`\times`$ months__*  worked, and the maximum total earnings to be the maximum total earnings for any employee in the __Employee__ table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as __2__ pace-separated integers.

__Input Format__

The  __Employee__ table containing employee data for a company is described as follows:

|Column        | Type                     
|------------  | ---------
|employee_id   | Integer
|name          | String
|months        | Integer
|salary        | Integer

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

-------------------------------

__Sample Input__

![image](https://github.com/user-attachments/assets/44805a88-f26d-47ee-ab7c-4086a283e67b)


__Sample Output__
```
69952 1
```
-----------------------------------

__Explanation:__

The table and earnings data is depicted in the following diagram:

![image](https://github.com/user-attachments/assets/e2d7ec85-0dd5-4f35-bc1a-586dfebbf00b)

The maximum earnings value is **69952**. The only employee with earnings **=69952** is Kimberly, so we print the maximum earnings value (**69952**) and a count of the number of employees who have earned **$69952** (which is **1**) as two space-separated values.

Here is the query:
```SQL
SELECT *
FROM (
      SELECT
          salary * months AS total_earnings,
          COUNT(*)
      FROM employee
      GROUP BY salary * months
      ORDER BY total_earnings DESC
     )
WHERE ROWNUM = 1;
```

**Explanation of the Query:**

- SELECT * FROM(. . .) : This means this OUTER query will retrieve all the columns from the subquery result.

- SELECT salary * months: This calculates the total earnings for each employee by multiplying their monthly salary (salary) by the number of months they worked (months).

- COUNT(*): This counts the number of employees with the same total earnings (useful to identify how many employees share the same maximum earnings).

- AS total_earnings: It renames the result as total_earnings using the alias AS.

- FROM employee: This specifies the table (employee) from which the data will be retrieved.

- GROUP BY salary * months: This groups the data by the calculated total_earnings. For each unique value of salary * months, the query calculates:
      - The total earnings (total_earnings).
      - The count of employees (COUNT(*)).
