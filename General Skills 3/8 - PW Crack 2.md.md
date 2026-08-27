## Descripción
Can you crack the password to get the flag?

Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

## Solución
AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.py
--2026-08-27 03:57:26--  https://artifacts.picoctf.net/c/13/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.64, 3.160.5.40, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py          100%[==============>]     914  --.-KB/s    in 0s      

2026-08-27 03:57:26 (39.7 MB/s) - 'level2.py' saved [914/914]

AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
--2026-08-27 03:57:43--  https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.40, 3.160.5.18, 3.160.5.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.en 100%[==============>]      31  --.-KB/s    in 0s      

2026-08-27 03:57:43 (23.6 MB/s) - 'level2.flag.txt.enc' saved [31/31]

AaronTank5-academy@webshell:~$ ls
Addadshashanammu      dec4                 level2.py
Addadshashanammu.zip  dec5                 ltdis.sh
README.txt            dec6                 ltdis.sh.1
]                     enc_flag             runme.py
big-zip-files         files                static
big-zip-files.zip     files.zip            static.1
code.py               fixme1.py            static.2
codebook.txt          fixme2.py            static.ltdis.strings.txt
convertme.py          l                    static.ltdis.x86_64.txt
dec1                  level1.flag.txt.enc  strings
dec2                  level1.py            warm
dec3                  level2.flag.txt.enc
AaronTank5-academy@webshell:~$ nano level2.py
AaronTank5-academy@webshell:~$ de76
-bash: de76: command not found
AaronTank5-academy@webshell:~$ python3 level2.py
Please enter correct password for flag: de76    
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
AaronTank5-academy@webshell:~$ 

## Notas Adicionales


## Referencias
https://webshell.cylabacademy.org/
