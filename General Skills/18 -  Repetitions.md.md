## Descripción
Can you make sense of this file?

Multiple decoding is always good.

## Solución
AaronTank5-academy@webshell:~$ wget https://artifacts.picoctf.net/c/471/enc_flag
--2026-08-25 03:43:37--  https://artifacts.picoctf.net/c/471/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.64, 3.160.5.95, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 349 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag           100%[==============>]     349  --.-KB/s    in 0s      

2026-08-25 03:43:37 (157 MB/s) - 'enc_flag' saved [349/349]

AaronTank5-academy@webshell:~$ ls
Addadshashanammu      enc_flag    static.1                  strings
Addadshashanammu.zip  ltdis.sh    static.2                  warm
README.txt            ltdis.sh.1  static.ltdis.strings.txt
]                     static      static.ltdis.x86_64.txt
AaronTank5-academy@webshell:~$ cat enc_flag
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFpSV0VKWVZGVmtNRTVHV2tWU2JYUlVDbUpXV25sVWJGcHZWbGRHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
AaronTank5-academy@webshell:~$ base64 -d enc_flag
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlZRWEJYVFVkME5GWkVSbXRUCmJWWnlUbFpvVldGdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==
AaronTank5-academy@webshell:~$ base64 -d enc_flag > dec1
AaronTank5-academy@webshell:~$ cat dec1
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlZRWEJYVFVkME5GWkVSbXRUCmJWWnlUbFpvVldGdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==
AaronTank5-academy@webshell:~$ base64 -d dec1 > dec2
AaronTank5-academy@webshell:~$ cat dec2
V1RCa2MyRnRTWGRVYkZaVFltNVNjRmRXYUU5aVJUVnhWVzFhYVdGck5UWmFSVkpQWVRGbmVWVnVR
bHBsYTBweVUxWmpNRTVHWjNsVgpXR1JyVFdwV2VsUlZVbE5oTURCNVZXMWFVQXBXTUd0NFZERmtT
bVZyTlZoVWFteEVXbm93T1VOblBUMEsK
AaronTank5-academy@webshell:~$ base64 -d dec2 > dec3
AaronTank5-academy@webshell:~$ cat dec3
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aUApWMGt4VDFkSmVrNVhUamxEWnowOUNnPT0K
AaronTank5-academy@webshell:~$ base64 -d dec3 > dec4
AaronTank5-academy@webshell:~$ cat dec4
Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZP
V0kxT1dJek5XTjlDZz09Cg==
AaronTank5-academy@webshell:~$ base64 -d dec4 > dec5
AaronTank5-academy@webshell:~$ cat dec5
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfOWI1OWIzNWN9Cg==
AaronTank5-academy@webshell:~$ base64 -d dec5 > dec6
AaronTank5-academy@webshell:~$ cat dec6
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_9b59b35c}

## Notas Adicionales


## Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)