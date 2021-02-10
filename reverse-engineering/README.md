# Reverse Engineering

> Mihai Stanciu | February 11, 2021

## Task 1

* Look through `strings crackme1.bin`

* Found password

```
hax0r
```

## Task 2

* Used `Ghidra` to check out the code

* Found it checking for input to be the hex value `0x7a61` which in decimal is the password

```
4988
```

## Task 3

* Used `gdb` to set a breakpoint at the `cmp` function

* Kept trying letters until found the first 3 letters

```
azt
```