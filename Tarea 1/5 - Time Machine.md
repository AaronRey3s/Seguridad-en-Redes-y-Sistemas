## Descripción
What was I last working on? I remember writing a note to help me remember...

You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/160/challenge.zip)

## Solución
AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c_titan/160/challenge.zip
--2026-08-30 05:51:24--  https://artifacts.picoctf.net/c_titan/160/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.64, 3.160.5.95, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17740 (17K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip      100%[==============>]  17.32K  --.-KB/s    in 0s      

2026-08-30 05:51:24 (69.3 MB/s) - 'challenge.zip' saved [17740/17740]

AaronTank5-academy@webshell:~$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt     
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
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/89/
 extracting: drop-in/.git/objects/89/d296ef533525a1378529be66b22d6a2c01e530  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
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
AaronTank5-academy@webshell:~/drop-in$ cd ../
AaronTank5-academy@webshell:~$ cat drop-in/message.txt
This is what I was working on, but I'd need to look at my commit history to know why...AaronTank5-academy@webshell:~$ /drop-in/.git$ git log
-bash: /drop-in/.git$: No such file or directory
AaronTank5-academy@webshell:~$ drop-in/.git$ git log
-bash: drop-in/.git$: No such file or directory
AaronTank5-academy@webshell:~$ cd drop-in
AaronTank5-academy@webshell:~/drop-in$ /drop-in/.git$ git log
-bash: /drop-in/.git$: No such file or directory
AaronTank5-academy@webshell:~/drop-in$ drop-in/.git$ git log
-bash: drop-in/.git$: No such file or directory
AaronTank5-academy@webshell:~/drop-in$ git log --oneline
picoCTF{t1m3m@ch1n3_186cd7d7}
## Notas Adicionales


## Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)
- [https://primer.picoctf.org/#_git_version_control](https://primer.picoctf.org/#_git_version_control)

