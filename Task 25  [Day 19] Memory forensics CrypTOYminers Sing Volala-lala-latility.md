# Task 25  [Day 19] Memory forensics CrypTOYminers Sing Volala-lala-latility

---

Learning Objectives

﻿- Understand what memory forensics is and how to use it in a digital forensics investigation
- Understand what volatile data and memory dumps are
- Learn about Volatility and how it can be used to analyse a memory dump
- Learn about Volatility profiles
---


Creating profiles is out of scope for this room, so for your convenience, a profile is already in the ```/home/ubuntu/Desktop/Evidence``` directory called Ubuntu_5.4.0-163-generic_profile.zip.

Open up the terminal

got to ```/home/ubuntu/Desktop/Evidence``` this directory.

To use the profile, we have to copy it where Volatility stores the various profiles for Linux. The command 
```
cp Ubuntu_5.4.0-163-generic_profile.zip ~/.local/lib/python2.7/site-packages/volatility/plugins/overlays/linux/
```

<img width="1440" alt="Screenshot 2024-01-10 at 3 21 14 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/381c7035-4bbc-4a6d-8426-65a32a8b3d80">

---

To examine the history file for any such commands, we can use the linux_bash plugin. 

Command
```
vol.py -f linux.mem --profile="LinuxUbuntu_5_4_0-163-generic_profilex64" linux_bash
```

<img width="1440" alt="Screenshot 2024-01-10 at 3 24 12 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/dabf34e1-2aff-4878-9947-6cbd7a1afc0b">

---

**After running the above command we find mysql password:**

<img width="1440" alt="Screenshot 2024-01-10 at 3 25 50 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/93a2172e-cbfa-4747-a58e-c7a277129ab7">

---














**QUESTIONS**

1. What is the exposed password that we find from the bash history output?

ANSWER
```
NEhX4VSrN7sV
```

<img width="1440" alt="Screenshot 2024-01-10 at 3 27 38 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/4bc773d1-5732-438a-be62-2c0089b2b863">


---
2. What is the PID of the miner process that we find?

ANSWER
```
10280
```

To find PID Command:
```
vol.py -f linux.mem --profile="LinuxUbuntu_5_4_0-163-generic_profilex64" linux_pslist
```

<img width="1440" alt="Screenshot 2024-01-10 at 3 30 06 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/3e291cdb-fba9-4d9b-81ba-b88fc039047d">


   
---
3. What is the MD5 hash of the miner process?

ANSWER
```
153a5c8efe4aa3be240e5dc645480dee
```

To extract a process first we need to create a directory.
command
```
mkdir extracted
```
```
vol.py -f linux.mem --profile="LinuxUbuntu_5_4_0-163-generic_profilex64" linux_procdump -D extracted -p 10280
```

now go to extracted folder then use 

```
md5sum miner.10280.0x400000
```

<img width="1440" alt="Screenshot 2024-01-10 at 3 35 31 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/7d47b081-449b-4a31-9b0c-711f162fc947">


---
4. What is the MD5 hash of the mysqlserver process?

ANSWER
```
c586e774bb2aa17819d7faae18dad7d1
```

First of all we need find the process id of mysqlserver. command:
```
vol.py -f linux.mem --profile="LinuxUbuntu_5_4_0-163-generic_profilex64" linux_pslist
```
process id of mysqlserver : 10291
then run 

command:
```
vol.py -f linux.mem --profile="LinuxUbuntu_5_4_0-163-generic_profilex64" linux_procdump -D extracted -p 10291
```

now go to extracted folder then use 

```
md5sum mysqlserver.10291.0x400000
```


<img width="1440" alt="Screenshot 2024-01-10 at 3 40 30 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/a6b7a4b8-0dc3-4a33-9994-890df98e928e">



---
5. Use the command ```strings extracted/miner.<PID from question 2>.0x400000 | grep http://```. What is the suspicious URL? (Fully defang the URL using CyberChef)

ANSWER
```
hxxp[://]mcgreedysecretc2[.]thm
```

Runthe command:
```
strings miner.10280.0x400000 | grep http://
```

<img width="1440" alt="Screenshot 2024-01-10 at 3 47 51 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/4f4eb8a2-79a7-439c-8f7f-165160dbc4d2">



---
6. After reading the elfie file, what location is the mysqlserver process dropped in on the file system?

ANSWER
```
/var/tmp/.system-python3.8-Updates/mysqlserver
```

run 
```
vol.py -f linux.mem --profile="LinuxUbuntu_5_4_0-163-generic_profilex64" linux_enumerate_files | grep -i cron
```

<img width="1440" alt="Screenshot 2024-01-10 at 3 51 22 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/bbd3a6f1-0125-448d-bd66-4b5aae979735">

now run 
```
vol.py -f linux.mem --profile="LinuxUbuntu_5_4_0-163-generic_profilex64" linux_find_file -i 0xffff9ce9b78280e8 -O extracted/elfie
```

go to extracted folder and cat elfie


<img width="1440" alt="Screenshot 2024-01-10 at 3 54 32 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/28958025-8ced-4d92-8f63-5d48c595c900">

---
