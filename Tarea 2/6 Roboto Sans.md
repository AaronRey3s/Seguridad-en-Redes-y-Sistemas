## Descripción
The flag is somewhere on this web application not necessarily on the website. Find it.

Check [this](http://saturn.picoctf.net:63793/) out.

## Solución
Entre al link que aparece en el reto
[flexed](http://saturn.picoctf.net:63793/)a este link le agregue esto al final   "/robots.txt"
me dio esto que esta codificado en Base 64
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/

al descodificarlo reemplace "/robots.txt" por lo que estaba codificado de este modo 
- `saturn.picoctf.net:63793/js/myfile.txt`
    
- `saturn.picoctf.net:63793/flag1.txt`
ya solo busque en cual de los dos links estaba la flag
## Notas Adicionales


## Referencias
