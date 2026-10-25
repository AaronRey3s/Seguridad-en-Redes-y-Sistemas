## Descripción
This service provides you an encrypted flag. Can you decrypt it with just N & e? Connect to the program with netcat:

`$ nc chatelaine.cylabacademy.net 39887`

The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/742b4d10be646510247831837d9876dafee7f7eb0eea7ee82eaf8f04981ef2d3/encrypt.py).

1.- How much do we trust randomness?

2.- Notice anything interesting about N?

3.- Try comparing N across multiple requests

## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir -p ~/even-rsa
cd ~/even-rsa
nc -w 5 chatelaine.cylabacademy.net 39887 | tee datos.txt
nano exp.py
N: 23678255470198524947349063042466830530437107459223589740613844937245824234088716414889339923448529076990865965853278826000758520890081424048886506757769186 e: 65537 cyphertext: 11370319844740477773564746186767886448626957440659665316447273422380975404777405066105368233927248292674190910731071350543023793395572323493235805429405443
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/even-rsa]
└─$ python3 exp.py 
academy{tw0_1$_pr!m3d832b35c}
```

## Notas Adicionales


## Referencias
