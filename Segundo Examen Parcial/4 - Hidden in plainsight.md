## Descripción
You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag. Download the jpg image [here](https://challenge-files.cylabacademy.net/library/6618af1eb2daf007cb7b54d1213093d4dd2801941619b236580ebe3b738dea7b/img.jpg).

1.- Download the jpg image and read its metadata

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-forensics/04-hidden-in-plainsight
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-forensics/04-hidden-in-plainsight
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/04-hidden-in-plainsight$ wget
wget: falta la URL
Uso: wget [OPCIÓN]... [URL]...

Intente «wget --help» para tener más opciones.
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/04-hidden-in-plainsight$ wget https://challenge-files.cylabacademy.net/library/364c5c391edaf4ab3da852e0fc51a5285bc4a570900618b112c52805fc1d5c14/img.jpg
--2026-10-31 15:42:00--  https://challenge-files.cylabacademy.net/library/364c5c391edaf4ab3da852e0fc51a5285bc4a570900618b112c52805fc1d5c14/img.jpg
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.49, 18.238.132.115, 18.238.132.88, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.49]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 73505 (72K) [application/octet-stream]
Guardando como: ‘img.jpg’

img.jpg             100%[===================>]  71,78K  --.-KB/s    en 0,07s   

2026-10-31 15:42:01 (1,03 MB/s) - ‘img.jpg’ guardado [73505/73505]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/04-hidden-in-plainsight$ pista=$(exiftool -s3 -Comment img.jpg | base64 --decode)
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/04-hidden-in-plainsight$ printf '%s\n' "$pista"
steghide:cEF6endvcmQ=
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/04-hidden-in-plainsight$ clave=$(printf '%s' "${pista#*:}" | base64 --decode)
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/04-hidden-in-plainsight$ steghide extract -sf img.jpg -xf recuperado.txt -p "$clave"
anot� los datos extra�dos e/"recuperado.txt".
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/04-hidden-in-plainsight$ cat recuperado.txt
academy{h1dd3n_1n_1m4g3_45cfe9c1}
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/04-hidden-in-plainsight$ 



## Notas Adicionales
- Los metadatos contienen la pista para extraer otro archivo incrustado. No fue necesario probar contraseñas.

## Referencias