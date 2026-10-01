## Descripción
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer. `ssh -p 28134 ctf-player@xebec.cylabacademy.net`. The password is `13792798`


Al conectarnos, obtenemos una shell llamada `Specialer`, la cual tiene comandos extremadamente limitados.

Intentamos usar comandos comunes:

```shell
ls
cat flag.txt
```

Pero obtenemos:

```
-bash: ls: command not found
-bash: cat: command not found
```

## Enumeración

Al presionar `Enter`, la shell muestra los comandos disponibles (builtins de bash):

```shell
echo
cd
pwd
read
printf
...
```

Esto significa que solo podemos usar **builtins de bash**, no binarios del sistema.

## Navegación
Podemos movernos con `cd` y ver rutas con `pwd`:

```shell
cd /home
pwd
```

Luego entramos al directorio del usuario:

```shell
cd ctf-player
```

Observamos directorios interesantes:

```
abra/  ala/  sim/
```

Entramos en `ala`:

```shell
cd ala
```

---

## Lectura de archivos sin `cat`

Sabemos que `cat` no está disponible, pero bash permite leer archivos con redirección:

```shell
echo $(<archivo)
```

Intentamos con el archivo sospechoso:

```shell
echo $(<kazam.txt)
```

Esto nos devuelve la flag
academy{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_f7316569}

- La shell está restringida eliminando comandos como `ls` y `cat`.
    
- Sin embargo, **bash sigue permitiendo expansión de comandos**.
    
- La sintaxis `$(<archivo)` es una forma de leer archivos directamente en bash sin usar `cat`.
    
- Esto permite evadir restricciones del entorno.