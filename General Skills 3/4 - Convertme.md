## Descripción
Run the Python script and convert the given number from decimal to binary to get the flag.

[Download Python script](https://artifacts.picoctf.net/c/24/convertme.py)

## Solución
AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/24/convertme.py
--2026-08-27 02:48:02--  https://artifacts.picoctf.net/c/24/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.95, 3.160.5.18, 3.160.5.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py       100%[==============>]   1.16K  --.-KB/s    in 0s      

2026-08-27 02:48:02 (758 MB/s) - 'convertme.py' saved [1189/1189]

AaronTank5-academy@webshell:~$ python3 convertne.py
python3: can't open file '/home/AaronTank5-academy/convertne.py': [Errno 2] No such file or directory
AaronTank5-academy@webshell:~$ python3 convertme.py
If 86 is in decimal base, what is it in binary base?
Answer: 1010110
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_722f6b39}

## Notas Adicionales


## Referencias
https://webshell.cylabacademy.org/