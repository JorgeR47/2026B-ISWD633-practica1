# BIND MOUNT
En un bind mount mapeamos (montar) un directorio o archivo específico del sistema de archivos del host con una parte del sistema de ficheros del contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```
ó
```
docker run -d --name <nombre contenedor> --mount type=bind,source=<ruta carpeta host>,target=<ruta carpeta contenedor> <imagen>
```
- destination, dst, target: La ruta donde se monta el archivo o directorio en el contenedor.
- source, src: El origen del montaje.
  
### En tu computador crear una carpeta llamada nginx y dentro de esta carpeta crea otra llamada html. Como se aprecia en la figura.
![Volúmenes](directorio.PNG)

### Crear un contenedor con la imagen nginx:alpine, mapear todos por puertos, para la ruta carpeta host colocar el directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html (esta ruta se obtiene al revisar la documentación de la imagen)
![Volúmenes](volumen-host.PNG)
# docker run -d  --name nginx -p 3000:80 -v  "C:\Users\vbox\docker\nginx\html":/usr/share/nginx/html  nginx:alpine

### ¿Qué sucede al ingresar al servidor de nginx?

# Al ejecutar el comando "docker exec -it nginx sh" se ingresa normalmente al contenedor. Al refrescar la página http://localhost:3000/ anteriormente se aprecia el mensaje "403 Forbidden nginx/1.31.6". 


### ¿Qué pasa con el archivo index.html del contenedor?

# El archivo index.html queda oculto por el contenido de la carpeta del computador (C:\Users\vbox\docker\nginx\html). Al ingresar al navegador (http://localhost/index.php) se muestra el mensaeje "No se puede acceder a este sitio web"


### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de tu computador en la carpeta html

### ¿Qué sucede al ingresar al servidor de nginx?
# Al ejecutar el comando "docker exec -it nginx sh" se ingresa normalmente al contenedor. Después de la descromprensión, al refrescar la página http://localhost:3000/  se aprecia el template. 

### Eliminar el contenedor
# docker rm -f nginx . 
# Este comando fuerza la eliminación, a pesar de que el contenedor se está ejecutando.


### ¿Qué sucede al crear nuevamente un contenedor montado al directorio definidos anteriormente?
# Al eliminar el contenedor, los archivos del host se mantienen. Al crear nuevamente el contenedor, incluso se visualiza el template al ingresar al navegador. 


