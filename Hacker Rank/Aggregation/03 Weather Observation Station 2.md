# Problem
Query the following two values from the STATION table:
1. The sum of all values in LAT_N rounded to a scale of  decimal places.
2. The sum of all values in LONG_W rounded to a scale of  decimal places.
Input Format

The STATION table is described as follows:

![image](https://github.com/user-attachments/assets/525f0a8c-a4be-4db1-9c31-9b6f47fb3b33)

where LAT_N is the northern latitude and LONG_W is the western longitude.

# Solution
```
SELECT 
    ROUND(SUM(LAT_N), 2) as lat,
    ROUND(SUM(LONG_W), 2) as lon
FROM STATION
