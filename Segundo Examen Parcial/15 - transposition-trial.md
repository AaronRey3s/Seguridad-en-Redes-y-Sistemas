## Descripción
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://challenge-files.cylabacademy.net/library/304dc08e455ad3c33cf532bb41f44a7e939e8e2ad161d9c9012b8375dee48829/message.txt).

1.- Split the message up into blocks of 3 and see how the first block is scrambled

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-crypto/05-transposition-trial
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-crypto/05-transposition-trial
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/05-transposition-trial$ wget -O message.txt 'https://challenge-files.cylabacademy.net/library/304dc08e455ad3c33cf532bb41f44a7e939e8e2ad161d9c9012b8375dee48829/message.txt'
--2026-10-31 17:21:26--  https://challenge-files.cylabacademy.net/library/304dc08e455ad3c33cf532bb41f44a7e939e8e2ad161d9c9012b8375dee48829/message.txt
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.88, 18.238.132.115, 18.238.132.49, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.88]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 54 [application/octet-stream]
Guardando como: ‘message.txt’

message.txt         100%[===================>]      54  --.-KB/s    en 0s      

2026-10-31 17:21:27 (41,1 MB/s) - ‘message.txt’ guardado [54/54]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/05-transposition-trial$ cat message.txt
heTfl g as icaaemd{7y4NRP051N5_16_35P3X51N3_V1CCA2B2}Aaaron-tank_3@aaron-tankVirnano exp.py
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/05-transposition-trial$ python3 exp.py

academy{7R4N5P051N6_15_3XP3N51V3_C1CBA2A2}

## Notas Adicionales


## Referencias