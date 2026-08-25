## Descripción
Can you look at the data in this binary? The bash script might help!

## Solución
AaronTank5-academy@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/ad443900e4d8d8e6d0f3250730125d24ce6ceaf10ab38658eaafc175eee37422/static
--2026-08-25 02:32:54--  https://challenge-files.picoctf.net/c_wily_courier/ad443900e4d8d8e6d0f3250730125d24ce6ceaf10ab38658eaafc175eee37422/static
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.95, 3.160.5.40, 3.160.5.64, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16776 (16K) [application/octet-stream]
Saving to: 'static.2'

static.2           100%[==============>]  16.38K  --.-KB/s    in 0.006s  

2026-08-25 02:32:54 (2.55 MB/s) - 'static.2' saved [16776/16776]

AaronTank5-academy@webshell:~$ https://challenge-files.picoctf.net/c_wily_courier/ad443900e4d8d8e6d0f3250730125d24ce6ceaf10ab38658eaafc175eee37422/ltdis.sh
-bash: https://challenge-files.picoctf.net/c_wily_courier/ad443900e4d8d8e6d0f3250730125d24ce6ceaf10ab38658eaafc175eee37422/ltdis.sh: No such file or directory
AaronTank5-academy@webshell:~$ chmod +x ltdis.sh 
AaronTank5-academy@webshell:~$ ./ltdis.sh
Attempting disassembly of  ...
objdump: 'a.out': No such file
objdump: section '.text' mentioned in a -j option, but not found in any input file
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
AaronTank5-academy@webshell:~$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
AaronTank5-academy@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_20335e41}
AaronTank5-academy@webshell:~$ 

## Notas Adicionales


## Referencias
