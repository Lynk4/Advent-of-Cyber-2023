# Task 14  [Day 8] Disk forensics Have a Holly, Jolly Byte!

---
### Task Objectives

Use FTK Imager to track down and piece together McGreedy's deleted digital breadcrumbs, exposing his evil scheme. Learn how to perform the following with FTK Imager:

- Analyse digital artefacts and evidence.
- Recover deleted digital artefacts and evidence.
- Verify the integrity of a drive/image used as evidence.

---

After the Machine is up go ahead and open ftk imager.


<img width="1440" alt="Screenshot 2023-12-28 at 3 09 51 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/952bd5d4-f731-4ad2-b627-09d1beee4d66">

---

open physical drive 2 by adding evidence inside ftk imager.

<img width="1440" alt="Screenshot 2023-12-28 at 3 12 04 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/d7277742-ceaf-4e7b-b40b-939b5d71d59f">


---

Questions:

---

What is the malware C2 server?

<img width="1440" alt="Screenshot 2023-12-28 at 3 16 51 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/e3408307-96be-4b5a-9cfe-83bcd085496b">


Answer
```
mcgreedysecretc2.thm
```

---

What is the file inside the deleted zip archive?

<img width="1440" alt="Screenshot 2023-12-28 at 3 19 12 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/2715e61b-66a0-47e4-864a-760f08f2b550">


Answer
```
JuicyTomaTOY.exe
```
---


What flag is hidden in one of the deleted PNG files?

<img width="1440" alt="Screenshot 2023-12-28 at 3 22 26 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/b0a64937-79d4-43a4-84be-975c8d84b898">

Answer
```
THM{byt3-L3vel_@n4Lys15}
```

---


What is the SHA1 hash of the physical drive and forensic image?

<img width="1440" alt="Screenshot 2023-12-28 at 3 26 01 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/48573021-2da0-4f9d-b80a-9a1515a44a05">


Answer
```
39f2dea6ffb43bf80d80f19d122076b3682773c2
```

---

