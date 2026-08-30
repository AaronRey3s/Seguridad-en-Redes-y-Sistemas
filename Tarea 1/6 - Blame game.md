## Descripción
Someone's commits seems to be preventing the program from working. Who is it?

You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/72/challenge.zip)

## Solución
Se hizo primero wget de challenge.zip despues se descomprimió con unzip
AaronTank5-academy@webshell:~$ cd drop-in
AaronTank5-academy@webshell:~/drop-in$ git log message.py
AaronTank5-academy@webshell:~/drop-in$ cat message.py
print("Hello, World!"
AaronTank5-academy@webshell:~/drop-in$  git log message.py
AaronTank5-academy@webshell:~/drop-in$ 
picoCTF{@sk_th3_1nt3rn_b64c4705}
## Notas Adicionales


## Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)
- [https://primer.picoctf.org/#_git_version_control](https://primer.picoctf.org/#_git_version_control)

