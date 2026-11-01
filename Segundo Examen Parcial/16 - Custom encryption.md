## Descripción
Can you get sense of this code file and write the function that will decode the given encrypted file content.

Find the encrypted file here [flag_info](https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/enc_flag) and [code file](https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/custom_encryption.py) might be good to analyze and get the flag.

1.- Understanding encryption algorithm to come up with decryption algorithm.

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/picoctf-crypto/06-custom-encryption
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/picoctf-crypto/06-custom-encryption
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/06-custom-encryption$ wget -O enc_flag 'https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/enc_flag'
--2026-10-31 17:29:40--  https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/enc_flag
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.26, 18.238.132.49, 18.238.132.88, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.26]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 280 [application/octet-stream]
Guardando como: ‘enc_flag’

enc_flag            100%[===================>]     280  --.-KB/s    en 0s      

2026-10-31 17:29:40 (370 MB/s) - ‘enc_flag’ guardado [280/280]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/06-custom-encryption$ wget -O custom_encryption.py 'https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/custom_encryption.py'
--2026-10-31 17:29:52--  https://challenge-files.cylabacademy.net/library/168dfb66953daef3e9c494a5ee63a78f09370e1e39d8b1489d5f9c090acd2a8f/custom_encryption.py
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.88, 18.238.132.115, 18.238.132.26, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[18.238.132.88]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1411 (1,4K) [application/octet-stream]
Guardando como: ‘custom_encryption.py’

custom_encryption.p 100%[===================>]   1,38K  --.-KB/s    en 0,001s  

2026-10-31 17:29:53 (2,43 MB/s) - ‘custom_encryption.py’ guardado [1411/1411]

aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/06-custom-encryption$ cat enc_flag
a = 91
b = 25
cipher is: [148347, 379109, 313177, 82415, 98898, 32966, 1137327, 1120844, 1054912, 692286, 0, 1368089, 346143, 82415, 1120844, 0, 362626, 1417538, 16483, 1021946, 395592, 445041, 98898, 98898, 280211, 98898, 428558, 197796, 412075, 379109, 280211, 82415, 98898, 0]
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/06-custom-encryption$ cat custom_encryption.py
from random import randint
import sys


def generator(g, x, p):
    return pow(g, x) % p


def encrypt(plaintext, key):
    cipher = []
    for char in plaintext:
        cipher.append(((ord(char) * key*311)))
    return cipher


def is_prime(p):
    v = 0
    for i in range(2, p + 1):
        if p % i == 0:
            v = v + 1
    if v > 1:
        return False
    else:
        return True


def dynamic_xor_encrypt(plaintext, text_key):
    cipher_text = ""
    key_length = len(text_key)
    for i, char in enumerate(plaintext[::-1]):
        key_char = text_key[i % key_length]
        encrypted_char = chr(ord(char) ^ ord(key_char))
        cipher_text += encrypted_char
    return cipher_text


def test(plain_text, text_key):
    p = 97
    g = 31
    if not is_prime(p) and not is_prime(g):
        print("Enter prime numbers")
        return
    a = randint(p-10, p)
    b = randint(g-10, g)
    print(f"a = {a}")
    print(f"b = {b}")
    u = generator(g, a, p)
    v = generator(g, b, p)
    key = generator(v, a, p)
    b_key = generator(u, b, p)
    shared_key = None
    if key == b_key:
        shared_key = key
    else:
        print("Invalid key")
        return
    semi_cipher = dynamic_xor_encrypt(plain_text, text_key)
    cipher = encrypt(semi_cipher, shared_key)
    print(f'cipher is: {cipher}')


if __name__ == "__main__":
    message = sys.argv[1]
    test(message, "trudeau")
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/06-custom-encryption$ nano exp.py
aaron-tank_3@aaron-tankVirtualBox:~/picoctf-crypto/06-custom-encryption$ python3 exp.py
Flag: academy{custom_d2cr0pt6d_200ccafe}


## Notas Adicionales
- XOR se deshace aplicando de nuevo la misma clave.
- El script lee los parámetros de tu archivo para evitar copiar valores de otra instancia.

## Referencias