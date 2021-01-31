# Ice Windows

> Mihai Stanciu | 30 January 2021

```
export ip=10.10.11.56
```

## Nmap scan is in the `nmap` folder

### Ports for `initial` scan

```
135, 139, 3389, 5357, 8000
```

## Running metasploit (`msfconsole`)

Using the `exploit/windows/http/icecast_header` exploit

Finding possible exploits `run post/multi/recon/local_exploit_suggester`

Chose first recommended exploit and gained admin privelages