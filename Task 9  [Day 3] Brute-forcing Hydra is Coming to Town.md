# Brute-forcing Hydra is Coming to Town

---

### Learning Objectives
After completing this task, you will understand:

Password complexity and the number of possible combinations
How the number of possible combinations affects the feasibility of brute force attacks
Generating password combinations using crunch
Trying out passwords automatically using hydra

---

After the machine is up go to http://machine_ip:8000/login.php

You will be prompted like this:

<img width="1303" alt="Screenshot 2023-12-22 at 1 36 47 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/4c294cb3-7854-4826-9194-fdd4f5e789e5">

---

So basically we need to bruteforce the pin.

for that we need a passwordlist.

TO Generating the Password List. We will use crunch

command: ```crunch 3 3 0123456789ABCDEF -o 3digits.txt```



