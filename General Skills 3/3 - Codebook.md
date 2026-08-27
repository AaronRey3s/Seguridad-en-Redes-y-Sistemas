## Descripción
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)

## Solución
AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2026-08-27 02:44:56--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.64, 3.160.5.95, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py            100%[==============>]   1.25K  --.-KB/s    in 0s      

2026-08-27 02:44:56 (629 MB/s) - 'code.py' saved [1278/1278]

AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2026-08-27 02:45:19--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.64, 3.160.5.95, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt       100%[==============>]      27  --.-KB/s    in 0s      

2026-08-27 02:45:20 (9.05 MB/s) - 'codebook.txt' saved [27/27]

AaronTank5-academy@webshell:~$ python3 code.py
picoCTF{c0d3b00k_455157_197a982c}

## Notas Adicionales
- Algunos scripts al ejecutarse es posible que requieran la existencia de otros archivos para poder trabajar
- nano - es un editor en modo texto de linux y se usa Ctrl x para salir

## Referencias
https://webshell.cylabacademy.org/

