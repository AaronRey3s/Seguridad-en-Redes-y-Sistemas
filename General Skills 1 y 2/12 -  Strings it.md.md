## Descripción
Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/285538e2710605958a055500d6573657fcafea6308545cecfabb34462199cfd5/strings) without running it?

## Solución
AaronTank5-academy@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/563d66bbed3925c75ed71efa974bfafab26460ae99938d699a8881cd173fca60/strings
--2026-08-25 02:24:41--  https://challenge-files.picoctf.net/c_fickle_tempest/563d66bbed3925c75ed71efa974bfafab26460ae99938d699a8881cd173fca60/strings
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.64, 3.160.5.40, 3.160.5.95, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 784424 (766K) [application/octet-stream]
Saving to: 'strings'

strings            100%[==============>] 766.04K  1.83MB/s    in 0.4s    

2026-08-25 02:24:42 (1.83 MB/s) - 'strings' saved [784424/784424]

AaronTank5-academy@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_dB2CEA76}

## Notas Adicionales
Strings muestra las caenas (caracteres imprimibles) en un archivo binario (no texto)

## Referencias
https://webshell.cylabacademy.org/


