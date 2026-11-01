## Descripción
Everything seems secure; strong numbers, familiar parameters but something small might ruin it all. Can you recover the message? Download the [message](https://challenge-files.cylabacademy.net/library/6838f6423a4aaa55592ff8b72be8e3453da45539db3e12dc43bc3ba783654be9/message.txt). And source [code](https://challenge-files.cylabacademy.net/library/6838f6423a4aaa55592ff8b72be8e3453da45539db3e12dc43bc3ba783654be9/encryption.py)

1.- This might be a job for Boneh-Durfee.

## Solución
mkdir -p ~/picoctf-crypto/08-small-trouble

cd ~/picoctf-crypto/08-small-trouble

wget -O message.txt 'https://challenge-files.cylabacademy.net/library/12a109dcb6df171263125b726d1065707a5a3907ca77783ca8d11693931443f0/message.txt'

wget -O encryption.py 'https://challenge-files.cylabacademy.net/library/12a109dcb6df171263125b726d1065707a5a3907ca77783ca8d11693931443f0/encryption.py'

cat message.txt

cat encryption.py

nano exp.py

source ~/picoctf-crypto/entorno/bin/activate

python3 exp.py
FLAG: academy{sm4ll_d_073cf0e5}


## Notas Adicionales
- Aunque la pista menciona Boneh-Durfee, Wiener funciona con estos datos. El script también comprueba el resultado volviendo a cifrar el mensaje recuperado.

## Referencias