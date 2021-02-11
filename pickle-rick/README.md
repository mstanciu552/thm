# Pickle Rick

> Mihai Stanciu | February 11, 2021

## Found ports `22, 80` with `nmap`

### Looked through HTML

* Found comment with username: `R1ckRul3s`

* Found `Wubbalubbadubdub` at `/robots.txt`

* `R1ckRul3s:Wubbalubbadubdub` user for the `login.php` page

## Task 1

* After login found a command line form

* `cat` does not work so we are using `less`

* Found first ingredient in `/var/www/html`

```
mr. meeseek hair
```

## Task 2

* Found out user `www-data` can run `sudo`

* Found second ingredient with `sudo less /home/rick/"second ingredients"`

```
1 jerry tear
```

## Task 3

* Ran `sudo ls /root` and found a `3rd.txt` file

* Displayed it with `sudo less /root/3rd.txt`

```
fleeb juice
```