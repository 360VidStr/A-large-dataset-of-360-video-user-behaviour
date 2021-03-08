There's a folder for each time bin
each foler contains 88 text files- a file for each video
each line of the text file has the following format

17 values in a row

0. video number
1. user number
2. yaw distribution - 25th percentile
3. yaw distribution - mean
4. yaw distribution - 75th percentile
5. pitch distribution - 25th percentile
6. pitch distribution - mean
7. pitch distribution - 75th percentile
8. %of the sphere covered during the time window
9. Maximum angle moved from initial position - pitch
10. Maximum angle moved from initial position - yaw
11. head movement speed in yaw - 25th percentile
12. head movement speed in yaw - mean
13. head movement speed in yaw - 75th percentile
14. head movement speed in pitch - 25th percentile
15. head movement speed in pitch - mean
16. head movement speed in pitch - 75th percentile

(I use 2-16 for VP trace clustering)