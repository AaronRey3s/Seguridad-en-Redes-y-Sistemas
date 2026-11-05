aaron-tank_3@aaron-tankVirtualBox:~$ mkdir -p ~/safeopener
aaron-tank_3@aaron-tankVirtualBox:~$ cd ~/safeopener
aaron-tank_3@aaron-tankVirtualBox:~/safeopener$ wget -O SafeOpener.class https://challenge-files.cylabacademy.net/library/308dba42907970273fbd1e86cc3ca93a57e41541350cbb0e034b846c1d9c16c2/SafeOpener.class
--2026-11-05 10:38:49--  https://challenge-files.cylabacademy.net/library/308dba42907970273fbd1e86cc3ca93a57e41541350cbb0e034b846c1d9c16c2/SafeOpener.class
Resolviendo challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.22, 13.226.187.37, 13.226.187.66, ...
Conectando con challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)[13.226.187.22]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 2036 (2,0K) [application/octet-stream]
Guardando como: ‘SafeOpener.class’

SafeOpener.class    100%[===================>]   1,99K  --.-KB/s    en 0s      

2026-11-05 10:38:50 (19,5 MB/s) - ‘SafeOpener.class’ guardado [2036/2036]

aaron-tank_3@aaron-tankVirtualBox:~/safeopener$ strings -n10 SafeOpener.class
LineNumberTable
LocalVariableTable
LSafeOpener;
([Ljava/lang/String;)V
[Ljava/lang/String;
Ljava/io/BufferedReader;
InnerClasses
Ljava/util/Base64$Encoder;
encodedkey
Ljava/lang/String;
StackMapTable
Exceptions
(Ljava/lang/String;)Z
SourceFile
SafeOpener.java
java/io/BufferedReader
java/io/InputStreamReader
Enter password for the safe: 
java/lang/StringBuilder
You have  
 attempt(s) left
,academy{SAf3_0p3n3rr_y0u_solv3d_it_501f2cf5}
Sesame open
Password is incorrect
SafeOpener
java/lang/Object
java/util/Base64$Encoder
java/lang/String
java/io/IOException
java/lang/System
Ljava/io/InputStream;
(Ljava/io/InputStream;)V
(Ljava/io/Reader;)V
java/util/Base64
getEncoder
()Ljava/util/Base64$Encoder;
Ljava/io/PrintStream;
java/io/PrintStream
(Ljava/lang/String;)V
()Ljava/lang/String;
encodeToString
([B)Ljava/lang/String;
-(Ljava/lang/String;)Ljava/lang/StringBuilder;
(I)Ljava/lang/StringBuilder;
(Ljava/lang/Object;)Z
aaron-tank_3@aaron-tankVirtualBox:~/safeopener$ strings -n10 SafeOpener.class | grep aca
,academy{SAf3_0p3n3rr_y0u_solv3d_it_501f2cf5}
aaron-tank_3@aaron-tankVirtualBox:~/safeopener$ 


## Descripción
What can you do with this file? I forgot the key to my safe but this [file](https://challenge-files.cylabacademy.net/library/308dba42907970273fbd1e86cc3ca93a57e41541350cbb0e034b846c1d9c16c2/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

## Solución


## Notas Adicionales


## Referencias

