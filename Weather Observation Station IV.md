Find the difference between the total number of __CITY__ entries in the table and the number of distinct __CITY__ entries in the table.
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

For example, if there are three records in the table with __CITY__ values 'New York', 'New York', 'Bengalaru', there are 2 different city names: 'New York' and 'Bengalaru'. 

The query returns __1__, because __total number of records - number of unique city names = 3 - 2 = 1__  

Here is the query:
```SQL
SELECT
    (COUNT(city) - COUNT(DISTINCT(city))) AS duplicate_count
FROM station;
```

**Explanation of the Query:**

- COUNT(city): gives the total number of entries in the CITY column, including duplicates.
  
- COUNT(DISTINCT city): counts only unique entries in the CITY column.
  
- Subtracting COUNT(DISTINCT city) from COUNT(city): giveS you the number of duplicate CITY entries.
  
- FROM station: Indicates that the STATION table is the source of data.
