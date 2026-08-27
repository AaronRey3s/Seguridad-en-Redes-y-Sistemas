## Descripción
Can you crack the password to get the flag?

Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too.

There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solución
AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.py
--2026-08-27 04:03:03--  https://artifacts.picoctf.net/c/16/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.40, 3.160.5.18, 3.160.5.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py          100%[==============>]   1.31K  --.-KB/s    in 0.001s  

2026-08-27 04:03:03 (1.30 MB/s) - 'level3.py' saved [1337/1337]

AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
--2026-08-27 04:03:17--  https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.64, 3.160.5.18, 3.160.5.95, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.en 100%[==============>]      31  --.-KB/s    in 0s      

2026-08-27 04:03:17 (16.5 MB/s) - 'level3.flag.txt.enc' saved [31/31]

AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.hash.bin
--2026-08-27 04:05:05--  https://artifacts.picoctf.net/c/16/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.95, 3.160.5.40, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin    100%[==============>]      16  --.-KB/s    in 0s      

2026-08-27 04:05:05 (12.3 MB/s) - 'level3.hash.bin' saved [16/16]

AaronTank5-academy@webshell:~$ tail level3.py



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]

AaronTank5-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: 6997 
That password is incorrect
AaronTank5-academy@webshell:~$ 865e
-bash: 865e: command not found
AaronTank5-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: 865e
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
AaronTank5-academy@webshell:~$ 

## Notas Adicionales


## Referencias
https://webshell.cylabacademy.org/

