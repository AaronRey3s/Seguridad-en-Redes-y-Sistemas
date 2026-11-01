## Descripción
This file doesn't look like much... just a bunch of 1s and 0s. But maybe it's not just random noise. Can you recover anything meaningful from this? Download the file [here](https://challenge-files.cylabacademy.net/library/6ba8983da0e17a2e2015a530788849e9c9c0bc3393d62fa3f9a06ce8068567c8/digits.bin).

## Solución
aron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-forensics/07-binary-digits
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-forensics/07-binary-digits
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/07-binary-digits$ wget https://challenge-files.cylabacademy.net/library/4f119c7324ffc27875b984a1d0db0591c4214fa81bd566946f1d08ed29f35135/digits.bin
--2026-10-31 16:12:01--  https://challenge-files.cylabacademy.net/library/4f119c7324ffc27875b984a1d0db0591c4214fa81bd566946f1d08ed29f35135/digits.bin
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.26, 18.238.132.49, 18.238.132.88, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.26]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 71312 (70K) [application/octet-stream]
Guardando como: ‘digits.bin’

digits.bin          100%[===================>]  69,64K  --.-KB/s    en 0,09s   

2026-10-31 16:12:01 (818 KB/s) - ‘digits.bin’ guardado [71312/71312]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/07-binary-digits$ nano exp.py
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/07-binary-digits$ python3 exp.py
Creado recuperado.jpg: 8914 bytes
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/07-binary-digits$ file recuperado.jpg
recuperado.jpg: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 800x500, components 3
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/07-binary-digits$ xdg-open recuperado.jpg
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/07-binary-digits$ 

academy{h1dd3n_1n_th3_b1n4ry_75fdfb71}

## Notas Adicionales
- Contiene **71 744 dígitos**, que representan **71 744 ÷ 8 = 8 968 bytes**. Los bytes recuperados forman un JPEG.

## Referencias