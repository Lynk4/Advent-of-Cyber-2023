# Task 22  [Day 16] Machine learning Can't CAPTCHA this Machine!

---
Learning Objectives

- Complex neural network structures
- How does a convolutional neural networks function?
- Using neural networks for optical character recognition
- Integrating neural networks into red team tooling

So After the machine is up Follow this way.

open up the terminal.

---

<img width="1440" alt="Screenshot 2024-01-06 at 4 26 47 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/10c32824-dcb4-4ffb-9cf1-acd1489d2d1e">

---

After completing above task: 

Directly go to Hosting Our CNN Model section of THM. and follow the steps in the below image.

---

<img width="1440" alt="Screenshot 2024-01-06 at 4 28 28 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/2f96effc-f9e6-4c7d-90cd-0c332691fb78">

---

After killing the container:

Run another docker container:

---

<img width="1440" alt="Screenshot 2024-01-06 at 4 30 06 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/3f87362e-fd5d-42fd-bdfb-034c625650f8">

---

Now it's time to brute force  ```http://hqadmin.thm:8000/``` admin panel

For that open up a new terminal and paste the following command:

---
<img width="1440" alt="Screenshot 2024-01-06 at 4 32 02 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/73cfda0c-b2e3-40d8-97f4-3a74c6eda81c">

---

After one minute you get the id and password:

---

<img width="1440" alt="Screenshot 2024-01-06 at 4 32 17 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/6b2999a2-78e6-4f19-ac55-08f63eda733d">

---

***USERNAME***
```
admin
```

***PASSWORD***
```
ReallyNotGonnaGuessThis
```

Now go to ```http://hqadmin.thm:8000/ ``` and login to get your flag:

---

<img width="1440" alt="Screenshot 2024-01-06 at 4 35 11 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/783a43d2-97a0-4cc5-b3e8-fca5c3fcf277">

---

<img width="1440" alt="Screenshot 2024-01-06 at 4 35 58 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/c9fb8e48-af6a-45f4-81cd-2fbeb20898b0">

---

QUESTIONS:

1. What key process of training a neural network is taken care of by using a CNN?

ANSWER
```
Feature Extraction
```

2. What is the name of the process used in the CNN to extract the features?

ANSWER
```
Convolution
```

3. What is the name of the process used to reduce the features down?

ANSWER
```
Pooling
```

4. What off-the-shelf CNN did we use to train a CAPTCHA-cracking OCR model?

ANSWER
```
Attention OCR
```

5. What is the password that McGreedy set on the HQ Admin portal?

ANSWER
```
ReallyNotGonnaGuessThis
```

6. What is the value of the flag that you receive when you successfully authenticate to the HQ Admin portal?

ANSWER
```
THM{Captcha.Can't.Hold.Me.Back}
```

---

