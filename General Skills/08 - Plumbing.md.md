##Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?

##Solución
Se guardan los cambios en un archivo que llamé koala

```
AaronTank5-academy@webshell:~$ nc fickle-tempest.picoctf.net 59312 > koala
```

Se usa la funcion cat para buscar koala

```
AaronTank5-academy@webshell:~$ cat koala | grep pico
- picoCTF{digital_plumb3r_1eBfC512}
```

##Notas Adicionales


##Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)