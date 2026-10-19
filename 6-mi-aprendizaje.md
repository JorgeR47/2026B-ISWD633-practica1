# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado o utilizó otros comandos que no se mencionan al realizar la práctica también se debe documentar.

Previo a la práctica tenía conocimiento de ciertos comandos, el aprendizaje logrado es la administración de bases de datos y el uso de imagenes o servicios web como WordPress.

Para la ejecución de la práctica, se utilizaron los siguientes comandos adicionales:
1. docker rm -f nginx
Este comando fuerza la eliminación, a pesar de que el contenedor se está ejecutando.

ejercicio 3:
Se utilizaron los comandos para los contenedores con imagen mysql y wordpress
1. docker run -d --name mysql -e MYSQL_ROOT_PASSWORD=1234 --network net-wp -v "C:\Users\vbox\docker\ejercicio3\db":/var/lib/mysql mysql
2. docker run -d --name wordpress -e WORDPRESS_DB_HOST=mysql -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=1234 -p 9500:80 --network net-wp -v "C:\Users\vbox\docker\ejercicio3\www":/var/www/html wordpress

