Write a query that prints a list of employee names (i.e.: the name attribute) from the __Employee__ table in alphabetical order.

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
Bonnie
Frank
Joe
Kimberly
Lisa
Michael
Patrick
Rose
Todd
```
-----------------------------------

Here is the query:
```SQL
SELECT name
FROM employee
ORDER BY name ASC;
```

**Explanation of the Query:**

- SELECT name: Selects the name column from the __Employee__ table to retrieve the names of Employees who meet the conditions.

- FROM employee: Specifies the employee table as the data source.

- ORDER BY name ASC: Orders the name column in ascending (alphabetical) order. ASC is optional here since ascending order is the default for ORDER BY.
