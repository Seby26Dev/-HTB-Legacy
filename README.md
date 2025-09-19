# -HTB-Legacy


### We start with nmap scan 

```
nmap -p- -sVC --min-rate 5000 -vv -oN nmap_scan 10.10.10.4 
```

<img width="856" height="104" alt="image" src="https://github.com/user-attachments/assets/dcd7865f-c40e-4d78-9fb5-85f35b49665f" />


### After the first scan i make another for scanning smb . And discover a Vulnerability on smb

```
nmap -p- -sVC --min-rate 5000 -vv  10.10.10.4 --script=smb-vuln*
```

<img width="1113" height="847" alt="image" src="https://github.com/user-attachments/assets/ca4afd7a-44fd-40c6-b165-76ef75f9bfc5" />

```
|     IDs:  CVE:CVE-2008-4250    MS08-067
```

### I use searchsploit ot find the vulnerability 

```
searchsploit MS08-067 
```

<img width="1457" height="219" alt="image" src="https://github.com/user-attachments/assets/f7c75492-8c6b-4279-b619-b409edc66f60" />


### We use metasploit for exploiting this vulnerability 


<img width="1447" height="355" alt="image" src="https://github.com/user-attachments/assets/a0f9e3f4-8e5e-4e2f-920b-ed1b99522c8a" />


### And we find the user and root flag 


```
execute -f cmd.exe -i -H
```

Root ->C:\Documents and Settings\Administrator\Desktop 

<img width="529" height="64" alt="image" src="https://github.com/user-attachments/assets/9cac81a7-1e9d-48f7-8a43-b3a66e82d837" />


User -> C:\Documents and Settings\john\Desktop

<img width="475" height="51" alt="image" src="https://github.com/user-attachments/assets/924b5ffd-0d90-4026-94dd-0c3ba5d87f91" />







