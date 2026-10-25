## Descripción
A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it? Download the message [here](https://challenge-files.cylabacademy.net/library/d6cea3d41550d2d3e365dd3a7ea99fe9b44fe5fa437d1c921b5134a2070894a5/message.txt).

The decoded message names a phrase. Put that phrase, and nothing else, in the academy flag format: `academy{phrase}`.

## Solución
AaronTank5-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/d6cea3d41550d2d3e365dd3a7ea99fe9b44fe5fa437d1c921b5134a2070894a5/message.txt
--2026-10-25 01:19:58--  https://challenge-files.cylabacademy.net/library/d6cea3d41550d2d3e365dd3a7ea99fe9b44fe5fa437d1c921b5134a2070894a5/message.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.40, 3.160.5.64, 3.160.5.95, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 56 [application/octet-stream]
Saving to: 'message.txt'

message.txt        100%[==============>]      56  --.-KB/s    in 0s      

2026-10-25 01:19:58 (41.4 MB/s) - 'message.txt' saved [56/56]

AaronTank5-academy@webshell:~$ cat message.txt
Ta _7N6D4Chlg:W3D_H3C31N__3E4ef sHR053F38N43DBC i33___NBAaronTank5-academy
academy{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_43BBCEC4}

## Notas Adicionales


## Referencias
