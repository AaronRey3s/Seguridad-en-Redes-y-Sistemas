## Descripción
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://challenge-files.cylabacademy.net/library/c585b4adbdaa06f409db7bf5012c2e58e9aab24669764a5f1cf0f9ce0d60dcfd/cat.jpg)

## Solución
aron-tank_3@aaron-tankVirtualBox:~$ wget https://challenge-files.cylabacademy.net/library/c585b4adbdaa06f409db7bf5012c2e58e9aab24669764a5f1cf0f9ce0d60dcfd/cat.jpg
--2026-10-16 21:30:26--  https://challenge-files.cylabacademy.net/library/c585b4adbdaa06f409db7bf5012c2e58e9aab24669764a5f1cf0f9ce0d60dcfd/cat.jpg
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.66, 13.226.187.22, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[13.226.187.40]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 878136 (858K) [application/octet-stream]
Guardando como: ‘cat.jpg’

cat.jpg             100%[===================>] 857,55K  5,07MB/s    en 0,2s    

2026-10-16 21:30:27 (5,07 MB/s) - ‘cat.jpg’ guardado [878136/878136]

aaron-tank_3@aaron-tankVirtualBox:~$ exiftool cat.jpg
ExifTool Version Number         : 13.50
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2026:09:22 20:44:41-06:00
File Access Date/Time           : 2026:10:16 21:30:27-06:00
File Inode Change Date/Time     : 2026:10:16 21:30:27-06:00
File Permissions                : -rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 13.25
License                         : YWNhZGVteXt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
aaron-tank_3@aaron-tankVirtualBox:~$ echo "YWNhZGVteXt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 -d
academy{the_m3tadata_1s_modified}

## Notas Adicionales


## Referencias


