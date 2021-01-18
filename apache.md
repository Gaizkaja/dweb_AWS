# Apache

### Ficheros de configuración y directivas en Linux
#### 1. ¿Cuál es la ruta a los ficheros de configuración de apache?  
En la ruta /etc/apache2 están el fichero principal de configuración apache2.conf y ports.conf y en la misma ruta pero un directorio más adelante /etc/apache2/sites-available se encuentra el 000-default.conf
#### 2. ¿Cuál es el fichero de configuración principal?  
El fichero de la configuración principal suele ser en los sistemas Ubuntu apache2.conf y en los demás httpd.conf
#### 3. ¿Que son las directivas "include" que aparecen en el fichero de configuración principal?  
Las directivas "include" son los modulos que vienen activados por defecto un vez que instalas Apache
#### 4. ¿Que contiene el fichero ports.conf?  
Este fichero contiene los puertos que podemos modificar según nuestras necesidades.
#### 5. ¿Que contiene el fichero envvars?  
Almacenan variables de entorno de Apache2
#### 6. ¿Cuál es el uso de las carpetas "sites-avaliable" y "sites-enabled"?  
Contiene enlaces a ficheros del directorio /etc/apache2/sites-available. Cuando un fichero de configuración en sites-available está enlazado, el sitio será activado al iniciar Apache2.

## Ejercicio 2 Directivas de Apache

- ServerRoot: Indica el directorio raíz donde se encuentran los ficheros de configuración, error y logs
- ServerAdmin: Dirección de correo del administrador del servidor
- ServerName: Indica el nombre y puerto con el que el servidor se identificará ante las peticiones que se realicen.
- User: Usuario con el que se ejecutará apache
- Include: Entrada que indica la ruta a diferentes ficheros de configuración que apache cargará al iniciarse
- Group: Grupo con el que se ejecutará apache
- KeepAlive: Indica el modo de funcionamiento del servidor en el intercambio de peticiones y envíos con los clientes
- Files: Limita el alcance de las directivas adjuntas por nombre de archivo.
- Location: Las directivas incluidas se aplican a una URL determinada, por lo que la ruta especificada es relativa al valor de la raíz de los documentos del servidor DocumentRoot
- Errorlog: Indica donde se almacenarán los mensajes de error del servidor Web
- Listen: Indica la dirección IP y puerto en el que el servidor Web escucha peticiones Si no se indica ninguna dirección IP o se indica con el símbolo * el servidor. 80 / 443
- Alias: Indica un camino distinto al camino por defecto para un recurso al que debe acceder el servidor
- Redirect: Redirecciona a una página que nosotros pongamos.
- ErrorDocument 404: Sale cuando el documento HTML no ha sido encontrado.
- Options: La directiva Options controla qué características del servidor están disponibles en un directorio determinado.
- *<Virtualhost> Virtual Host</Virtualhost>*
- <Directory>Directort</Directory>: Las directivas incluidas se aplican sobre un directorio y sus subdirectorios
- DocumentRoot: Indica el directorio a partir del cual se encuentran las páginas Web del servidor	
- DirectoryIndex: Indica los nombres y orden de las páginas por defecto que apache buscará si en la petición de un cliente no se especifica
