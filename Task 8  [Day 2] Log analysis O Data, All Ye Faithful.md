# Task 8  [Day 2] Log analysis O Data, All Ye Faithful

---

<img width="1222" alt="Screenshot 2023-12-20 at 10 53 18 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/f7f74f2d-f2bb-4518-8fe7-c08ffaa0dca9">


Once the machine is up Proceed to the "Workbook.ipynb" Notebook, which can be found on the VM at 4_Capstone. 

Questions:
---
<img width="1440" alt="Screenshot 2023-12-20 at 9 46 05 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/d3deb5c4-d3fc-49ce-bc22-9c49b8aaed8b">

---

How many packets were captured (looking at the PacketNumber)?

Code: ```df.count()```

```
100
```
---
<img width="1440" alt="Screenshot 2023-12-20 at 9 49 00 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/929d46f3-5c2b-4681-8b9b-9e162f591d35">

---

What IP address sent the most amount of traffic during the packet capture?

Code: ```df.groupby(['Source']).size()```

```
10.10.1.4
```

---

<img width="1440" alt="Screenshot 2023-12-20 at 9 51 33 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/ba1b25a7-0cbc-471a-805a-b4ebaad5b5f6">

---

What was the most frequent protocol?

Code: ```df.groupby(['Protocol']).size().sort_values```

```
ICMP
```

