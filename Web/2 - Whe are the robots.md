## Descripción
Can you find the robots?

[http://fickle-tempest.picoctf.net:49369](http://fickle-tempest.picoctf.net:49369)

## Solución
aaron-tank_3@aaron-tankVirtualBox:~$ curl http://fickle-tempest.picoctf.net:50322/robots.txt
No se ha encontrado la orden «curl», pero se puede instalar con:
sudo apt install curl
aaron-tank_3@aaron-tankVirtualBox:~$ sudo apt install curl
[sudo: authenticate] Contraseña:          
Instalando:                              
  curl

Resumen:
  Actualizando: 0, Instalando 1, Eliminando: 0, no actualizando: 2
  Tamaño de la descarga: 272 kB
  Espacio necesario: 522 kB / 30,2 GB disponible

Des:1 http://mx.archive.ubuntu.com/ubuntu resolute-updates/main amd64 curl amd64 8.18.0-1ubuntu2.4 [272 kB]
Descargados 272 kB en 1s (214 kB/s)
Seleccionando el paquete curl previamente no seleccionado.
(Leyendo la base de datos ... 153003 ficheros o directorios instalados actualmente.)
Preparando para desempaquetar .../curl_8.18.0-1ubuntu2.4_amd64.deb ...
Desempaquetando curl (8.18.0-1ubuntu2.4) ...
Configurando curl (8.18.0-1ubuntu2.4) ...
Procesando disparadores para man-db (2.13.1-1build1) ...
aaron-tank_3@aaron-tankVirtualBox:~$ curl http://fickle-tempest.picoctf.net:50322/robots.txt
User-agent: *
Disallow: /cc6b1.htmlaaron-tank_3@aaron-tankVirtualBox:~$ curl http://fickle-tempest.picoctf.net:50322/cc6b1.html
<!doctype html>
<html>
  <head>
    <title>Where are the robots</title>
    <link href="https://fonts.googleapis.com/css?family=Monoton|Roboto" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>
  <body>
    <div class="container">
      
      <div class="content">
	<p>Guess you found the robots<br />
	  <flag>picoCTF{ca1cu1at1ng_Mach1n3s_cc6b1}</flag></p>
      </div>
      <footer></footer>
  </body>
</html>aaron-tank_3@aaron-tankVirtualBox:~$ 


picoCTF{ca1cu1at1ng_Mach1n3s_cc6b1}

## Notas Adicionales
`curl` es una herramienta de línea de comandos que sirve para **enviar y recibir datos desde una URL**. Se usa muchísimo en Linux, desarrollo web, APIs y ciberseguridad.

## Referencias


