## Descripción
Download this image file and find the flag.

- [Download image file](https://challenge-files.cylabacademy.net/library/248587d9a868db74a285623697f78ef3d87561aaa16ff1fb211fe88cd72f4a6c/drawing.flag.svg)

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-forensics/02-enhance
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-forensics/02-enhance
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/02-enhance$ wget https://challenge-files.cylabacademy.net/library/83bfcd323363337f297f4d4ee3bff06df8564155aa2037148151710fa8baec04/drawing.flag.svg
--2026-10-31 15:38:05--  https://challenge-files.cylabacademy.net/library/83bfcd323363337f297f4d4ee3bff06df8564155aa2037148151710fa8baec04/drawing.flag.svg
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.49, 18.238.132.26, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.115]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 4149 (4,1K) [application/octet-stream]
Guardando como: ‘drawing.flag.svg’

drawing.flag.svg    100%[===================>]   4,05K  --.-KB/s    en 0,005s  

2026-10-31 15:38:05 (850 KB/s) - ‘drawing.flag.svg’ guardado [4149/4149]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-forensics/02-enhance$ grep -oP '(?<=>)[^<>]+(?=</tspan>)' drawing.flag.svg | tr -d '[:space:]'
academy{3nh4nc3d_5b5e6f18}

## Notas Adicionales
- Un SVG puede conservar texto legible en su XML aunque aparezca diminuto en el visor. Este patrón funciona con las etiquetas repartidas en varias líneas del archivo proporcionado.

## Referencias