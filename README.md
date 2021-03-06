# Documentacion AWS Instancia
#### Lo primero que debemos hacer es crear una instancia una que hemos iniciado nos aparecera la siguiente pantalla 
Aqui tenemos que elegir l sistema operativo en nuestro caso Ubuntu con la ultima version disponible 20.04 LTS.

![Primera Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap1.PNG)
#### Seguiremos el Wizard que nos ofrece AWS y en nuestro caso utilizaremos las opciones gratuitas.

Como somos estudiantes nos acojeremos a las opciones gratuitas.
![Segunda Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap2.PNG)

#### Saltamos unas pantallas hasta la 4 donde cambiaremos el almacenamiento hasta los 30GB que nos oferta gratuitamente.

Añadimos los maximo que podemos gratuitamente.

![Tercera Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap3.PNG)

#### Ahora nos saltamos el paso de los tags y llegamos al apartado de Security.

En esta pantalla no sera necesario cambiar nada lo dejaremos todo por defecto.

![Cuarta Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap4.PNG)

#### Y por ultimo en la pantalla final del Wizard de creacion de la instacia lanzaremos dicha instacia y crearemos un fichero las claves privadas

Aqui elegimos un nombre que recordemos y que sea corto para luego entrar desde Git_bash no tengamos que poner una linea largisima. Y por último aqui lanzamos la instacia.

![Quinta Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap5.PNG)

#### Para saber que poner debemos ir al apartado conectar para que nos aparezca la siguiente pantalla 

Seguimos los pasos aqui referidos.

![Sexta Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap9.PNG)

#### Una vez que tenemos la clave privada ya creada nos iremos a la terminal desde donde nos conectaremos via SSH.

Aqui lo que deberemos hacer es cambiar permisos al archivo que hemos creado nosotros le pondremos 400 con el comando *chmod 400 [nombre del archivo]*

![Septima Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap6.PNG)

#### Ahora nos conectaremos por ssh

Desde la linea "*ssh -i "Claves_Privadas.pem" ubuntu@ec2-3-86-97-98-compute-1.amazonaws.com*" nos conectamos por ssh.
Le ponemos si para que nos deje continuar.

![Octava Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap7.PNG)

#### Una vez hecho todo ya estariamos dentro de la maquina virtual de Ubuntu

![Novena Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap8.PNG)

#### Por último pero no menos importante nos vamos a la pantalla principal de las instacias.
Aqui deberemos Detener la instancia para que en nuestro caso no se nos gaste el saldo.

# Ahora instalaremos unos paquetes en el servidor

## Empezaremos por instalar Apache

Lo primero que deberemos hacer es iniciar la instancia al igual que hicimos anteriormente. Con el comando *sudo apt install apache2*, comprobamos que estar funcionando con el comando *sudo systemctl status apache2*.

![Decima Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_Apache1.PNG)
![Undecima Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_Apache2.PNG)

## Visualizar desde navegador

Deberemos ir al apartado de seguridad de nuestra instacia en la consola de AWS y añadir una nueva regla que sera la de HTTP con el puerto 80 para poder conectar desde el navegador.

![Duodecima Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_Apache5.PNG)

Y esto nos aparecera si hemos configurado correctamente.

![Decimotercera Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_Apache3.PNG)

Ahora comprobamos desde el navegador y nos deberia aparecer lo siguiente.

![Decimocuarta Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_Apache4.PNG)

## Ahora instalaremos MySQL

### Es un proceso muy sencillo

Al igual que con Apache solo necesitaremos dos comando *sudo apt install mysql-server* y *sudo systemctl status mysql* esta vez lo deberemos hacer desde root ya que nos pide una contraseña por temas de seguridad y Ubuntu no trae por defecto lo cual nos lleva a que no nos deje comprobar el status.

![Decimoquinta Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_Mysql1.PNG)
![Decimasexta Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_Mysql2.PNG)

Por si nos salta algun fallo tenemos que un update antes de instalar MySQL

## Ahora instalaremos PHP

Al igual que con Apache,MySQL solo necesitaremos dos comando *sudo apt-get install php7.4 libapache2-mod-php7.4 php7.4-cli php7.4-mysql php7.4-gd php7.4-imagick php7.4-recode php7.4-tidy php7.4-xmlrpc* y *sudo systemctl status php7.4-fpm* esta vez lo deberemos hacer desde root ya que nos pide una contraseña por temas de seguridad y Ubuntu no trae por defecto lo cual nos lleva a que no nos deje comprobar el status.

![Decimaseptima Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_PHP1.PNG)
![Decimaoctava Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_PHP2.PNG)

## Ahora instalaremos FTP

Al igual que con Apache,MySQL,PHP solo necesitaremos dos comando *sudo apt-get install vsftpd* y *sudo systemctl status vsftpd* esta vez lo deberemos hacer desde root ya que nos pide una contraseña por temas de seguridad y Ubuntu no trae por defecto lo cual nos lleva a que no nos deje comprobar el status.

![Decimanovena Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_Vsftp1.PNG)
![Vigesima Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_Vsftp2.PNG)

# Ahora configuraremos una IP Elastica en la consola AWS

## ¿Qué es y para qué sirve una IP Elástica?

Las direcciones IP elásticas son direcciones IPv4 estáticas diseñadas para la informática en la nube dinámica.

## Es un proceso realmente sencillo de configurar

Debemos ir al apartado de seguridad IP elastica, asignamos un IP Elastica

![Vigesimprimera Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_IpElastic.PNG)

![Vigesimosegunda Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_IpElastic1.PNG)

Lo unico que debemos configurar es el ultimo apartado que tendremos que poner nuestra instacia 

![Vigesimotercera Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_IpElastic2.PNG)




# Configuración DNS

## ¿Qué es y para qué sirve el DNS?

Es un sistema jerárquico que se ocupa de administrar los nombres de dominio. Una especie de base de datos y traductor para que, en vez de leer la IP 172.11.122.45 —un número asociado a la máquina donde está alojado el dominio—, leamos grupo1.zerbitzaria.net, algo legible y fácil de recordar.

## - Indica cuales son y para qué se usan los diferentes tipos de registros DNS.

1. A: Apunta a una dirección IP. Por ejemplo: 192.168.32.15  
2. AAAA: Al igual que el anterior apunta a una IP pero esta vez a una dirección IPv6. Por ejemplo: 2001:0dd8:85a3:08d3:1319:8a2e:0370:7334  
3. CNAME: Apunta a otro dominio o a otro subdominio.   
4. MX: Se utilizan para apuntar a los servidores de correo electrónico.  
5. PTR: Se utiliza para  el registro inverso, traduce IP a nombre de dominio. 
6. TXT: puedes rellenarlos con cualquier texto que desees. Los usos más habituales de los registros TXT son verificar la propiedad del dominio y evitar el uso indebido del correo electrónico. 
7. NS: Servidor de nombres, asocia un nombre de dominio y el servidor de nombres.
8. SOA: Zona de autoridad, proporciona información sobre el servidor DNS primario.  
9. SRV: Service record.  

## Imagen los registros DNS de tu sitio en Guebs y explicación de los registros de tu dominio grupo1.zerbitzaria.net.

![Vigesimocuarta Captura ](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/img/Cap_DNS1.PNG)

1. Dirección IP de nuestro dominio 
2. Nombre asociado a la dirección de correo.
3. Lo rellenamos para evitar el uso indebido del correo electronico.

## ¿Cuántos servidores DNS existen ?
  
Exiten varios servidores DNS pero yo he elegido los siguientes:

1. Servidor de resolución de código auxiliar DNS
2. Servidor de resolución recursiva DNS
3. Servidor autoritario de DNS

## ¿Cuántas redirecciones DNS son posibles?

Todas las necesarias hasta que encuentre la direccion IP que corresponda a la dirección solicitada.

## ¿Que es un servidor DNS Raiz?

Un servidor raíz es un servidor de nombres para la zona raíz del Sistema de nombres de dominio de Internet.​ Los servidores de nombres raíz son una parte fundamental de Internet, ya que son el primer paso en la resolución de los nombres de host legibles en direcciones IP que se utilizan en la comunicación entre los hosts de Internet.

Una combinación de los límites en el DNS y de ciertos protocolos, a saber, como el tamaño de los paquetes no fragmentados en el User Datagram Protocol (UDP), se tradujo en un número limitado de direcciones de los servidores raíz que se pueden acomodar en respuestas a consultas DNS de nombres.

## ¿Para qué montar un servidor si simplemente escribiendo en un fichero la relación IP/Nombre el sistema ya funcionaría?

Por temas de seguridad, y si alguien quiere conectarse al servidor necesitaria tener en local el fichero /etc/hosts la resolución de nombres y si tienes un servidor cualquiera que sepa la dirección IP o la URL se podría conectar.

##  ¿Es posible si dispones de una conexión a Internet con IP dinámica ofrecer servicios en Internet?
Si, a través del servicio de DNS Dinamico que nos cambiaria nuestra IP en todos los sevidores. 

## ¿cuál sería el proceso para encontrar la IP de la dirección web: http://www.debian.org/distrib/netinst?

Lo primero que hacemos es introducir la dirección URL, luego esa petición llega al Servidor DNS Primario que hace una consulta Servidor DNS Raiz y responde con la dirección IP y nombre de un servidor DNS para el dominio superior .org.  Ahora El servidor vuelve a hacer una consulta pero esta vez al servidor DNS para el dominio .org, el cual te responde con la dirección IP y el nombre de los servidores de nombre para debian.org.   
El  servidor DNS primario otra vez hace una consulta pero esta vez el servidor autoritario de debian.org el cual responde con la dirección IP de e corresponde. 

Por último el servidor DNS Primario nos responde a la consulta direccionandonos a la pagina solicitada.


## ¿Que es la ICANN?

ICANN es una organización que opera a nivel multinacional/internacional y es la responsable de asignar las direcciones del protocolo IP, de los identificadores de protocolo, de las funciones de gestión del sistema de dominio y de la administración del sistema de servidores raíz.  
ICANN se dedica a preservar la estabilidad de Internet por medio de procesos basados en el consenso.  
ICANN coordina la administración de los elementos técnicos del Sistema de Nombres de Dominio (DNS) para garantizar la resolución unívoca de los nombres, de esta manera los usuarios puedan encontrar todas las direcciones IP sin ser repetidas.
