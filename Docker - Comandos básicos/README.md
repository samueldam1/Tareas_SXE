1. Descarga la imagen 'ubuntu’ y comprueba que está en tu equipo.

Descargamos la imagen usando `docker run ubuntu`.
Comprobamos que la imagen está en nuestro equipo con `docker image ls`.

2. Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre.

Con `docker run ubuntu` arrancamos un contenedor ubuntu sin nombre. Para obtener el nombre usamos el comando `docker ps` que nos permite ver la lista de contenedores en ejecución. Para ver los que ya no están en	ejecución añadiremos el parámetro `-a`.

3. Crea un contenedor con el nombre 'dam_ubu1'. ¿Como puedes acceder a él?

Añadiendo el parámetro `-it` a `docker run` nos permitirá interactuar con el contenedor. 

El comando final quedaría tal que así `docker run -it --name dam_ubu1 ubuntu bash`.

4. Comprueba que ip tiene y si puedes hacer un ping a google.com

Para esto necesitamos instalar `iputils-ping` (lo haremos con el comando `apt install iputils-ping`). 

Una vez instalado en el contenedor haremos ping a "google.com" con el comando `ping google.com`.

5. Crea un contenedor con el nombre 'dam_ubu2'. ¿Puedes hacer ping entre los contenedores?

Necesitamos instalar primero `net-tools` (lo haremos con el comando `apt install net-tools`) y usar el comando `ifconfig` para saber la ip de nuestros contendores.

6. Sal del terminal, ¿que ocurrió con el contenedor?

Al salir del terminal los contendores se paran pero no se borran. Para poder visualizarlos tendremos que añadir el parámetro `-a` al comando `docker ps`.

Podremos volver a levantarlos con el comando `docker start 'nombre-del-container'`.

7. ¿Cuanta memoria en el disco duro ocupaste?



8. ¿Cuanta RAM ocupan los contenedores? ¿Hay algún comando docker para saber esto?.

|CONTAINER ID | NAME     | CPU % | MEM USAGE | LIMIT | MEM % | NET I/O     | BLOCK I/O | PIDS |
|-------------|----------|-------|--------|----------|-------|-------------|-----------|------|
|2f5783bfd699 | dam_ubu2 | 0.00% | 876KiB | 15.39GiB | 0.01% | 5.41kB / 0B | 0B / 0B   | 1    |
|8694323c23fd | dam_ubu1 | 0.00% | 884KiB | 15.39GiB | 0.01% | 5.67kB / 0B | 0B / 0B   | 1    |