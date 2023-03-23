# Práctica 2
## Parte 1
Para comenzar con la práctica creamos un volumen haciendo uso del comando:


`docker volume create volumeDocker`


Con este comando hemos podido crear el volumen con el nombre indicado en el enunciado. Una vez tenemos el volumen pasamos a crear nuestro contenedor Nginx haciendo uso del comando:


`docker run -d -p 80:8080 --name=ContenedorNginx --mount type=volume,source=volumeDocker,target=/app bitnami/apache`


Tras esto hemos creado un contenedor el cual hemos añadido al volumen que acabamos de crear y adelantándonos un poco le hemos asignado el puerto 80. Procedemos a comprobar que el contenedor está vacío y actualizamos el _index.html_ añadiendole un saludo personal. Esto lo conseguiremos haciendo uso de los siguientes comandos:


`docker exec -it --user=root ContenedorNginx /bin/bash` --> Para acceder a un terminal del contenedor


`nano index.html` --> Para acceder y modificar el fichero _index.html_


Cabe destacar que tenemos que instalar las herramientas necesarias para poder hacer uso del nano, comandos que considero irrelevantes en la redacción de la resolución de la práctica ya que son de conocimiento general y si los incluimos alargaríamos la resolución innecesariamente llegando a ser tedioso su contenido.


Continuando con la resolución, tras acceder al fichero _index.html_ lo modificados quedando en mi caso su contenido tal que así:


```html
<html>
    <head>
        <title>zuleimamuji</title>
    </head>
    <body>
        <p>Holaaa esto ha sido creado por Zuleima Munoz Jimenez en el curso 22/23</p>
    </body>
</html>
```

