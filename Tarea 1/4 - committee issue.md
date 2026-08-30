## Descripción
I accidentally wrote the flag down. Good thing I deleted it!

You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/76/challenge.zip)

## Solución
AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c_titan/76/challenge.zip
--2026-08-30 02:52:15--  https://artifacts.picoctf.net/c_titan/76/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.95, 3.160.5.40, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19201 (19K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip      100%[==============>]  18.75K  --.-KB/s    in 0.002s  

2026-08-30 02:52:15 (11.0 MB/s) - 'challenge.zip' saved [19201/19201]

AaronTank5-academy@webshell:~$ ls
Addadshashanammu      dec5                 level3.py
Addadshashanammu.zip  dec6                 ltdis.sh
README.txt            enc_flag             ltdis.sh.1
]                     files                runme.py
big-zip-files         files.zip            serpentine.py
big-zip-files.zip     fixme1.py            static
challenge.zip         fixme2.py            static.1
code.py               l                    static.2
codebook.txt          level1.flag.txt.enc  static.ltdis.strings.txt
convertme.py          level1.py            static.ltdis.x86_64.txt
dec1                  level2.flag.txt.enc  strings
dec2                  level2.py            warm
dec3                  level3.flag.txt.enc
dec4                  level3.hash.bin
AaronTank5-academy@webshell:~$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/d2/
 extracting: drop-in/.git/objects/d2/63841da2567e3e869d2b90e8e3bdd8838555b5  
   creating: drop-in/.git/objects/c0/
 extracting: drop-in/.git/objects/c0/cc0495794727db1682daa105367f28112796af  
   creating: drop-in/.git/objects/e7/
 extracting: drop-in/.git/objects/e7/20dc26a1a55405fbdf4d338d465335c439fb3e  
   creating: drop-in/.git/objects/d5/
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
   creating: drop-in/.git/objects/0c/
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
   creating: drop-in/.git/objects/a6/
 extracting: drop-in/.git/objects/a6/dca68e4310585eac3b5c9caf0f75967dfe972c  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt     
AaronTank5-academy@webshell:~$ ls
Addadshashanammu      dec5                 level3.hash.bin
Addadshashanammu.zip  dec6                 level3.py
README.txt            drop-in              ltdis.sh
]                     enc_flag             ltdis.sh.1
big-zip-files         files                runme.py
big-zip-files.zip     files.zip            serpentine.py
challenge.zip         fixme1.py            static
code.py               fixme2.py            static.1
codebook.txt          l                    static.2
convertme.py          level1.flag.txt.enc  static.ltdis.strings.txt
dec1                  level1.py            static.ltdis.x86_64.txt
dec2                  level2.flag.txt.enc  strings
dec3                  level2.py            warm
dec4                  level3.flag.txt.enc
AaronTank5-academy@webshell:~$ cd drop-in
AaronTank5-academy@webshell:~/drop-in$ ls -la
total 8
drwxr-xr-x 3 AaronTank5-academy AaronTank5-academy   37 Mar  9  2024 .
drwxr-xr-x 8 AaronTank5-academy AaronTank5-academy 4096 Aug 30 02:52 ..
drwxr-xr-x 8 AaronTank5-academy AaronTank5-academy  166 Mar  9  2024 .git
-rw-r--r-- 1 AaronTank5-academy AaronTank5-academy   11 Mar  9  2024 message.txt
AaronTank5-academy@webshell:~/drop-in$ git log --oneline
AaronTank5-academy@webshell:~/drop-in$ git log --oneline
AaronTank5-academy@webshell:~/drop-in$ git show e720dc2
AaronTank5-academy@webshell:~/drop-in$ 

## Notas Adicionales


## Referencias


