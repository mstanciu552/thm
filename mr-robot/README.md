# Mr. Robot CTF

> Mihai Stanciu | 30 January 2021

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