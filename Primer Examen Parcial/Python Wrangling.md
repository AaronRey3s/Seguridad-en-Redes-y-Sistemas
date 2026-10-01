## Descripción
Python scripts are invoked kind of like programs in the Terminal... Can you run [ende.py](https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/ende.py) using [password.txt](https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/password.txt) to get [flag.txt.en](https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/flag.txt.en)?

## Solución
AaronTank5-academy@webshell:~$ mkdir python_wrangling
AaronTank5-academy@webshell:~$ cd python_wrangling
AaronTank5-academy@webshell:~/python_wrangling$ wget https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/ende.py
--2026-09-30 03:20:52--  https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/ende.py
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.40, 3.160.5.18, 3.160.5.95, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1328 (1.3K) [application/octet-stream]
Saving to: 'ende.py'

ende.py            100%[==============>]   1.30K  --.-KB/s    in 0s      

2026-09-30 03:20:52 (616 MB/s) - 'ende.py' saved [1328/1328]

AaronTank5-academy@webshell:~/python_wrangling$ wget https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/password.txt
--2026-09-30 03:21:10--  https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/password.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.18, 3.160.5.95, 3.160.5.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 33 [application/octet-stream]
Saving to: 'password.txt'

password.txt       100%[==============>]      33  --.-KB/s    in 0s      

2026-09-30 03:21:10 (15.0 MB/s) - 'password.txt' saved [33/33]

AaronTank5-academy@webshell:~/python_wrangling$ wget https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/flag.txt.en
--2026-09-30 03:21:25--  https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/flag.txt.en
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.95, 3.160.5.64, 3.160.5.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 140 [application/octet-stream]
Saving to: 'flag.txt.en'

flag.txt.en        100%[==============>]     140  --.-KB/s    in 0s      

2026-09-30 03:21:25 (68.3 MB/s) - 'flag.txt.en' saved [140/140]

AaronTank5-academy@webshell:~/python_wrangling$ python3 ende.py -d flag.txt.en
Please enter the password:^CTraceback (most recent call last):
  File "/home/AaronTank5-academy/python_wrangling/ende.py", line 39, in <module>
    sim_sala_bim = input("Please enter the password:")
KeyboardInterrupt

AaronTank5-academy@webshell:~/python_wrangling$ cat password.txt
563e47ddeaf84eca8b2a31201381a898
AaronTank5-academy@webshell:~/python_wrangling$ python3 ende.py -d flag.txt.en
Please enter the password:563e47ddeaf84eca8b2a31201381a898
academy{4p0110_1n_7h3_h0us3_d6af8f37}



## Notas Adicionales


## Referencias