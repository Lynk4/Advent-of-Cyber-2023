# Task 23  [Day 17] Traffic analysis I Tawt I Taw A C2 Tat!

---

Learning Objectives

- Gain knowledge of the network traffic data format
- Understand the differences between full packet captures and network flows
- Learn how to process network flow data
- Discover the SiLK tool suite
- Gain hands-on experience in network flow analysis with SiLK

---

QUESTIONS:

1. Which version of SiLK is installed on the VM?

Command:
```
rwfileinfo suspicious-flows.silk
```

ANSWER
```
3.19.1
```

<img width="1440" alt="1" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/b7226eba-e066-432f-b7a9-b95264ca85ae">

---

2. What is the size of the flows in the count records?

Command
```
rwfileinfo suspicious-flows.silk
```

ANSWER
```
11774
```

<img width="1440" alt="2" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/32059429-b807-4e13-a7bf-973f15d605db">

---

3. What is the start time (sTime) of the sixth record in the file?

Command:
```
rwcut suspicious-flows.silk --fields=sTime --num-recs=6
```

ANSWER
```
2023/12/05T09:33:07.755
```

<img width="1440" alt="3" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/4e6f4321-75ee-49f3-8449-26352310b867">

---

4. What is the destination port of the sixth UDP record?

Command
```
rwfilter suspicious-flows.silk --proto=17 --pass=stdout | rwcut --fields=protocol,sIP,sPort,dIP,dPort --num-recs=5
```

ANSWER
```
49950
```

<img width="1440" alt="4" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/0640ebb4-20f3-4fb2-a351-98504d5f19a4">

---

5. What is the record value (%) of the dport 53?

Command
```
rwstats suspicious-flows.silk --fields=dPort --values=records --count=5
```

ANSWER
```
35.332088
```

<img width="1440" alt="5" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/b8f9daa2-d639-45c4-9fce-a82dcd61f1ab">


---

6. What is the number of bytes transmitted by the top talker on the network?

Command
```
rwstats suspicious-flows.silk --fields=sIP --values=bytes --count=10 --top
```

ANSWER
```
735229
```

<img width="1440" alt="6" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/c5f7a786-1984-4dc8-a3de-977f82ee5560">

---

7. What is the sTime value of the first DNS record going to port 53?

Command
```
rwfilter suspicious-flows.silk --aport=53 --pass=stdout | rwcut --fields=sTime,sIP,dIP --num-recs=1
```

ANSWER
```
2023/12/08T04:28:44.825
```

<img width="1440" alt="7" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/776bfc2c-5a12-43b5-a986-4032c5464ed6">

---

8. What is the IP address of the host that the C2 potentially controls? (In defanged format: 123[.]456[.]789[.]0 )

Command
```
rwfilter suspicious-flows.silk --aport=53 --pass=stdout | rwstats --fields=sIP,dIP --values=records,bytes,packets --count=10
```

ANSWER We have to write the answer in defanged format:
```
175[.]175[.]173[.]221
```

<img width="1440" alt="8" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/a7fbd416-85a3-446d-ba59-9fc03edf9bb4">

---

9. Which IP address is suspected to be the flood attacker? (In defanged format: 123[.]456[.]789[.]0 )

Command
```
rwfilter suspicious-flows.silk --aport=80 --pass=stdout | rwstats --fields=sIP,dIP,dPort --count=10
```

ANSWER
```
175[.]215[.]236[.]223
```

<img width="1440" alt="9" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/0720c15e-4b77-4410-aef6-9bf55d915d60">

---

10. What is the sent SYN packet's number of records?

Command
```
rwstats suspicious-flows.silk --fields=sIP,dIP --values=records,packets --count=10
```

ANSWER
```
1658
```

<img width="1440" alt="10" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/23783933-a289-4a02-a7aa-c0bfa9b1bf44">

---

