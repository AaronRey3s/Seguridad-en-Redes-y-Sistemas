## Descripción
How to automate tasks to run at intervals on linux servers?
Aquí olvide anotar los datos del puerto
## Solución
AaronTank5-academy@webshell:~$ ssh -p 52173 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:52173 ([13.59.203.175]:52173)' can't be established.
ED25519 key fingerprint is SHA256:dMTscRrUiURy7uMu5eGWwEKdd2FzqLzx6LfWhssWnNQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:52173' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.17.0-1019-aws x86_64)

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

picoplayer@challenge:~$ sudo cd challenge/
[sudo] password for picoplayer: 
picoplayer is not in the sudoers file.  This incident will be reported.
picoplayer@challenge:~$ cd challenge/
-bash: cd: challenge/: No such file or directory
picoplayer@challenge:~$ cat etc/cron
cat: etc/cron: No such file or directory
picoplayer@challenge:~$ cat etc/crontab
cat: etc/crontab: No such file or directory
picoplayer@challenge:~$ cat /etc/crontab
picoCTF{Sch3DUL7NG_T45K3_L1NUX_1b4d8744}
picoplayer@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.

## Notas Adicionales
Cron para programar scripts que se ejecutan automaticamente en segundo plano a intervalos regulares, utiliza una sintaxis de 5 campos, desde el dia de la semana hasta el minuto en que se ejecutara la tarea.

## Referencias
