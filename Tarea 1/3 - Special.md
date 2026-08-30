## Descripción
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)

Start your instance to see connection details.

`ssh -p 50466 [ctf-player@saturn.picoctf.net](mailto:ctf-player@saturn.picoctf.net)`

The password is `8a707622`

## Solución
AaronTank5-academy@webshell:~$ ssh -p 50466 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:50466 ([13.59.203.175]:50466)' can't be established.
ED25519 key fingerprint is SHA256:tJ0wuU5yBvNO/FrkHmR9iY36VJClMhKV+Hq2sxqKFmg.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:50466' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.17.0-1019-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

Special$ ls
Is 
sh: 1: Is: not found
Special$ ls -la
Is la 
sh: 1: Is: not found
Special$ ${:ls}
${:ls} 
sh: 1: Bad substitution
Special$ ${parameter=ls}
${parameter=ls} 
blargh
Special$ cat blarh
Cat blah 
sh: 1: Cat: not found
Special$ cat blargh
Cat large 
sh: 1: Cat: not found
Special$ ((cat)) < blargh/flag.txt
((cat)) < blargh/flag.txt 
picoCTF{5p311ch3ck_15_7h3_w0r57_a60bdf40}Special$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
AaronTank5-academy@webshell:~$ 

## Notas Adicionales
En realidad se estaba ejecuntado un script de python que cambiaba las palabras, al poner entre doble parentesis el comando a ejecutar se rompia la "seguridad" que tenia el script de python

## Referencias

