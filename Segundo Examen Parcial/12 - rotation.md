## Descripción
You will find the flag after decrypting this file Download the encrypted flag [here](https://challenge-files.cylabacademy.net/library/ee237b7e28b6b3871ce9d37f01093b13c190138d2be22fcae22865975e362c1f/encrypted.txt)

## Solución
aron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-crypto/02-rotation
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-crypto/02-rotation
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/02-rotation$ wget -O encrypted.txt https://challenge-files.cylabacademy.net/library/ee237b7e28b6b3871ce9d37f01093b13c190138d2be22fcae22865975e362c1f/encrypted.txt
--2026-10-31 16:51:25--  https://challenge-files.cylabacademy.net/library/ee237b7e28b6b3871ce9d37f01093b13c190138d2be22fcae22865975e362c1f/encrypted.txt
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.88, 18.238.132.26, 18.238.132.49, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.88]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 37 [application/octet-stream]
Guardando como: ‘encrypted.txt’

encrypted.txt       100%[===================>]      37  --.-KB/s    en 0s      

2026-10-31 16:51:26 (31,2 MB/s) - ‘encrypted.txt’ guardado [37/37]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/02-rotation$ cat encrypted.txt
ikilmug{z0bib1wv_l3kzgxb3l_76m5m998}
academy{r0tat1on_d3crypt3d_76e5e998}

## Notas Adicionales


## Referencias