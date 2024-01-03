# Task 19  [Day 13] Intrusion detection To the Pots, Through the Walls


---
Learning Objectives
In today's task, you will:

- Learn to understand incident analysis through the Diamond Model.
- Identify defensive strategies that can be applied to the Diamond Model.
- Learn to set up firewall rules and a honeypot as defensive strategies.
---

After the machine is up. login via ssh.
credentials: 

Username:	```vantwinkle```
Password:	```TwinkleStar```

---

After Succesfull login Swith to root user
```
sudo su -
```

Now go to ```/home/vantwinkle/```

You will find a script named as ***Van_Twinkle_rules.sh***

Run this script.

<img width="1172" alt="script" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/814209b0-36d7-42b2-b94d-a212cd462bc8">


---

***QUESTIONS***

1. Which security model is being used to analyse the breach and defence strategies?

Answer
```
Diamond model
```

2. Which defence capability is used to actively search for signs of malicious activity?

Answer
```
threat hunting
```

3. What are our main two infrastructure focuses? (Answer format: answer1 and answer2)

Answer
```
firewall and honeypot
```

4. Which firewall command is used to block traffic?

Answer
```
deny
```

5. There is a flag in one of the stories. Can you find it?

Answer
```
THM{P0T$_W@11S_4_S@N7@}
```
First Scan the machine using nmap.

---
<img width="936" alt="nmap" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/420a8f10-b101-4e5a-942b-5b9a9b315ff0">

---

The flag is in the port 8090 but this port is blocked by the firewall.
To enable 8090 port

Command
```
ufw allow 8090/tcp
```
---

<img width="1165" alt="Screenshot 2024-01-03 at 4 12 02 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/501cf947-921e-4142-9136-a5968c86b7a4">

---

<img width="1308" alt="flag" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/49d79e4c-48ff-4787-870e-0a18d73cbc8e">


---

