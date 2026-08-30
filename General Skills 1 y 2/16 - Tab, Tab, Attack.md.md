## Descripción
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.

## Solución
AaronTank5-academy@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/1d211441eced2214a10b0c2aacbf05d153aafcd6edc055f913cafcdb48a0b02b/Addadshashanammu.zip
--2026-08-25 03:24:04--  https://challenge-files.picoctf.net/c_wily_courier/1d211441eced2214a10b0c2aacbf05d153aafcd6edc055f913cafcdb48a0b02b/Addadshashanammu.zip
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.95, 3.160.5.64, 3.160.5.18, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 5166 (5.0K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.z 100%[==============>]   5.04K  --.-KB/s    in 0s      

2026-08-25 03:24:04 (118 MB/s) - 'Addadshashanammu.zip' saved [5166/5166]

AaronTank5-academy@webshell:~$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
 extracting: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet.c  
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
AaronTank5-academy@webshell:~$ ls
Addadshashanammu      ltdis.sh    static.2                  warm
Addadshashanammu.zip  ltdis.sh.1  static.ltdis.strings.txt
README.txt            static      static.ltdis.x86_64.txt
]                     static.1    strings
AaronTank5-academy@webshell:~$ cd add
-bash: cd: add: No such file or directory
AaronTank5-academy@webshell:~$ cd add
-bash: cd: add: No such file or directory
AaronTank5-academy@webshell:~$ cd Addadshashanammu/
AaronTank5-academy@webshell:~/Addadshashanammu$ cd Almurbalarammi/
AaronTank5-academy@webshell:~/Addadshashanammu/Almurbalarammi$ cd Ashalmimilkala/
AaronTank5-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilka
la$ cd Assurnabitashpi/
AaronTank5-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilka
la/Assurnabitashpi$ cd Maelkashishi/
AaronTank5-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilka
la/Assurnabitashpi/Maelkashishi$ cd Onn
-bash: cd: Onn: No such file or directory
AaronTank5-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilka
la/Assurnabitashpi/Maelkashishi$ cd Onnissiralis/
AaronTank5-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilka
la/Assurnabitashpi/Maelkashishi/Onnissiralis$ cd Ularradallaku/
AaronTank5-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilka
la/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet  fang-of-haynekhtnamet.c
AaronTank5-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilka
la/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427}
AaronTank5-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilka
la/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ 

## Notas Adicionales


## Referencias