
## Descripción

We found this [file](https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery). Recover the flag.
## Solución

1. Descargar e identificar el archivo

Primero, creamos un directorio de trabajo y descargamos el archivo proporcionado.

```
mkdir -p ~/corrupt
cd ~/corrupt

wget https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery

file c0rrupt-mystery
```

El comando `file` devuelve `data`, lo que indica que no reconoce el formato del archivo.

2. Analizar y reparar la cabecera PNG

Utilizamos `xxd` para examinar los primeros 64 bytes:

```
xxd -l 64 c0rrupt-mystery
```

El resultado muestra que la firma PNG y el nombre del bloque `IHDR` están dañados:

```
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452
```

La firma correcta de un PNG es `89 50 4E 47 0D 0A 1A 0A`. Reparamos la cabecera, restauramos el nombre `IHDR` y recalculamos su CRC mediante Python.

```
python3 - <<'PY'
import zlib

with open("c0rrupt-mystery", "rb") as f:
    data = bytearray(f.read())

data[:8] = bytes.fromhex("89504e470d0a1a0a")
data[12:16] = b"IHDR"

crc = zlib.crc32(data[12:29])
data[29:33] = crc.to_bytes(4, "big")

with open("reparado.png", "wb") as f:
    f.write(data)
PY
```

Comprobamos el resultado:

```
file reparado.png
```

Ahora el sistema reconoce una imagen PNG de 1642 × 1095 píxeles.

3. Detectar y eliminar un bloque dañado

Instalamos `pngcheck` y analizamos la estructura de la imagen.

```
sudo apt install pngcheck -y
pngcheck -v reparado.png
```

La herramienta detecta un error de CRC en el bloque `pHYs`. Como este bloque almacena información opcional sobre la resolución física, podemos eliminarlo sin afectar los píxeles.

```
python3 - <<'PY'
with open("reparado.png", "rb") as f:
    data = f.read()

pos = 0x42
assert data[pos:pos+4] == b"pHYs"

inicio = pos - 4
longitud = int.from_bytes(data[inicio:pos], "big")
assert longitud == 9

fin = pos + 4 + longitud + 4
data = data[:inicio] + data[fin:]

with open("reparado2.png", "wb") as f:
    f.write(data)
PY
```

4. Reparar el primer bloque IDAT

Volvemos a analizar el archivo:

```
pngcheck -v reparado2.png
xxd -s 0x38 -l 112 reparado2.png
grep -aob 'IDAT' reparado2.png
```

`pngcheck` señala una longitud de bloque inválida. Al examinar los bytes y localizar los bloques `IDAT`, identificamos que la longitud y el nombre del primero están alterados.

Corregimos ambos campos:

```
python3 - <<'PY'
with open("reparado2.png", "rb") as f:
    data = bytearray(f.read())

data[0x3e:0x42] = bytes.fromhex("0000ffa5")
data[0x42:0x46] = b"IDAT"

with open("reparado3.png", "wb") as f:
    f.write(data)
PY
```

5. Verificar la reparación y recuperar la bandera

Ejecutamos una última comprobación:

```
pngcheck -v reparado3.png
```

Esta vez, la herramienta reconoce correctamente los bloques `IHDR`, `sRGB`, `gAMA`, cuatro bloques `IDAT` y `IEND`. El resultado final es:

```
No errors detected in reparado3.png (8 chunks, 96.3% compression).
```

Abrimos la imagen recuperada:

```
xdg-open reparado3.png
```

La bandera se obtiene visualizando el contenido de la imagen. No se incluye su valor textual porque no quedó registrado en la salida de la terminal.

## Notas Adicionales

- `file`: identifica el formato de un archivo a partir de su contenido.
    
- `xxd`: permite visualizar los bytes de un archivo en formato hexadecimal.
    
- `pngcheck`: comprueba la estructura de los archivos PNG e identifica bloques dañados y errores de CRC.
    
- `IHDR`: bloque obligatorio que contiene las dimensiones y características de la imagen.
    
- `IDAT`: contiene los datos comprimidos de los píxeles.
    
- `pHYs`: bloque opcional que almacena la resolución física de la imagen.
    
- CRC: código de verificación utilizado para detectar alteraciones en los bloques PNG.
    

Durante la solución conservamos el archivo original y generamos copias sucesivas (`reparado.png`, `reparado2.png` y `reparado3.png`) para evitar perder información.

## Referencias

- [Archivo original del reto c0rrupt](https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery)
    
- [Especificación oficial del formato PNG — W3C](https://www.w3.org/TR/png-3/)
    
- [pngcheck — Herramienta para verificar archivos PNG](http://www.libpng.org/pub/png/apps/pngcheck.html)