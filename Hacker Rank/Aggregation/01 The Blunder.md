# The Blunder
Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's  key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.
Write a query calculating the amount of error (i.e.:  average monthly salaries), and round it up to the next integer.

Input Format
The EMPLOYEES table is described as follows:
![image](https://github.com/user-attachments/assets/8879a6a4-ee0a-4574-a325-dd27abf947d8)

## Solution
```
WITH calculation as (
  SELECT 
    AVG(EMPLOYEES.Salary) as avg_salary,
    AVG(CAST(REPLACE(CAST(EMPLOYEES.Salary AS CHAR), '0', '') AS UNSIGNED)) As without_zero
  FROM EMPLOYEES)
SELECT CEIL(avg_salary-without_zero) as result
FROM calculation
