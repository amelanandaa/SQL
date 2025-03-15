# Problem
Consider P1(a,b) and P2(c,d) to be two points on a 2D plane.
- a happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
- b happens to equal the minimum value in Western Longitude (LONG_W in STATION).
- c happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
- d happens to equal the maximum value in Western Longitude (LONG_W in STATION).
Query the Manhattan Distance between points P1 and P2 and round it to a scale of  decimal places.

Input Format

The STATION table is described as follows:

![image](https://github.com/user-attachments/assets/90b4c990-ca9a-412f-8b18-ed9158201bdc)

# Solution
Manhattan distance : The distance between two points measured along axes at right angles. In a plane with p1 at (x1, y1) and p2 at (x2, y2), it is |x1 - x2| + |y1 - y2|.
```
WITH distance as(
    SELECT 
        MIN(LAT_N) as a,
        MIN(LONG_W) as b,
        MAX(LAT_N) as c,
        MAX(LONG_W) as d
    FROM STATION)
SELECT
    ROUND((ABS(a-c))+(ABS(b-d)),4) as manhattan
FROM distance
```
