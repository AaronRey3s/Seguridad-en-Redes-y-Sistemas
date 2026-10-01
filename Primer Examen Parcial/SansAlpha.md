## Descripción
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols. `ssh -p 48553 ctf-player@chatelaine.cylabacademy.net`

Use password: `fd7746b4`

## Solución
El servidor no acepta comando con letras 

Se intenta ejecutar archivos en subdirectorios:

```shell
./*/*
```

Output:

```
bash: ./blargh/flag.txt: Permission denied
```

### Explicación

- `*` es un wildcard que representa cualquier nombre
    
- `./*/*` intenta acceder a archivos dentro de carpetas
    

Se detecta el archivo:

```
./blargh/flag.txt
```

Pero no se puede ejecutar directamente por permisos.

## Generación de texto sin usar letras

Se ejecuta:

```shell
_1=`$ 2>&1`
```

### Explicación

- `$` por sí solo genera un error
    
- `2>&1` redirige el error a salida estándar
    
- El resultado se guarda en la variable `_1`
    

Contenido aproximado de `_1`:

```
bash: $: command not found
```

---

## Extracción de caracteres

Se utilizan substrings:

```shell
${_1:9:1}
${_1:10:1}
```

### Explicación

Sintaxis:

```shell
${variable:posición:longitud}
```

Esto permite extraer letras específicas del mensaje de error sin escribirlas manualmente.

Se arma el comando dinámicamente:

```shell
/???/?${_1:9:1}?${_1:10:1}
```

### Explicación

- `/???/` coincide con rutas como `/bin/`
    
- `?` representa un carácter
    
- `${_1:...}` inserta letras extraídas
    

Esto reconstruye un comando como:

```shell
/bin/cat
```

---

## Lectura del archivo sin escribir su nombre

Se utiliza:

```shell
"$(<./*/????.???)"
```

### Explicación

- `./*/????.???` busca archivos como `flag.txt`
    
- `< archivo` lee el contenido
    
- `$()` ejecuta la expresión
    

---

## Ejecución final

```shell
/???/?${_1:9:1}?${_1:10:1} "$(<./*/????.???)"
```

---

Como resultado dará la flag.

## Notas Adicionales


## Referencias

