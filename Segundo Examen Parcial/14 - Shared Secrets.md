## Descripción
A message was encrypted using a shared secret... but it looks like one side of the exchange leaked something. Can you piece together the secret and get the flag? Download the [message](https://challenge-files.cylabacademy.net/library/696a330c92491df25f02f3f20e552a2b8b1b8fd8c5ffc3b3902b972c24638f19/message.txt). And source [code](https://challenge-files.cylabacademy.net/library/696a330c92491df25f02f3f20e552a2b8b1b8fd8c5ffc3b3902b972c24638f19/encryption.py)

1.- What do you get if you combine a public key with a known private one?

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-crypto/04-shared-secrets
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-crypto/04-shared-secrets
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/04-shared-secrets$ wget -O message.txt 'https://challenge-files.cylabacademy.net/library/0c5716023de07c8f5e39852dad85c3c416bb8de0fb7fb3216ae79dd5bf1a58e3/message.txt'
--2026-10-31 17:14:03--  https://challenge-files.cylabacademy.net/library/0c5716023de07c8f5e39852dad85c3c416bb8de0fb7fb3216ae79dd5bf1a58e3/message.txt
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.26, 18.238.132.49, 18.238.132.88, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.26]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1027 (1,0K) [application/octet-stream]
Guardando como: ‘message.txt’

message.txt         100%[===================>]   1,00K  --.-KB/s    en 0,001s  

2026-10-31 17:14:08 (1,27 MB/s) - ‘message.txt’ guardado [1027/1027]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/04-shared-secrets$ wget -O encryption.py 'https://challenge-files.cylabacademy.net/library/0c5716023de07c8f5e39852dad85c3c416bb8de0fb7fb3216ae79dd5bf1a58e3/encryption.py'
--2026-10-31 17:14:17--  https://challenge-files.cylabacademy.net/library/0c5716023de07c8f5e39852dad85c3c416bb8de0fb7fb3216ae79dd5bf1a58e3/encryption.py
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.26, 18.238.132.49, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.115]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1090 (1,1K) [application/octet-stream]
Guardando como: ‘encryption.py’

encryption.py       100%[===================>]   1,06K  --.-KB/s    en 0s      

2026-10-31 17:14:18 (10,2 MB/s) - ‘encryption.py’ guardado [1090/1090]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/04-shared-secrets$ cat message.txt
g = 2
p = 2145321271368762603109368281068901863057920430686244838680943803686084982191431380882751960074075303634188521097409123807735825768081836679766652776844695974321842685262658985995721561125725799315096255838972736446052295081735044555740238902064575290346513159227816093492744414622581004346156503174602882444846777607
A = 85841679821316185176510217540374787910617937121996371280787993961302612118583512408006926302837093963400088083507204043726190743741256068961711826803091702032869674485098509200462418617206677392227538038429508972552415839722721204727756264643225087592751608914981619684381335479660745494274582368438318625660898716
b = 754367239667829665929306554646797966628812257493888916847188353235739149112713860169499396745795576012482115028598706226284915273517220329639404222927667752084760248912860274058539305948473139903230697905081933228057441138891801529356672350338617082362712469705681122566301235070824860406217225054390955765962776994
enc = 0a080a0f0e0612100f033418580819581f34525a580f0f0f5c5e16
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/04-shared-secrets$ cat encryption.py
import os
import sys

from Crypto.Util.number import getPrime
from random import randint

# Public parameters
g = 2
p = getPrime(1048)

# Server's secret
a = randint(2, p-2)
A = pow(g, a, p)

# Client secret
b = randint(2, p-2)

B = pow(g, b, p)

# Shared key
shared = pow(A, b, p)

# Encrypt flag
flag = b"academy{...}"
enc = bytes([x ^ (shared % 256) for x in flag])

# Write challenge info
#
# You were handed message.txt alongside this script, and this writes that same
# name. Running it here would overwrite the file you have to solve with a fresh
# transcript over the redacted flag above -- a different p and b, and nothing to
# recover. So refuse rather than clobber.
if os.path.exists("message.txt"):
    sys.exit("message.txt already exists here -- that is the file you were given, "
             "and running this would overwrite it. Move it aside first, or run "
             "this somewhere else.")

with open("message.txt", "w") as f:
    f.write(f"g = {g}\n")
    f.write(f"p = {p}\n")
    f.write(f"A = {A}\n")
    f.write(f"b = {b}\n")
    f.write(f"enc = {enc.hex()}\n")
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/04-shared-secrets$ nano exp.py
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/04-shared-secrets$ python3 exp.py
academy{dh_s3cr3t_913ddd75}
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/04-shared-secrets$ 



## Notas Adicionales
- El valor privado `b` filtrado permite reconstruir el secreto compartido.
- En esta instancia, `secreto % 256` produce `34`; ese es el valor utilizado para deshacer XOR.

## Referencias