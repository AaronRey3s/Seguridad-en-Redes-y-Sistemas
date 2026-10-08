
## Descripción
Download this disk image and find the flag.

Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://challenge-files.cylabacademy.net/library/699d021acdedf3ce7c6944b6f3e16046a82b3a1f7ee2e79716132292ce4adbbd/disk.flag.img.gz)

## Solución
aron-tank_3@aaron-tankVirtualBox:~$ wget https://challenge-files.cylabacademy.net/library/699d021acdedf3ce7c6944b6f3e16046a82b3a1f7ee2e79716132292ce4adbbd/disk.flag.img.gz
--2026-10-07 21:06:10--  https://challenge-files.cylabacademy.net/library/699d021acdedf3ce7c6944b6f3e16046a82b3a1f7ee2e79716132292ce4adbbd/disk.flag.img.gz
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.66, 13.226.187.37, 13.226.187.22, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[13.226.187.66]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 47534527 (45M) [application/octet-stream]
Guardando como: ‘disk.flag.img.gz’

disk.flag.img.gz    100%[===================>]  45,33M  9,90MB/s    en 5,6s    

2026-10-07 21:06:17 (8,14 MB/s) - ‘disk.flag.img.gz’ guardado [47534527/47534527]

aaron-tank_3@aaron-tankVirtualBox:~$ gzip -d disk.flag.img.gz

aron-tank_3@aaron-tankVirtualBox:~$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
aaron-tank_3@aaron-tankVirtualBox:~$ fls -r -o 360448 disk.flag.img | grep -i flag 
++ r/r * 2082(realloc):	flag.txt
++ r/r 2371:	flag.uni.txt

aaron-tank_3@aaron-tankVirtualBox:~$ icat -o 360448 disk.flag.img 2371
academy{by73_5urf3r_6395be48}


## Notas Adicionales


## Referencias





