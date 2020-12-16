# Documentacion AWS Instancia
#### Lo primero que debemos hacer es crear una instancia una que hemos iniciado nos aparecera la siguiente pantalla 
Aqui tenemos que elegir l sistema operativo en nuestro caso Ubuntu con la ultima version disponible 20.04 LTS.

![Primera Captura](img/Cap1.png)
#### Seguiremos el Wizard que nos ofrece AWS y en nuestro caso utilizaremos las opciones gratuitas.

Como somos estudiantes nos acojeremos a las opciones gratuitas.
![Segunda Captura](img/Cap2.png)

#### Saltamos unas pantallas hasta la 4 donde cambiaremos el almacenamiento hasta los 30GB que nos oferta gratuitamente.

Añadimos los maximo que podemos gratuitamente.

![Tercera Captura](img/Cap3.png)

#### Ahora nos saltamos el paso de los tags y llegamos al apartado de Security.

En esta pantalla no sera necesario cambiar nada lo dejaremos todo por defecto.

![Cuarta Captura](img/Cap4.png)

#### Y por ultimo en la pantalla final del Wizard de creacion de la instacia lanzaremos dicha instacia y crearemos un fichero las claves privadas

Aqui elegimos un nombre que recordemos y que sea corto para luego entrar desde Git_bash no tengamos que poner una linea largisima. Y por último aqui lanzamos la instacia.

![Quinta Captura](img/Cap5.png)

#### Para saber que poner debemos ir al apartado conectar para que nos aparezca la siguiente pantalla 

Seguimos los pasos aqui referidos.

![Sexta Captura ](img/Cap9.png)

#### Una vez que tenemos la clave privada ya creada nos iremos a la terminal desde donde nos conectaremos via SSH.

Aqui lo que deberemos hacer es cambiar permisos al archivo que hemos creado nosotros le pondremos 400 con el comando *chmod 400 [nombre del archivo]*

![Septima Captura ](img/Cap6.png)

#### Ahora nos conectaremos por ssh

Desde la linea "*ssh -i "Claves_Privadas.pem" ubuntu@ec2-3-86-97-98-compute-1.amazonaws.com*" nos conectamos por ssh.
Le ponemos si para que nos deje continuar.

![Octava Captura ](img/Cap7.png)

#### Una vez hecho todo ya estariamos dentro de la maquina virtual de Ubuntu

![Novena Captura ](img/Cap8.png)

#### Por último pero no menos importante nos vamos a la pantalla principal de las instacias.
Aqui deberemos Detener la instancia para que en nuestro caso no se nos gaste el saldo.

# Ahora instalaremos unos paquetes en el servidor

## Empezaremos por instalar Apache

Lo primero que deberemos hacer es iniciar la instancia al igual que hicimos anteriormente. Con el comando *sudo apt install apache2*, comprobamos que estar funcionando con el comando *sudo systemctl status apache2*.

![Decima Captura ](img/Cap_Apache1.png)
![Undecima Captura ](img/Cap_Apache2.png)

## Visualizar desde navegador

Deberemos ir al apartado de seguridad de nuestra instacia en la consola de AWS y añadir una nueva regla que sera la de HTTP con el puerto 80 para poder conectar desde el navegador.

![Duodecima Captura ](img/Cap_Apache5.png)

Y esto nos aparecera si hemos configurado correctamente.

![Decimotercera Captura ](img/Cap_Apache3.png)

Ahora comprobamos desde el navegador y nos deberia aparecer lo siguiente.

![Decimocuarta Captura ](img/Cap_Apache4.png)

## Ahora instalaremos MySQL

### Es un proceso muy sencillo

Al igual que con Apache solo necesitaremos dos comando *sudo apt install mysql-server* y *sudo systemctl status mysql* esta vez lo deberemos hacer desde root ya que nos pide una contraseña por temas de seguridad y Ubuntu no trae por defecto lo cual nos lleva a que no nos deje comprobar el status.

![Decimoquinta Captura ](img/Cap_Mysql1.png)
![Decimasexta Captura ](img/Cap_Mysql2.png)

Por si nos salta algun fallo tenemos que un update antes de instalar MySQL

## Ahora instalaremos PHP

Al igual que con Apache,MySQL solo necesitaremos dos comando *sudo apt-get install php7.4 libapache2-mod-php7.4 php7.4-cli php7.4-mysql php7.4-gd php7.4-imagick php7.4-recode php7.4-tidy php7.4-xmlrpc* y *sudo systemctl status php7.4-fpm* esta vez lo deberemos hacer desde root ya que nos pide una contraseña por temas de seguridad y Ubuntu no trae por defecto lo cual nos lleva a que no nos deje comprobar el status.

![Decimaseptima Captura ](img/Cap_PHP1.png)
![Decimaoctava Captura ](img/Cap_PHP2.png)

## Ahora instalaremos FTP

Al igual que con Apache,MySQL,PHP solo necesitaremos dos comando *sudo apt-get install vsftpd* y *sudo systemctl status vsftpd* esta vez lo deberemos hacer desde root ya que nos pide una contraseña por temas de seguridad y Ubuntu no trae por defecto lo cual nos lleva a que no nos deje comprobar el status.

![Decimanovena Captura ](img/Cap_Vsftp1.png)
![Vigesima Captura ](img/Cap_Vsftp2.png)

# Ahora configuraremos una IP Elastica en la consola AWS

## ¿Qué es y para qué sirve una IP Elástica?

Las direcciones IP elásticas son direcciones IPv4 estáticas diseñadas para la informática en la nube dinámica.

## Es un proceso realmente sencillo de configurar

Debemos ir al apartado de seguridad IP elastica, asignamos un IP Elastica

![Vigesimprimera Captura ](img/Cap_IpElastic.png)

![Vigesimosegunda Captura ](img/Cap_IpElastic1.png)

Lo unico que debemos configurar es el ultimo apartado que tendremos que poner nuestra instacia 

![Vigesimotercera Captura ](img/Cap_IpElastic2.png)




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

![Vigesimocuarta Captura ](img/Cap_DNS1.png)

1. Dirección IP de nuestro dominio 
2. Nombre asociado a la dirección de correo.
3. Lo rellenamos para evitar el uso indebido del correo electronico.
