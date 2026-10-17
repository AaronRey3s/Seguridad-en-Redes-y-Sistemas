## Descripción
Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://challenge-files.cylabacademy.net/library/a454b00812f80f3ffa4115dc27a9eb78fbfcab841218f5502f7f53ab8d5d7f49/flag.png).

## Solución
aron-tank_3@aaron-tankVirtualBox:~$ wget https://challenge-files.cylabacademy.net/library/a454b00812f80f3ffa4115dc27a9eb78fbfcab841218f5502f7f53ab8d5d7f49/flag.png
--2026-10-16 22:02:12--  https://challenge-files.cylabacademy.net/library/a454b00812f80f3ffa4115dc27a9eb78fbfcab841218f5502f7f53ab8d5d7f49/flag.png
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.37, 13.226.187.22, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[13.226.187.40]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 21564 (21K) [application/octet-stream]
Guardando como: ‘flag.png’

flag.png            100%[===================>]  21,06K  --.-KB/s    en 0s      

2026-10-16 22:02:13 (47,3 MB/s) - ‘flag.png’ guardado [21564/21564]

aron-tank_3@aaron-tankVirtualBox:~$ binwalk -e flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
75            0x4B            Zlib compressed data, default compression
15929         0x3E39          Zip archive data, at least v1.0 to extract, name: secret/
15994         0x3E7A          Zip archive data, at least v1.0 to extract, compressed size: 5313, uncompressed size: 5313, name: secret/flag.png

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

aaron-tank_3@aaron-tankVirtualBox:~$ cd _flag.png.extracted
aaron-tank_3@aaron-tankVirtualBox:~/_flag.png.extracted$ ls -R
.:
3E39.zip  4B  4B.zlib  secret

./secret:
flag.png
aaron-tank_3@aaron-tankVirtualBox:~/_flag.png.extracted$ xdg-open secret/flag.png
aaron-tank_3@aaron-tankVirtualBox:~/_flag.png.extracted$ 

aquí me abrió la imagen y en esta imagen venía la flag

## Notas Adicionales


## Referencias


