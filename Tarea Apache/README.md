1. Descarga la imagen 'httpd' y comprueba que está en tu equipo.

Descargamos la imagen en nuestro equipo con el comando `docker image pull httpd:2.4`. En nuestro caso usaremos el tag "2.4" pero por default viene el tag "latest".

2. Crea un contenedor con el nombre 'dam_httpd'.

Con el comando `docker run --name dam_httpd` creamos el contenedor con el nombre que querramos.

3. Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.

En el `docker run` deberemos añadir el parámetro `-p 8080:80`.

4. Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.

Para esto debemos añadir a nuestro `docker run` el parámetro `-v "$PWD"/htdocs:/usr/local/apache2/htdocs/`

5. Realiza un 'hola mundo' en html (usa Code) y comprueba que accedes desde el navegador.

Crearemos un fichero en nuestra máquina con nombre 'index.html' en la carpeta htdocs y crearemos una etiqueta 'h1' cuyo contenido sea 'hola mundo'.

6. Crea otro contenedor 'dam_web2' con el mismo volumen y a otro puerto, por ejemplo 9080.

Usaremos el comando `docker run -dit --name dam_web2 -p 9080:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4`.

7. Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador:

Ambos muestran los mismo. "HOLA MUNDO".

8. Realiza modificaciones de la página y comprueba que los dos servidores 'sirven' la misma página

Modificando el archivo 'index.html' para que muestre "ADIOS MUNDO" cambia lo mostrado en el navegador.
