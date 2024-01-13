# Task 27  [Day 21] DevSecOps Yule be Poisoned: A Pipeline of Insecure Code!

---

Learning Objectives

- Understand how a larger CI/CD environment operates.
- Explore indirect poisoned pipeline execution (PPE) and how it can be used to exploit Git.
- Apply CI/CD exploitation knowledge to the larger CI/CD environment.

---

Navigate to http://machine_ip:3000, the Gitea platform AntarctiCrafts uses for version control and development. Log in using the 
credentials
```
guest:password123
```


<img width="1300" alt="Screenshot 2024-01-13 at 4 30 08 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/e5f99ee3-9cb2-4d48-9906-4494a115c017">

---

When you have logged in successfully, you should see two repositories: gift-wrapper and gift-wrapper-pipeline. Navigate to

http://machine_ip:8080

The Jenkins platform AntarctiCrafts uses for building and automation. Log in using the credentials 
```
admin:admin
```

<img width="1298" alt="Screenshot 2024-01-13 at 4 32 24 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/305c8164-7307-4e31-93ce-9dc58a3eff05">

Once you have logged in successfully, you should see a project: gift-wrapper-build.

---

Now on our local machine: open up the terminal

Clone this repo

<img width="1300" alt="Screenshot 2024-01-13 at 4 36 59 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/680753b2-a7e4-4b1e-8ac5-59ad41c57a31">


```
git clone http://machine_ip:3000/McHoneyBell/gift-wrapper.git
```

---
These are the file in gift-wrapper repo:

<img width="913" alt="Screenshot 2024-01-13 at 4 38 33 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/1b05f647-cd06-45dc-8e6d-69b1d2afca01">

We need to edit Makefile 

**after modification Makefile should look like this**

<img width="934" alt="Screenshot 2024-01-13 at 4 40 09 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/bf0a81b4-42bf-411b-931c-bba8dddf352a">

---
After editing push the repo.

```
git add .
git commit -m "<message here>"
git push
```

***QUESTIONS***

1. What Linux kernel version is the Jenkins node?

ANSWER
```
5.4.0-1029-aws
```

<img width="1044" alt="Screenshot 2024-01-13 at 4 47 55 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/69ac12df-0841-4556-8137-983c21de8450">

---

2. What value is found from /var/lib/jenkins/secret.key?

ANSWER
```
90e748eafdd2af4746a5ef7941e63272f24f1e33a2882f614ebfa6742e772ba7
```
Perform the same procedure to obatain the secret key 

edit Makefile 

<img width="930" alt="Screenshot 2024-01-13 at 4 54 32 PM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/2bb868bd-e887-4aa4-aa60-365ee8742b10">


then push it..

---






