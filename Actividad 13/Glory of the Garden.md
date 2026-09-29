## Descripción
This file contains more than it seems. Get the flag from garden.jpg.

1.- What is a hex editor?

## Solución
AaronTank5-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/e78198c6a7dc5e471e8429d4953e7595feafe17764258eec169b8dab8bb3c925/garden.jpg
--2026-09-29 01:45:29--  https://challenge-files.cylabacademy.net/library/e78198c6a7dc5e471e8429d4953e7595feafe17764258eec169b8dab8bb3c925/garden.jpg
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.18, 3.160.5.64, 3.160.5.95, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295191 (2.2M) [application/octet-stream]
Saving to: 'garden.jpg'

garden.jpg         100%[==============>]   2.19M  1.82MB/s    in 1.2s    

2026-09-29 01:45:30 (1.82 MB/s) - 'garden.jpg' saved [2295191/2295191]

AaronTank5-academy@webshell:~$ strings garden.jpg | grep "picoCTF{"
AaronTank5-academy@webshell:~$ strings garden.jpg | grep "academyCTF{"
AaronTank5-academy@webshell:~$ file garden.jpg
garden.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, baseline, precision 8, 2999x2249, components 3
AaronTank5-academy@webshell:~$ strings -n 10 garden.jpg
XICC_PROFILE
mntrRGB XYZ 
Copyright (c) 1998 Hewlett-Packard Company
sRGB IEC61966-2.1
sRGB IEC61966-2.1
IEC http://www.iec.ch
IEC http://www.iec.ch
.IEC 61966-2.1 Default RGB colour space - sRGB
.IEC 61966-2.1 Default RGB colour space - sRGB
,Reference Viewing Condition in IEC61966-2.1
,Reference Viewing Condition in IEC61966-2.1
        %       :       O       d       y
#*%%*525EE\
#*%%*525EE\
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
jVRVik#'        E
Kqk,*[zHW s
.n"Vg`8,2Mz
+^+}N/}7-^
(.Zm')[M_n
kHlmmWlpg/
@:W7ykc<RK4j
h       wvgpZ%!T
oKlqv6QYZy
jO$Q\oe8!G
{We:qN)-Zvf
z;7^}k,6        8:|
.ji[[&cF4qU
fU$P>Rx?J-
 ,J?!^ouyd
|f]8{hJVJ)
}>g<\gn_u5{4x
DVF?t7<}=+
l[Muyqp&#m
zxjRi9Is~F
=GcQZY^Egh
#<m;q^m_iZ
Y|Soif&YFQO=95
.fkBx'"Bx@
VrjN2I'm69
+Fpi>^[[]N
[Gq     ;x9*{WC{
5yo/$YJF0v
m6%bq{*ztM
_;$Mo#FF0F+
l5{mWOh/c*
F5      'r2     ,2=
vIidlkqJn7
yIn+v]N;M:T
'n~_SJm;->
zj0Z\XI8vL
bm.saewewlD
l=:IsB7rmI=w
I/-mr8<%bad
E9-m{_Vg7G
[\}Qn%[wo,
Fn+M7?N|Co
*y}-5VItW=7
cU*T_,uR]QX
<9yd53"\Aj
zx|5:Xx({h
Ksi#E2)a!=
qn;w<%,.nnv
kt}L15!E:p
_c^mHEUUoy]]_F
w{sog3m@8V+
Hn#7.70PS8;
_AQUsKk?=n]
Y=L4%)^I=-
3k$7[@|`tl
*D[X    0rFGj
)n%U`8$7j+
*E4RJC&FG'
su*(~$7z;^
OzWfwrN:VL
5:wZigm=w&
w:m_R7RDT`z
UZzkmu9eQ)=
hIINJ1Q[kgc
}7;=rdk[ub
Z2.]NGpONM:
BkR>i!>iB=
IpWTKFT$)8
M=u4wi'&Cif
=1H"#b0',8
hlk7pi6?iwL
aa,yD=E}..
3`|9pu]F9~C3
6RHK>e\oB:g
v0,'x^D99]
}4s,5'*x,<.
Fquau);^=l|
Pj2Oe2M:DR<
%F7}3_)x        u
*}r=sNFK}.e#
mN5'MBNPm?
09>WE:1NMiRz
ZRikwmum#|5iS
Y#B|+4;AlK ]
o<S#yrG dld
pEtN.mm.mle
\GhZY?y'oA
6L4n>R;r}+
wae:uc(>YwG
Here is a flag: academy{more_than_m33ts_the_3y3e23d7ba9}

## Notas Adicionales
Un editor hexadecimal es un tipo de programa informático que permite a los usuarios modificar archivos binarios.

## Referencias