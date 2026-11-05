
## Descripción
This service can provide you with a random number, but can it do anything else? Connect to the program with netcat:

`$ nc xebec.cylabacademy.net 46024`

The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/0981ed1dcae182f5d272ebe49164d0dc2c09f043e1843e26dbebaa80317d3245/picker-I.py).

1.- Can you point the program to a function that does something useful for you?

## Solución
                                                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ mkdir pickeruno
                                                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ cd pickeruno 
                                                                                                                                                             
┌──(kali㉿kali)-[~/pickeruno]
└─$ nc chatelaine.cylabacademy.net 48238
Try entering "getRandomNumber" without the double quotes...
==> win
0x61 0x63 0x61 0x64 0x65 0x6d 0x79 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x63 0x35 0x35 0x66 0x62 0x65 0x66 0x35 0x7d 
Try entering "getRandomNumber" without the double quotes...
==> 
Try entering "getRandomNumber" without the double quotes...
==> python3 -c 'print("".join(chr(int(x, 16)) for x in input("Pega los valores hex: ").split()))'
invalid syntax (<string>, line 1)
                                                                                                                                                             
┌──(kali㉿kali)-[~/pickeruno]
└─$ python3 -c 'print("".join(chr(int(x, 16)) for x in input("Pega los valores hex: ").split()))'
Pega los valores hex: 0x61 0x63 0x61 0x64 0x65 0x6d 0x79 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x63 0x35 0x35 0x66 0x62 0x65 0x66 0x35 0x7d
academy{4_d14m0nd_1n_7h3_r0ugh_c55fbef5}


academy{4_d14m0nd_1n_7h3_r0ugh_c55fbef5}

## Notas Adicionales


## Referencias

