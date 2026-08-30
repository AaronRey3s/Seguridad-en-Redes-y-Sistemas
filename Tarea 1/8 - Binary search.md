## Descripción
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.

Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!

You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/18/challenge.zip)

## Solución
AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c_atlas/18/challenge.zip
--2026-08-30 06:26:06--  https://artifacts.picoctf.net/c_atlas/18/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.64, 3.160.5.95, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1041 (1.0K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip      100%[==============>]   1.02K  --.-KB/s    in 0s      

2026-08-30 06:26:07 (288 MB/s) - 'challenge.zip' saved [1041/1041]

AaronTank5-academy@webshell:~$ ssh -p 56490 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:56490 ([18.217.83.136]:56490)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:56490' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 67
Higher! Try again.
Enter your guess: 500
Higher! Try again.
Enter your guess: 300
Higher! Try again.
Enter your guess: 123
Higher! Try again.
Enter your guess: 456
Higher! Try again.
Enter your guess: 890
Lower! Try again.
Enter your guess: 678
Higher! Try again.
Enter your guess: 700
Lower! Try again.
Enter your guess: 690
Lower! Try again.
Enter your guess: 680
Higher! Try again.
Sorry, you've exceeded the maximum number of guesses.
Connection to atlas.picoctf.net closed.
AaronTank5-academy@webshell:~$ ssh -p 56490 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 685
Higher! Try again.
Enter your guess: 686
Higher! Try again.
Enter your guess: 687
Higher! Try again.
Enter your guess: 688
Higher! Try again.
Enter your guess: 689
Higher! Try again.
Enter your guess: 690
Higher! Try again.
Enter your guess: 800
Higher! Try again.
Enter your guess: 999
Lower! Try again.
Enter your guess: 900
Higher! Try again.
Enter your guess: 950
Lower! Try again.
Sorry, you've exceeded the maximum number of guesses.
Connection to atlas.picoctf.net closed.
AaronTank5-academy@webshell:~$ ssh -p 56490 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 900
Higher! Try again.
Enter your guess: 950
Higher! Try again.
Enter your guess: 990
Higher! Try again.
Enter your guess: 999
Lower! Try again.
Enter your guess: 998
Lower! Try again.
Enter your guess: 997
Lower! Try again.
Enter your guess: 996
Lower! Try again.
Enter your guess: 990
Higher! Try again.
Enter your guess: 993
Higher! Try again.
Enter your guess: 994
Higher! Try again.
Sorry, you've exceeded the maximum number of guesses.
Connection to atlas.picoctf.net closed.
AaronTank5-academy@webshell:~$ ssh -p 56490 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 995
Lower! Try again.
Enter your guess: 999
Lower! Try again.
Enter your guess: 500
Higher! Try again.
Enter your guess: 747
Higher! Try again.
Enter your guess: 871
Lower! Try again.
Enter your guess: 809
Higher! Try again.
Enter your guess: 840
Higher! Try again.
Enter your guess: 855
Lower! Try again.
Enter your guess: 847
Higher! Try again.
Enter your guess: 850
Higher! Try again.
Sorry, you've exceeded the maximum number of guesses.
Connection to atlas.picoctf.net closed.
AaronTank5-academy@webshell:~$ ssh -p 56490 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 250
Lower! Try again.
Enter your guess: 125
Lower! Try again.
Enter your guess: 80
Higher! Try again.
Enter your guess: 102
Lower! Try again.
Enter your guess: 91
Lower! Try again.
Enter your guess: 85
Higher! Try again.
Enter your guess: 88
Lower! Try again.
Enter your guess: 86
Congratulations! You guessed the correct number: 86
Here's your flag: picoCTF{g00d_gu355_2e90d29b}
Connection to atlas.picoctf.net closed.

## Notas Adicionales


## Referencias


