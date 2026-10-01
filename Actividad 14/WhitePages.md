## Descripción
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.picoctf.net/c_fickle_tempest/f35d2be8de731d412d3dbd8c79e6c5b32c62efbb124cf319f54ebddf76ea0ffe/whitepages.txt) is all blank!

## Solución
aron-tank_3@aaron-tankVirtualBox:~/moonwalk$ cd ~
mkdir whitepages
cd whitepages
aaron-tank_3@aaron-tankVirtualBox:~/whitepages$ wget https://challenge-files.cylabacademy.net/library/4a463561643f2cc25e74665dadd7ca654a9b828dc7a5b9239a8000ab4179c57e/whitepages.txt
--2026-09-30 11:10:11--  https://challenge-files.cylabacademy.net/library/4a463561643f2cc25e74665dadd7ca654a9b828dc7a5b9239a8000ab4179c57e/whitepages.txt
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.37, 13.226.187.22, 13.226.187.66, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[13.226.187.37]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 2766 (2,7K) [application/octet-stream]
Guardando como: ‘whitepages.txt’

whitepages.txt      100%[===================>]   2,70K  --.-KB/s    en 0,001s  

2026-09-30 11:10:12 (5,07 MB/s) - ‘whitepages.txt’ guardado [2766/2766]

aaron-tank_3@aaron-tankVirtualBox:~/whitepages$ ls -lh
file *
total 4.0K
-rw-rw-r-- 1 aaron-tank_3 aaron-tank_3 2.8K Sep 22 19:52 whitepages.txt
whitepages.txt: Unicode text, UTF-8 text, with very long lines (1296), with no line terminators
aron-tank_3@aaron-tankVirtualBox:~/whitepages$ xxd -l 160 whitepages.txt
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 8320 20e2 8083 e280 83e2   ......  .......
00000020: 8083 e280 8320 e280 8320 20e2 8083 e280  ..... ...  .....
00000030: 83e2 8083 2020 e280 8320 20e2 8083 e280  ....  ...  .....
00000040: 83e2 8083 e280 8320 e280 8320 20e2 8083  ....... ...  ...
00000050: e280 8320 e280 83e2 8083 e280 8320 20e2  ... .........  .
00000060: 8083 e280 8320 e280 8320 e280 8320 20e2  ..... ... ...  .
00000070: 8083 2020 e280 8320 e280 8320 2020 20e2  ..  ... ...    .
00000080: 8083 e280 8320 e280 83e2 8083 e280 83e2  ..... ..........
00000090: 8083 20e2 8083 20e2 8083 e280 83e2 8083  .. ... .........
aaron-tank_3@aaron-tankVirtualBox:~/whitepages$ python3 - <<'PY'
with open("whitepages.txt", "r", encoding="utf-8") as f:
    contenido = f.read()

bits = contenido.replace("\u2003", "0").replace(" ", "1")

print("Cantidad de bits:", len(bits))

mensaje = bytes(
    int(bits[i:i+8], 2)
    for i in range(0, len(bits), 8)
)

print(mensaje.decode("utf-8", errors="replace"))
PY
Cantidad de bits: 1296

academy

SEE PUBLIC RECORDS & BACKGROUND REPORT
5000 Forbes Ave, Pittsburgh, PA 15213
academy{not_all_spaces_are_created_equal_743510e5f5459071ed7d4109b7832a8e}

## Notas Adicionales


## Referencias