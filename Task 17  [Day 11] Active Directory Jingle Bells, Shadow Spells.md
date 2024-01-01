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

