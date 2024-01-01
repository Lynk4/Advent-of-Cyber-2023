# Task 16  [Day 10] SQL injection Inject the Halls with EXEC Queries

---
<img width="1240" alt="Screenshot 2024-01-01 at 3 41 11 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/16571ef9-aa15-4670-9f3b-57454f7d66ee">

---

After the machine is up go to machine ip:

***QUESTIONS***

1. Manually navigate the defaced website to find the vulnerable search form. What is the first webpage you come across that contains the gift-finding feature?

Answer
```
/giftsearch.php
```

<img width="1303" alt="1" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/9484387d-c216-4482-bc46-7fbf86e79961">

---

2. Analyze the SQL error message that is returned. What ODBC Driver is being used in the back end of the website?

Answer
```
ODBC Driver 17 for SQL Server]
```
<img width="1301" alt="2" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/17e35d8c-5635-499a-a188-d21e82956840">

---

3. Inject the 1=1 condition into the Gift Search form. What is the last result returned in the database?

Answer
```
THM{a4ffc901c27fb89efe3c31642ece4447}
```

<img width="1304" alt="3" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/764d863d-ab30-4158-87a8-4eb5b7f6a5bf">

---

4. What flag is in the note file Gr33dstr left behind on the system?

Answer
```
THM{b06674fedd8dfc28ca75176d3d51409e}
```

<img width="1150" alt="4" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/f23a719b-60f5-4900-aa03-43461330465a">

---

5. What is the flag you receive on the homepage after restoring the website?

Answer
```
 THM{4cbc043631e322450bc55b42c}
```

<img width="1298" alt="5" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/36debe5a-43af-4d55-93bf-ab6fb4abb50b">

---

