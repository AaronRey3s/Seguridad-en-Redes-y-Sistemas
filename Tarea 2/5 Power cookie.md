## Descripción
Can you get the flag?

Go to this [website](http://saturn.picoctf.net:58170/) and see what you can discover.

## Solución
- Abrí el reto haciendo clic en el enlace "website" de la descripción.
    
- Al entrar, vi el mensaje "We apologize, but we have no guest services at the moment.". Para investigar más, presioné **F12** y abrí las herramientas de desarrollador de mi navegador.
    
- Fui directamente a la pestaña **Application**. Si no la veía junto a "Elements" y "Console", daba clic en el ícono de las flechitas (`>>`) para buscarla en el menú oculto.
    
- En el menú del lado izquierdo, bajé hasta la sección "Storage" y ubiqué la opción **Cookies** (teniendo cuidado de no meterme por error a "Session storage").
    
- Desplegué **Cookies** y seleccioné la URL del reto, que empezaba con `[http://saturn.picoctf.net](http://saturn.picoctf.net)...`.
    
- En la tabla principal que me apareció del lado derecho, busqué la fila que tenía la variable `isAdmin` bajo la columna "Key".
    
- Le di doble clic al `0` que estaba en la columna "Value", lo borré, escribí un `1` y presioné **Enter** para guardar el cambio.
    
- Por último, presioné **F5** para recargar la página; con ese cambio el sitio se creyó que yo era administrador y me mostró la bandera en la pantalla.

picoCTF{gr4d3_A_c00k13_5d2505be}
## Notas Adicionales


## Referencias
