## Descripción
Can you break into this super secure portal?

[http://fickle-tempest.picoctf.net:57723](http://fickle-tempest.picoctf.net:57723)

## Solución
La lógica se basa en cómo funciona el método `substring()` de JavaScript y en el uso de multiplicadores matemáticos para ocultar el orden real del texto.

- **La función `substring(inicio, fin)`:** Extrae una porción de una cadena de texto, comenzando en la posición de `inicio` y terminando justo antes de la posición `fin`.
    
- **La variable `split`:** Actúa como el tamaño fijo de cada bloque de texto. Como la primera validación es `substring(0, split) == 'pico'`, y la palabra "pico" tiene exactamente 4 letras, sabemos que `split` equivale a **4**.
    

El programador dividió la bandera en bloques de 4 caracteres. Para verificar la contraseña, usó multiplicadores de la variable `split` (ej. `split*2`, `split*3`) para calcular la posición exacta de cada bloque. Sin embargo, para confundirte, escribió las condiciones `if` en un orden completamente aleatorio.

Para reconstruir la contraseña, simplemente debes ignorar el orden en que están escritos los `if` y organizar los fragmentos matemáticamente, de la posición más baja a la más alta:

1. Posición **0** a **4** `(0, split)`: **pico**
    
2. Posición **4** a **8** `(split, split*2)`: **CTF{**
    
3. Posición **8** a **12** `(split*2, split*3)`: **no_c**
    
4. Posición **12** a **16** `(split*3, split*4)`: **lien**
    
5. Posición **16** a **20** `(split*4, split*5)`: **ts_p**
    
6. Posición **20** a **24** `(split*5, split*6)`: **lz_2**
    
7. Posición **24** a **28** `(split*6, split*7)`: **eb02**
    
8. Posición **28** a **32** `(split*7, split*8)`: **b45}**
    

Al alinear los bloques siguiendo la secuencia de los multiplicadores (0, 1, 2, 3, 4, 5, 6, 7), los fragmentos se unen como un rompecabezas para formar la cadena completa.
picoCTF{no_clients_plz_2eb02b45}
## Notas Adicionales


## Referencias