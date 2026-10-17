## Descripción
How about some hide and seek?

Download this file [here](https://challenge-files.cylabacademy.net/library/26d33b97d1745fc99c1cf94e3783a3dc963b8b667ca6960ebfce48aa9909251c/unknown.zip).

## Solución
aron-tank_3@aaron-tankVirtualBox:~$ wget https://challenge-files.cylabacademy.net/library/26d33b97d1745fc99c1cf94e3783a3dc963b8b667ca6960ebfce48aa9909251c/unknown.zip
--2026-10-17 08:23:05--  https://challenge-files.cylabacademy.net/library/26d33b97d1745fc99c1cf94e3783a3dc963b8b667ca6960ebfce48aa9909251c/unknown.zip
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.22, 13.226.187.66, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[13.226.187.37]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 2252242 (2,1M) [application/octet-stream]
Guardando como: ‘unknown.zip’

unknown.zip         100%[===================>]   2,15M  1,03MB/s    en 2,1s    

2026-10-17 08:23:08 (1,03 MB/s) - ‘unknown.zip’ guardado [2252242/2252242]
aaron-tank_3@aaron-tankVirtualBox:~$ unzip unknown.zip
Archive:  unknown.zip
  inflating: ukn_reality.jpg     
  aaron-tank_3@aaron-tankVirtualBox:~$ exiftool ukn_reality.jpg
ExifTool Version Number         : 13.50
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2026:09:22 23:17:42-06:00
File Access Date/Time           : 2026:09:22 23:17:42-06:00
File Inode Change Date/Time     : 2026:10:17 08:27:33-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 12.76
Attribution URL                 : YWNhZGVteXtNRTc0RDQ3QV9ISUREM05fYWViZThjMGZ9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4
aaron-tank_3@aaron-tankVirtualBox:~$ echo "YWNhZGVteXtNRTc0RDQ3QV9ISUREM05fYWViZThjMGZ9Cg==" | base64 -d
academy{ME74D47A_HIDD3N_aebe8c0f}
aaron-tank_3@aaron-tankVirtualBox:~$ 



## Notas Adicionales


## Referencias


