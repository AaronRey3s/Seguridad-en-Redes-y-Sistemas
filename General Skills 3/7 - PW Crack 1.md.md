## Descripción
Can you crack the password to get the flag?

Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

## Solución
AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.py
--2026-08-27 03:51:12--  https://artifacts.picoctf.net/c/10/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.40, 3.160.5.95, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py          100%[==============>]     876  --.-KB/s    in 0s      

2026-08-27 03:51:12 (42.7 MB/s) - 'level1.py' saved [876/876]

AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
--2026-08-27 03:51:33--  https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.40, 3.160.5.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.en 100%[==============>]      30  --.-KB/s    in 0s      

2026-08-27 03:51:33 (2.11 MB/s) - 'level1.flag.txt.enc' saved [30/30]

AaronTank5-academy@webshell:~$ ls
Addadshashanammu      dec3                 level1.py
Addadshashanammu.zip  dec4                 ltdis.sh
README.txt            dec5                 ltdis.sh.1
]                     dec6                 runme.py
big-zip-files         enc_flag             static
big-zip-files.zip     files                static.1
code.py               files.zip            static.2
codebook.txt          fixme1.py            static.ltdis.strings.txt
convertme.py          fixme2.py            static.ltdis.x86_64.txt
dec1                  l                    strings
dec2                  level1.flag.txt.enc  warm
AaronTank5-academy@webshell:~$ nano level1.py
AaronTank5-academy@webshell:~$ python3 level1.py
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
AaronTank5-academy@webshell:~$ 

## Notas Adicionales


## Referencias
https://webshell.cylabacademy.org/

