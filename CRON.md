# CRON

### ¿Qué es CRON?
Es un administrador de procesos en segundo plano (demonio) que se ejecuta
cuando arranca el sistema. Comprueba si existe alguna tarea (job) para ser
ejecutado de acuerdo a la hora configurada en el sistema.  

### ¿Qué es CRONTAB?
Es un archivo de texto que contiene la lista de comandos que se deben ejecutar.
Crontab verificará la fecha y hora en que se debe ejecutar el script o comando,
los permisos de ejecución y lo ejecutará en segundo plano.  


## Ejercicios CRON practicos

###  30 * * * * /home/prueba.sh
Todos los días cada hora a los 30 minutos (12:30,13:30...) se ejecuta el script prueba
### 30 20 * * * /home/prueba.sh
Todos los días a las 20:30 se ejectua el script
### 30 20 * * 1-5 /home/prueba.sh
Todos los dias de Lunes a Viernes a las 20:30 se ejecuta el script
### 30 20 * * 2,4 /home/prueba.sh
Todos los martes y jueves a las 20:30 
### 30 20 10,20 * * /home/prueba.sh
Todos los 10 y 20 días de cada mes a las 20:30 se ejecuta el script.
### */15 * * * * /home/prueba.sh
Todos los días cada 15 minutos se ejecuta el script.
### @daily /home/prueba.sh
Todos los días se ejecuta el script.
### @mountly /etc/backup.sh 
Todos los meses se ejecutaria el script si estuviese bien escrito.
### 30 20 * * Mon-Fri /etc/test.sh
Todos los días de Lunes a Viernes a las 20:30 se ejecuta el script.
### 1 0 1-7 * * [ "$(date '+%a')" = "Fri" ] && /etc/backup.sh
Hace una comparación del dia de la semana con los establecido en este caso viernes y lo imprime en backup.sh todos los días del 1-7 de cada mes a las 00:01.  
## CRON Ejercicio 7

Lo primero que tenemos que hacer es iniciar el CRON al ser la primera vez que utilizamos el CRONTAB tendremos que iniciarlo con el comando "crontab -l" para comprobar que no hay ningún CRONTAB iniciado. Para editarlo necesitamos el comando "crontab -e" y nos abrira un fichero en el cual debemos poner la linea de ejecucción.   
![Primera Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/Crontab_1.PNG)
Ponemos en la ultima linea cuando queremos que se ejecute la tarea.

Una vez hecho esto, tenemos que crear el script donde queremos guardar los contenidos generados por el CRONTAB.  
![Segund Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/crontab_2.PNG)

Este es el resultado, utilizando comando cat text.txt nos aparecera la siguiente linea.
![Tercera Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/crontab_3.PNG)

## Ejercicio 8

En este ejercicio necesitaremos entrar de nuevo en el crontab -e y en el escribimos los siguiente.
![Cuarta Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/crontab_4.PNG)
Esto lo que nos ejecutará lo siguiente: todo los martes cada 15 minutos nos creará un archivo comprimido en la carpeta especificada en nuestro caso Copias.

Y este es el resutado:  
![Quinta Captura](https://raw.githubusercontent.com/Gaizkaja/dweb_AWS/main/crontab_5.PNG)

