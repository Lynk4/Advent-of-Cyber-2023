# Task 18  [Day 12] Defence in depth Sleighing Threats, One Layer at a Time

---
### Learning Objectives

- Defence in Depth
- Basic Endpoint Hardening
- Simple Boot2Root Methodology

---

After the machine is up.

Log in to the admin account via SSH using the credentials supplied below. 

Username:	
```
admin
```
Password:	
```
SuperStrongPassword123
```

---
QUESTIONS:

1. What is the default port for Jenkins?

Answer
```
8080
```
---

2. What is the password of the user tracy?

Answer
```
13_1n_33
```

Password of the user tracy is in the ```/opt/scripts/backup.sh``` file:

<img width="935" alt="2" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/8eb4bb48-8958-4c97-840d-a86361ab84b6">

---

3. What's the root flag?

Answer
```
ezRo0tW1thoutDiD
```
<img width="936" alt="3" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/16549cd9-3931-47b1-b9d1-2cf2ede8dca2">

---

4. What is the error message when you login as tracy again and try sudo -l after its removal from the sudoers group?

Answer
```
Sorry, user tracy may not run sudo on jenkins.
```

To remove user tracy from sudo group

Command:
```
sudo deluser tracy sudo
```
<img width="940" alt="remove tracy" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/612a2e0a-8938-4b0a-af51-8793ae1f6bc1">

Then again login as user tracy:

<img width="939" alt="4" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/28ccb886-6291-468f-8b19-533cc411ce21">

---

5. What's the SSH flag?

Answer
```
Ne3d2SecureTh1sSecureSh31l
```

SSH flag is located in /etc/ssh/sshd_config file.
```
cat /etc/ssh/sshd_config
```

<img width="919" alt="5" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/167d04a4-1baa-433a-9ebd-5c41c47c410a">

---

6. What's the Jenkins flag?

Answer
```
FullTrust_has_n0_Place1nS3cur1ty
```

Jenkis flag is located in ```/var/lib/jenkins/config.xml.bak``` file:
```
cat /var/lib/jenkins/config.xml.bak
```

<img width="935" alt="Screenshot 2024-01-02 at 3 27 46 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/554970c4-b894-4cb0-b084-907afa3cac7d">


---

