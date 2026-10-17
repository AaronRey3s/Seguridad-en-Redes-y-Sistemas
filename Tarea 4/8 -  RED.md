## Descripción
RED, RED, RED, RED Download the image: [red.png](https://challenge-files.cylabacademy.net/library/fefcf06050d98347e1585e5cb9f2940967f82e0b89c591966473c752de9f3aba/red.png)

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ wget https://challenge-files.cylabacademy.net/library/fefcf06050d98347e1585e5cb9f2940967f82e0b89c591966473c752de9f3aba/red.png
--2026-10-17 08:33:47--  https://challenge-files.cylabacademy.net/library/fefcf06050d98347e1585e5cb9f2940967f82e0b89c591966473c752de9f3aba/red.png
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.22, 13.226.187.66, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[13.226.187.37]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 792 [application/octet-stream]
Guardando como: ‘red.png’

red.png             100%[===================>]     792  --.-KB/s    en 0s      

2026-10-17 08:33:48 (6,97 MB/s) - ‘red.png’ guardado [792/792]

aaron-tank_3@aaron-tankVirtualBox:~$ zsteg -a red.png | grep -i "academy"
  
aaron-tank_3@aaron-tankVirtualBox:~$ 
aaron-tank_3@aaron-tankVirtualBox:~$ strings red.png | grep "academy{"
aaron-tank_3@aaron-tankVirtualBox:~$ xdg-open red.png
aaron-tank_3@aaron-tankVirtualBox:~$ exiftool red.png
ExifTool Version Number         : 13.50
File Name                       : red.png
Directory                       : .
File Size                       : 792 bytes
File Modification Date/Time     : 2026:09:22 23:36:01-06:00
File Access Date/Time           : 2026:10:17 08:34:17-06:00
File Inode Change Date/Time     : 2026:10:17 08:33:48-06:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 128
Image Height                    : 128
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Poem                            : Crimson heart, vibrant and bold,.Hearts flutter at your sight..Evenings glow softly red,.Cherries burst with sweet life..Kisses linger with your warmth..Love deep as merlot..Scarlet leaves falling softly,.Bold in every stroke.
Image Size                      : 128x128
Megapixels                      : 0.016
aaron-tank_3@aaron-tankVirtualBox:~$ zsteg -e "r1,lsb,bY,prime" red.png
/var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:228:in `block in decode_param_string': uknown param "r1" (RuntimeError)
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:208:in `each'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:208:in `decode_param_string'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:259:in `_extract_data'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:273:in `extract'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:170:in `block (2 levels) in run'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:168:in `each'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:168:in `block in run'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:161:in `each'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:161:in `each_with_index'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg/cli/cli.rb:161:in `run'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
	from /usr/local/bin/zsteg:25:in `load'
	from /usr/local/bin/zsteg:25:in `<main>'
aaron-tank_3@aaron-tankVirtualBox:~$ zsteg red.png
meta Poem           .. text: "Crimson heart, vibrant and bold,\nHearts flutter at your sight.\nEvenings glow softly red,\nCherries burst with sweet life.\nKisses linger with your warmth.\nLove deep as merlot.\nScarlet leaves falling softly,\nBold in every stroke."
chunk:0:IHDR        .. file: Adobe Photoshop Color swatch, version 0, 128 colors; 1st RGB space (0), w 0x80, x 0x806, y 0, z 0; 2nd HSB space (1), w 0, x 0xff, y 0xff01, z 0x1
b1,rgba,lsb,xy      .. text: "YWNhZGVteXtyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==YWNhZGVteXtyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==YWNhZGVteXtyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==YWNhZGVteXtyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="
b1,rgba,msb,xy      .. file: OpenPGP Public Key
b1,abgr,msb,xy      .. file: OpenPGP Secret Key
b2,g,lsb,xy         .. text: "ETEUTTPETUUT@TUUTD@PDUDDDPE"
b2,rgba,msb,xy      .. text: "CIkiiiII"
b2,abgr,lsb,xy      .. file: OpenPGP Public Key
b2,abgr,msb,xy      .. text: "akcikaicc"
b3,a,lsb,xy         .. file: MPEG ADTS, layer II, v1, 224 kbps, 48 kHz, Monaural
b3,bgr,lsb,xy       .. file: PDP-11 executable not stripped - version 56
b3,rgba,msb,xy      .. text: "#vr#w`#~p#6"
b3,abgr,msb,xy      .. text: "7r'7p#wp"
b4,b,lsb,xy         .. file: raw G3 (Group 3) FAX, byte-padded
aaron-tank_3@aaron-tankVirtualBox:~$ echo "YWNhZGVteXtyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==" | base64 -d
academy{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}

## Notas Adicionales


## Referencias


