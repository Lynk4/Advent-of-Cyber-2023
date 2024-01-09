# Task 24  [Day 18] Eradication A Gift That Keeps on Giving


Learning Objectives

In this task, we will:

- Identify the CPU and memory usage of processes in Linux.
- Kill unwanted processes in Linux.
- Find ways a process can persist beyond termination.
- Remove persistent processes permanently.

---
After machine is up open the terminal and follow along.


***QUESTIONS***

1. What is the name of the service that respawns the process after killing it?

Command
```
systemctl list-unit-files
```

ANSWER
```
a-unkillable.service
```

<img width="1440" alt="Screenshot 2024-01-10 at 12 30 06 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/267fb596-af52-42d0-8cea-8db9a8c4f822">


---

2. What is the path from where the process and service were running?

Command
```
systemctl status a-unkillable.service
```

ANSWER
```
/etc/systemd/system/
```

<img width="1440" alt="Screenshot 2024-01-10 at 12 32 09 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/4cd4c0b3-6be1-45b5-bec1-ebc0e903bc78">


---

3. The malware prints a taunting message. When is the message shown? Choose from the options below.

1. Randomly

2. After a set interval

3. On process termination

4. None of the above

ANSWER
```
4
```

---
