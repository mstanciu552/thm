# CTF Collection - Vol. 1

> Mihai Stanciu | February 04, 2021

## Task 2

* Can you decode the following?

VEhNe2p1NTdfZDNjMGQzXzdoM19iNDUzfQ==

* Decoded via `base64` to

```
THM{ju57_d3c0d3_7h3_b453}
``` 
## Task 3

* Used `exiftool` on image

```
THM{3x1f_0r_3x17}
```

## Task 4

* Used `steghide extract -sf Exploration.png` _without a password_

```
THM{500n3r_0r_l473r_17_15_0ur_7urn}
```

## Task 5

* Checked the HTML and found white colored text

```
THM{wh173_fl46}
```

## Task 6

* Checked the QR code online

```
THM{qr_m4k3_l1f3_345y}
```

## Task 7

* Reading through the output of `hexdump` found the flag

```
THM{345y_f1nd_345y_60}
```

## Task 8

* Tried decoding `3agrSy1CewF9v8ukcSkPSYm3oKUoByUpKG4L` with **base58**

```
THM{17_h45_l3553r_l3773r5}
```

## Task 9

* Counted the alphabetical difference between _T_ and _M_ which was 19

* Decoded with RO19

```
THM{hail_the_caesar}
``` 

## Task 10 

* Found the flag in an HTML comment

```
THM{4lw4y5_ch3ck_7h3_c0m3mn7}
```

## Task 11

## Task 12

## Task 13

* Identified as _brainf*ck_ programming language

* Compiled to flag with python module **brainf**

* `python3 -m brainf <filename.b>`

```
THM{0h_my_h34d}
```

## Task 14

## Task 15

* Ran `binwalk -e <filename>`

```
THM{y0u_w4lk_m3_0u7}
```

## Task 16

* Used `stegsolve`


```
THM{7h3r3_15_h0p3_1n_7h3_d4rkn355}
```

## Task 17

## Task 18

* Used the [Wayback Machine](https://web.archive.org/)

```
THM{ch3ck_th3_h4ckb4ck}
```

## Task 19

## Task 20

* Converted `581695969015253365094191591547859387620042736036246486373595515576333693` from _decimal_ to _hex_

* Converted the _hex_ to _ASCII_ which resulted in the flag

```
THM{17_ju57_4n_0rd1n4ry_b4535}
```

## Task 21

* Opened `flag.pcapng` with `wireshark`

* Found an **HTTP** request to a `/flag.txt` link

* Found the flag in the response

```
THM{d0_n07_574lk_m3}
```



