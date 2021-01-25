# Ejercicio Virtual Host

## Configurar los VirtualHost en base a los parametros que nos piden.
1. www.apuntes.daw.net:80   
1.1 Configuración mediante fichero .htaccess.   
1.2 Alojado en: /var/www/apuntes/.   
1.3 Sin Fichero index.   
1.4 Permitir mostrar índice de ficheros.   
1.5 Pagina de error 404: /var/www/404.html.   
1.6 Redirigir www.apuntes.daw.net/buscador/ a www.google.es.   
1.7 Ficheros log: apuntes.error.log y apuntes.access.log

![Primera Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/Config_Apache.PNG)  


2. www.daw.net:443  
2.1 Alojado en: /var/www/daw/seguro/   
2.2 Crear y utilizar el certificado daw.crt y la firma daw.key  
2.3 Fichero index: inicio.html.  
2.4 No permitir mostrar índice de ficheros.   
2.5 Pagina de error 404: /var/www/404.html   
2.6 Ficheros log: daw.ssl.error.log y daw.ssl.access.log   
2.7 Autenticación de usuarios "Basic” con fichero de usuarios permitidos en /var/www/acceso.basic.daw

![Segunda Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/Config_Apache2.PNG)  
