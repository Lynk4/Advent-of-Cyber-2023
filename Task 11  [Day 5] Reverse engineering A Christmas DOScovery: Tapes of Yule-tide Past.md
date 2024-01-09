# Task 11  [Day 5] Reverse engineering A Christmas DOScovery: Tapes of Yule-tide Past

---

<img width="1440" alt="Screenshot 2023-12-24 at 2 52 06 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/20df1df6-c202-4eaa-9387-45e744f55b03">

---
### Learning Objectives
- Experience how to navigate an unfamiliar legacy system.
- Learn about DOS and its connection to its contemporary, the Windows Command Prompt.
- Discover the significance of file signatures and magic bytes in data recovery and file system analysis.
---
After the machine is up.

Open AC2023.BAK using the MS-DOS Editor and the command 
```
EDIT C:\AC2023.BAK. 
```


As you can see, the current bytes are set to XX. According to the troubleshooting section we've read, BUMASTER.EXE expects the magic bytes of a file to be 41 43. These are hexadecimal values, however, so we need to convert them to their ASCII representations first.

Go back to the MS-DOS Editor window, move your cursor to the first two characters, remove XX, and replace it with AC. Once that's done, save the file by going to "File > Save".

---
<img width="1440" alt="Screenshot 2023-12-24 at 3 08 47 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/5bfc7517-d335-426c-916b-d1c5dbf6c70d">

---

Now, you can run the command 

```
BUMASTER.EXE C:\AC2023.BAK
```

---

 <img width="1440" alt="Screenshot 2023-12-24 at 3 10 20 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/af3f31ba-6bf2-4fc0-8ee1-587a949d7410">

---

***Questions:***

1. How large (in bytes) is the AC2023.BAK file?

ANSWER
```
12,704
```

2. What is the name of the backup program?

ANSWER
```
backupmaster3000
```

3. What should the correct bytes be in the backup's file signature to restore the backup properly?

ANSWER
```
41 43
```

4. What is the flag after restoring the backup successfully?

ANSWER
```
THM{0LD_5CH00L_C00L_d00D}
```

