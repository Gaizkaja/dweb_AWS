# Comprobar modulos de Apache en AWS 
Indica qué módulos estáticos hay activos en tu instancia de AWS y qué hace cada una de ellas:
Activar módulos:
1. Comprueba si los módulos info y status están activos en tu instancia.  
Con el comando *apache2ctl -M* nos aparecen los módulos activos actualmente como vemos de los dos arriba requeridos solo se encuentra activo el módulo status.  
![Primera Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/comprobacion.PNG)
2. Activa el módulo que no esté activo y compruébalo.
Lo que debemos hacer en este apartado es utilizar un comando que el el *a2enmod* para activar los módulos en el primer caso nos activa correctamente.   
![Segunda Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/apache.PNG)  
Para activar el módulo correctamente deberemos hacer un *sudo systemctl restart apache2* para reiniciar el servicio de Apache.   
![Tercera Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/apache2.PNG)  
 Y para comprobar volvemos a utilizar el comando anterior. *apache2ctl -M*  
![Cuarta Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/comp_2.PNG)
Y vemos como esta en el módulo status y el módulo info.
