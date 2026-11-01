## Descripción
The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log. Download the encoded data here: [Logs Data](https://challenge-files.cylabacademy.net/library/e6fc51b98dd61381c5cd54dc836c8344fb475f17728f2095969e3a0f401ea195/logs.txt). Be prepared—the file is large, and examining it thoroughly is crucial .

1.- Use `base64` to decode the data and generate the image file.

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-forensics/05-flag-in-flame
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-forensics/05-flag-in-flame
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/05-flag-in-flame$ wget https://challenge-files.cylabacademy.net/library/ad9f6c5d3cb51fb2e93e1f082064d16373daecd3fb37e05650e5a530179ccf68/logs.txt
--2026-10-31 15:49:17--  https://challenge-files.cylabacademy.net/library/ad9f6c5d3cb51fb2e93e1f082064d16373daecd3fb37e05650e5a530179ccf68/logs.txt
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.49, 18.238.132.88, 18.238.132.115, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.49]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1591896 (1,5M) [application/octet-stream]
Guardando como: ‘logs.txt’

logs.txt            100%[===================>]   1,52M  1,25MB/s    en 1,2s    

2026-10-31 15:49:19 (1,25 MB/s) - ‘logs.txt’ guardado [1591896/1591896]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/05-flag-in-flame$ base64 --decode logs.txt > flame.png
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/05-flag-in-flame$ file flame.png
flame.png: PNG image data, 896 x 1152, 8-bit/color RGB, non-interlaced
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/05-flag-in-flame$ xdg-open flame.png
academy{forensics_analysis_is_amazing_abe1d6ba}

## Notas Adicionales
- Hay dos capas: Base64 recupera el PNG y el hexadecimal de la imagen recupera la bandera.

## Referencias