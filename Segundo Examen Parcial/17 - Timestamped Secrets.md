## Descripción
Someone encrypted a message using AES in ECB mode but they weren’t very careful with their key. Turns out it’s derived from something as simple as the current time! Can you uncover the key and decrypt the flag? Download the encrypted message: [message](https://challenge-files.cylabacademy.net/library/838909e4e064bca5edc41edd46ebb4f8350eb82f2aea2540ea564e491c6d437e/message.txt)  
You may also find the encryption script helpful: [code](https://challenge-files.cylabacademy.net/library/838909e4e064bca5edc41edd46ebb4f8350eb82f2aea2540ea564e491c6d437e/encryption.py)

1.- `encryption.py` is a redacted example of the program

## Solución
mkdir -p ~/picoctf-crypto/07-timestamped-secrets

cd ~/picoctf-crypto/07-timestamped-secrets

wget -O message.txt 'https://challenge-files.cylabacademy.net/library/19f6ce60f219eddc3613ac4b301bea75a863ddca9e9230c50c8d72fe36ce2a21/message.txt'

wget -O encryption.py 'https://challenge-files.cylabacademy.net/library/19f6ce60f219eddc3613ac4b301bea75a863ddca9e9230c50c8d72fe36ce2a21/encryption.py'

cat message.txt

cat encryption.py

nano exp.py

source ~/picoctf-crypto/entorno/bin/activate

python3 exp.py
academy{sa3S_sEc9t_99162e4b}


## Notas Adicionales
- La clave se puede reconstruir porque depende de un timestamp revelado por la pista. Comprobé que recifrar la bandera con esa clave reproduce el archivo original.

## Referencias