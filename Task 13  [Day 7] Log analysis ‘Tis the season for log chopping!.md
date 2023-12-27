# Task 13  [Day 7] Log analysis ‘Tis the season for log chopping!

---
<img width="1440" alt="Screenshot 2023-12-27 at 9 58 45 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/ed421fdf-233b-42ae-b157-87788ae12738">

---
Learning  Objectives


In this task, we will focus on the following vital learnings to assist Forensic McBlue in uncovering the potential incident:

- Revisiting log files and their importance.
- Understanding what a proxy is and breaking down the contents of a proxy log.
- Building Linux command-line skills to parse log entries manually.
- Analysing a proxy log based on typical use cases.
---

***Questions:***

How many unique IP addresses are connected to the proxy server?

<img width="1440" alt="1" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/d14a5082-93ff-4d97-b02d-a001fe2386eb">

Command 

```
cut -d ' ' -f2 access.log | sort | uniq -c | sort -n | wc -l
```

