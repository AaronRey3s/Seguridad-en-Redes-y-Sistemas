
## Descripción
Can you figure out how this program works to get the flag? Connect to the program with netcat:

`$ nc chatelaine.cylabacademy.net 25599`

The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/29304f03408a71abe2959b78d93cf0ad4b599550b0dfc4ee3211c8376731d344/picker-IV.c). The binary can be downloaded [here](https://challenge-files.cylabacademy.net/library/29304f03408a71abe2959b78d93cf0ad4b599550b0dfc4ee3211c8376731d344/picker-IV).

1.- With Python, there are no binaries. With compiled languages like C, there is source code, and there are binaries. Binaries are created from source code, they are a conversion from the human-readable source code, to the highly efficient machine language, in this case: x86_64.

2.- How can you find the address that `win` is at?

## Solución
wget https://challenge-files.cylabacademy.net/library/29304f03408a71abe2959b78d93cf0ad4b599550b0dfc4ee3211c8376731d344/picker-IV -O picker-IV

file picker-IV

nm -n picker-IV | grep ' win$'

nc chatelaine.cylabacademy.net 25599

4012a1

academy{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_cccc13c1}

## Notas Adicionales


## Referencias

