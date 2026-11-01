## Descripción
A new modular challenge! Download the message [here](https://challenge-files.cylabacademy.net/library/4f25bc41d739375d13732691063a72f372cc433988ff76ad620c458a792b5c9e/message.txt).

Take each number mod 41 and find the modular inverse for the result. Then map to the following character set: 1-26 are the alphabet, 27-36 are the decimal digits, and 37 is an underscore.

Wrap your decrypted message in the academy flag format (i.e. `academy{decrypted_message}`)

1.- Do you know what the modular inverse is?

2.- The inverse modulo _z_ of _x_ is the number, _y_ that when multiplied by _x_ is 1 modulo _z_

3.- It's recommended to use a tool to find the modular inverses

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ sudo apt install -y wget python3 python3-pip python3-venv libimage-exiftool-perl xxd openssl
wget ya está en su versión más reciente (1.25.0-2ubuntu4.4).
fijado wget como instalado manualmente.
python3 ya está en su versión más reciente (3.14.3-0ubuntu2).
fijado python3 como instalado manualmente.
libimage-exiftool-perl ya está en su versión más reciente (13.50+dfsg-1).
Actualizando:                   
  libssl3t64  openssl  openssl-provider-legacy  vim-common  vim-tiny  xxd

Instalando:
  python3-pip  python3-venv

Instalando dependencias:
  python3-wheel

Paquetes recomendados:
  python3-dev

Resumen:
  Actualizando: 6, Instalando 3, Eliminando: 0, no actualizando: 235
 Tamaño de la descarga: 1.445 kB / 6.529 kB
  Espacio necesario: 10,5 MB / 21,4 GB disponible

Des:1 http://mx.archive.ubuntu.com/ubuntu resolute/universe amd64 python3-wheel all 0.46.3-2 [27,9 kB]
Des:2 http://mx.archive.ubuntu.com/ubuntu resolute/universe amd64 python3-pip all 25.1.1+dfsg-1ubuntu2 [1.416 kB]
Des:3 http://mx.archive.ubuntu.com/ubuntu resolute/universe amd64 python3-venv amd64 3.14.3-0ubuntu2 [1.032 B]
Descargados 1.445 kB en 10s (141 kB/s)                                         
(Leyendo la base de datos ... 192556 ficheros o directorios instalados actualmen
te.)
Preparando para desempaquetar .../openssl-provider-legacy_3.5.5-1ubuntu3.7_amd64
.deb ...
Desempaquetando openssl-provider-legacy (3.5.5-1ubuntu3.7) sobre (3.5.5-1ubuntu3
.5) ...
Configurando openssl-provider-legacy (3.5.5-1ubuntu3.7) ...
(Leyendo la base de datos ... 192556 ficheros o directorios instalados actualmen
te.)
Preparando para desempaquetar .../libssl3t64_3.5.5-1ubuntu3.7_amd64.deb ...
Desempaquetando libssl3t64:amd64 (3.5.5-1ubuntu3.7) sobre (3.5.5-1ubuntu3.5) ...
Configurando libssl3t64:amd64 (3.5.5-1ubuntu3.7) ...
(Leyendo la base de datos ... 192556 ficheros o directorios instalados actualmen
te.)
Preparando para desempaquetar .../0-openssl_3.5.5-1ubuntu3.7_amd64.deb ...
Desempaquetando openssl (3.5.5-1ubuntu3.7) sobre (3.5.5-1ubuntu3.5) ...
Preparando para desempaquetar .../1-vim-tiny_2%3a9.1.2141-1ubuntu4.9_amd64.deb .
..
Desempaquetando vim-tiny (2:9.1.2141-1ubuntu4.9) sobre (2:9.1.2141-1ubuntu4.8) .
..
Preparando para desempaquetar .../2-vim-common_2%3a9.1.2141-1ubuntu4.9_all.deb .
..
Desempaquetando vim-common (2:9.1.2141-1ubuntu4.9) sobre (2:9.1.2141-1ubuntu4.8)
 ...
Preparando para desempaquetar .../3-xxd_2%3a9.1.2141-1ubuntu4.9_amd64.deb ...
Desempaquetando xxd (2:9.1.2141-1ubuntu4.9) sobre (2:9.1.2141-1ubuntu4.8) ...
Seleccionando el paquete python3-wheel previamente no seleccionado.
Preparando para desempaquetar .../4-python3-wheel_0.46.3-2_all.deb ...
Desempaquetando python3-wheel (0.46.3-2) ...
Seleccionando el paquete python3-pip previamente no seleccionado.
Preparando para desempaquetar .../5-python3-pip_25.1.1+dfsg-1ubuntu2_all.deb ...
Desempaquetando python3-pip (25.1.1+dfsg-1ubuntu2) ...
Seleccionando el paquete python3-venv previamente no seleccionado.
Preparando para desempaquetar .../6-python3-venv_3.14.3-0ubuntu2_amd64.deb ...
Desempaquetando python3-venv (3.14.3-0ubuntu2) ...
Configurando python3-wheel (0.46.3-2) ...
Configurando xxd (2:9.1.2141-1ubuntu4.9) ...
Configurando vim-common (2:9.1.2141-1ubuntu4.9) ...
Configurando python3-venv (3.14.3-0ubuntu2) ...
Configurando python3-pip (25.1.1+dfsg-1ubuntu2) ...
Configurando openssl (3.5.5-1ubuntu3.7) ...
Configurando vim-tiny (2:9.1.2141-1ubuntu4.9) ...
Procesando disparadores para desktop-file-utils (0.28-1build1) ...
Procesando disparadores para hicolor-icon-theme (0.18-2build1) ...
Procesando disparadores para gnome-menus (3.38.1-1ubuntu1) ...
Procesando disparadores para libc-bin (2.43-2ubuntu2.3) ...
Procesando disparadores para man-db (2.13.1-1build1) ...
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-crypto
aaron-tank_3@aaron-tankVirtualBox:~$ python3 -m venv ~/picoctf-crypto/entorno

aaron-tank_3@aaron-tankVirtualBox:~$ 
aaron-tank_3@aaron-tankVirtualBox:~$ source ~/picoctf-crypto/entorno/bin/activate
(entorno) aaron-tank_3@aaron-tankVirtualBox:~$ python3 -m pip install pycryptodome owiener sympy
Collecting pycryptodome
  Downloading pycryptodome-4.2.0-cp39-abi3-manylinux2014_x86_64.manylinux_2_17_x86_64.whl.metadata (6.1 kB)
Collecting owiener
  Downloading owiener-1.0.10.tar.gz (4.7 kB)
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
  Preparing metadata (pyproject.toml) ... done
Collecting sympy
  Downloading sympy-1.14.0-py3-none-any.whl.metadata (12 kB)
Collecting mpmath<1.4,>=1.1.0 (from sympy)
  Downloading mpmath-1.3.0-py3-none-any.whl.metadata (8.6 kB)
Downloading pycryptodome-4.2.0-cp39-abi3-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (3.0 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.0/3.0 MB 256.3 kB/s eta 0:00:00
Downloading sympy-1.14.0-py3-none-any.whl (6.3 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.3/6.3 MB 140.4 kB/s eta 0:00:00
Downloading mpmath-1.3.0-py3-none-any.whl (536 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 536.2/536.2 kB 271.4 kB/s eta 0:00:00
Building wheels for collected packages: owiener
  Building wheel for owiener (pyproject.toml) ... done
  Created wheel for owiener: filename=owiener-1.0.10-py3-none-any.whl size=6103 sha256=af9df698a94957a3e9e0e4241adf5f72545e5815d19aafb9fa7b4807691b03ee
  Stored in directory: /home/aaron-tank_3/.cache/pip/wheels/cb/fc/35/c4b6c1ba7dea5a05b5bdc167a0e93a78ff1c9e8f5817af952b
Successfully built owiener
Installing collected packages: mpmath, sympy, pycryptodome, owiener
Successfully installed mpmath-1.3.0 owiener-1.0.10 pycryptodome-4.2.0 sympy-1.14.0
(entorno) aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-crypto/01-basic-mod2
(entorno) aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-crypto/01-basic-mod2
(entorno) aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/01-basic-mod2$ wget https://challenge-files.cylabacademy.net/library/79ab2df83c3efdaa68f8d1d7b4ce3e478bd49e8193ca7002a30ea460743c412c/message.txt
--2026-10-31 16:42:48--  https://challenge-files.cylabacademy.net/library/79ab2df83c3efdaa68f8d1d7b4ce3e478bd49e8193ca7002a30ea460743c412c/message.txt
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.26, 18.238.132.49, 18.238.132.88, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.26]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 86 [application/octet-stream]
Guardando como: ‘message.txt’

message.txt         100%[===================>]      86  --.-KB/s    en 0s      

2026-10-31 16:42:49 (39,2 MB/s) - ‘message.txt’ guardado [86/86]

(entorno) aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/01-basic-mod2$ cat message.txt
309 44 274 149 57 378 313 311 64 420 405 86 98 195 256 48 238 277 448 411 240 43(entorno) aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/01-basic-mod2$ nano exp.pyexp.py
(entorno) aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/01-basic-mod2$ python3 exp.py

academy{1NV3R53LY_H4RD_FED0A735}
## Notas Adicionales
- Primero se calcula el residuo módulo `41` y después su inverso; ese orden importa.

## Referencias