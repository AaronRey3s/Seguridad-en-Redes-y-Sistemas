## Descripción
1.- Try checking the file’s header.

2.- JPEG

3.- Tools like xxd or hexdump can help you inspect and edit file bytes.

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-forensics/06-corrupted-file
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-forensics/06-corrupted-file
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/06-corrupted-file$ wget https://challenge-files.cylabacademy.net/library/217bef66dcb5fd0797e1c0f064b705a73600a8be2e1ebadeab51df5be013109d/file
--2026-10-31 16:05:23--  https://challenge-files.cylabacademy.net/library/217bef66dcb5fd0797e1c0f064b705a73600a8be2e1ebadeab51df5be013109d/file
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.88, 18.238.132.26, 18.238.132.115, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.88]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 8783 (8,6K) [application/octet-stream]
Guardando como: ‘file’

file                100%[===================>]   8,58K  --.-KB/s    en 0,009s  

2026-10-31 16:05:24 (991 KB/s) - ‘file’ guardado [8783/8783]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/06-corrupted-file$ xxd -l 16 file
00000000: 5c78 ffe0 0010 4a46 4946 0001 0100 0001  \x....JFIF......
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/06-corrupted-file$ cp file reparado.jpg
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/06-corrupted-file$ printf '\xff\xd8' | dd of=reparado.jpg bs=1 seek=0 conv=notrunc status=none
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/06-corrupted-file$ file reparado.jpg
reparado.jpg: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 800x500, components 3
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/06-corrupted-file$ xdg-open reparado.jpg
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/06-corrupted-file$ 


academy{r3st0r1ng_th3_by73s_3908f978}
## Notas Adicionales
- Cambiar la extensión no corrige una cabecera dañada.
- La reparación se realiza sobre una copia y conserva el original.

## Referencias