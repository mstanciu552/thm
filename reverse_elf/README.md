# Reverse ELF

> Mihai Stanciu | February 10, 2021

## Task 1

* Simply run the ELF

```
flag{not_that_kind_of_elf}
```

## Task 2

* Look through `strings crackme2`

* Got password `super_secret_password`

```
flag{if_i_submit_this_flag_then_i_will_get_points}
```

## Task 3

* Look through `strings crackme3`

* Found `base64` encoding `ZjByX3kwdXJfNWVjMG5kX2xlNTVvbl91bmJhc2U2NF80bGxfN2gzXzdoMW5nNQ==`

```
f0r_y0ur_5ec0nd_le55on_unbase64_4ll_7h3_7h1ng5
```
## Task 4

* Using `gdb`

1. `info functions` - found function `strcmp@plt`
2. `b *0x0000000000400520` - set breakpoint at that function
3. `run crackme4` - ran the binary
4. `info registers` - to look at registers after hitting the breakpoint
5. `x/s 0x7fffffffe380` - checking what's inside `rax`
6. Found password

```
my_m0r3_secur3_pwd
```

## Task 5

* Same process as **Task 4**

```
OfdlDSA|3tXb32~X3tX@sX`4tXtz
```

## Task 6

* Used `Ghidra` to look through the code

* Found nested `if` statements

* Composed the password from them

```
1337_pwd0
```

## Task 7

* Used `Ghidra` to check out the code

* Found `if` statement checking to see if the input is the decimal value of `0x7a69` whick is `31337` -> used `printf $((0x7a69))`

```
flag{much_reversing_very_ida_wow}
```

## Task 8

* Used `Ghidra`

* Saw `if` statement that checked wether or not the param was equal to the decimal value of `-0x35010ff3` (`-889262067`)

* Got the flag back


```
flag{at_least_this_cafe_wont_leak_your_credit_card_numbers}
```