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
When you have logged in successfully, you should see two repositories: gift-wrapper and gift-wrapper-pipeline. Navigate to

http://10.10.196.98:8080
T
he Jenkins platform AntarctiCrafts uses for building and automation. Log in using the credentials 
```
admin:admin
```
 Once you have logged in successfully, you should see a project: gift-wrapper-build.
