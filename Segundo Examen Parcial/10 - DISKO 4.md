## Descripción
Can you find the flag in this disk image? This time I deleted the file! Let see you get it now! Download the disk image [here](https://challenge-files.cylabacademy.net/library/73410159cc8aafa59ec856dcc13ab8b30a50f6827eef6627d3e346bbd3c0085a/disko-4.dd.gz).

1.- How would you look for deleted files?

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-forensics/10-disko-4
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-forensics/10-disko-4
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/10-disko-4$ wget https://challenge-files.cylabacademy.net/library/eb382e7a661cefeb2a260ce85a423ae53331e859032f82b2a8375fe1ce68c2e8/disko-4.dd.gz
--2026-10-31 16:26:46--  https://challenge-files.cylabacademy.net/library/eb382e7a661cefeb2a260ce85a423ae53331e859032f82b2a8375fe1ce68c2e8/disko-4.dd.gz
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.26, 18.238.132.49, 18.238.132.88, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.26]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 20766210 (20M) [application/octet-stream]
Guardando como: ‘disko-4.dd.gz’

disko-4.dd.gz       100%[===================>]  19,80M  1,46MB/s    en 11s     

2026-10-31 16:26:58 (1,79 MB/s) - ‘disko-4.dd.gz’ guardado [20766210/20766210]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/10-disko-4$ gzip -dc disko-4.dd.gz > disko-4.dd
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/10-disko-4$ file disko-4.dd
disko-4.dd: DOS/MBR boot sector, code offset 0x58+2, OEM-ID "mkfs.fat", Media descriptor 0xf8, sectors/track 32, heads 8, sectors 204800 (volumes > 32 MB), FAT (32 bit), sectors/FAT 1576, serial number 0x49838d0b, unlabeled
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/10-disko-4$ fls -r -d -p disko-4.dd > eliminados.txt
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/10-disko-4$ cat eliminados.txt
r/r * 522629:	log/messages
r/r * 532021:	log/dont-delete.gz
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/10-disko-4$ icat -r disko-4.dd 532021 > recuperado.gz
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/10-disko-4$ gzip -dc recuperado.gz
Here is your flag
academy{d3l_d0n7_h1d3_w3ll_d257c742}

## Notas Adicionales
- Eliminar un archivo puede dejar datos recuperables mientras no se sobrescriban.
- `fls -d` muestra entradas eliminadas e `icat -r` aplica técnicas de recuperación.

## Referencias