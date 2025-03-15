# Problem
Consider P1(a,c) and P2(b,d) to be two points on a 2D plane where (a,b) are the respective minimum and maximum values of Northern Latitude (LAT_N) and (c,d) are the respective minimum and maximum values of Western Longitude (LONG_W) in STATION.

Query the Euclidean Distance between points P1 and P2 and format your answer to display 4 decimal digits.

Input Format

The STATION table is described as follows:

![image](https://github.com/user-attachments/assets/e0f7d1b8-31b9-49d7-aec4-8f2e2cf8b29f)

# Solution
Euclidean Distance = ![image](https://github.com/user-attachments/assets/46cc21ee-74f0-4f40-9538-d56e74b82143)

```
WITH distance as(
    SELECT 
        MIN(LAT_N) AS a,
        MAX(LAT_N) AS b,
        MIN(LONG_W) AS c,
        MAX(LONG_W) AS d
    FROM STATION)
SELECT 
    ROUND(SQRT((POWER(a-b, 2))+(POWER(c-d, 2))),4) as result
FROM distance
