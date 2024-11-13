Write a query that prints a list of employee names (i.e.: the name attribute) for employees in __Employee__ having a salary greater than $2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.

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

![image](https://github.com/user-attachments/assets/15ef4dbb-7dbe-4bdc-af48-6e4a29060844)

__Sample Output__
```
Angela
Michael
Todd
Joe
```
-----------------------------------

Explanation

Angela has been an employee for 1 month and earns $3443  per month.

Michael has been an employee for 6 months and earns $2017 per month.

Todd has been an employee for 5 months and earns $3396 per month.

Joe has been an employee for 9 months and earns $3573 per month.

We order our output by ascending employee_id.


Here is the query:
```SQL
SELECT name
FROM employee
WHERE salary > 2000
AND months < 10
ORDER BY employee_id ASC;
```

**Explanation of the Query:**

- SELECT name: Retrieves only the name column from the Employee table.

- FROM employee: Specifies the __Employee__ table as the data source.

- WHERE salary > 2000: Filters for employees with a salary greater than $2000 per month.

- AND months < 10: Adds a condition to include only employees who have been working for less than 10 months.

- ORDER BY employee_id ASC:

  ORDER BY employee_id ASC: Orders the result by employee_id in ascending order to ensure results are sorted by employee_id.

  ASC is optional here since ascending order is the default for ORDER BY.
