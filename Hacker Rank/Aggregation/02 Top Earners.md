# Problem
We define an employee's total earnings to be their monthly salary x months worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as 2 space-separated integers.

Input Format
The Employee table containing employee data for a company is described as follows:

![image](https://github.com/user-attachments/assets/7cfe02c3-fe61-4318-9a65-7ac561c0d489)

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

# Solution
```
SELECT 
    MAX(salary * months) as earning,
    COUNT(*) as count
FROM Employee
WHERE salary * months = (SELECT MAX(salary*months) FROM Employee)
