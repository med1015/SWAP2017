# Practica 2

## Probar el funcionamiento de la copiade archivos por ssh.


Tal y como se puede ver en la siguiente imagen se ha creado un tar con los ficheros locales en le equipo remoto usando el comando: 
* tar czf - SWAP2017 | ssh medmol-2@192.169.1.100 'cat > /tar.tgz' *

y continuacion podemos ver que el tar ha sido creado en la maquina remota metiendonos en la maquina remota via ssh y luego con el comando ls para verlo.

ter_ssh.png

## Clonado de una carpeta entre las dos maquinas.

Para realizar el clonado de la carpeta /var/www vamos a usar la herramienta rsync que nos permite realizar el clonado de forma sencilla indicando la carpeta a clonar y la maquina de donde traimos los ficheros y donde se van a clonar todo esto con el comando:
* rsync -avz -e ssh medmolato@192.169.1.101:/var/www /var/www/ *

tal y como se puede ver en la siguiente imagen.

rsync_cop_fich.png

## Configuracion de ssh para acceder sin que solicite contrasena:

### paso1:
Mediante ssh-keygen vamos a generar la clave con la opcion -t para elegir el tipo de clave tal y como se puede ver en la siguiente imagen:

ssh_keygen.png

### paso2 :
Ahora vamos a copiar la clave generada en la maquina a la que queremos acceder con el comando:
* ssh-copy-id medmolato@192.169.1.101 *

y a continuacion comprobamos que ya no nos pide la contrasena cuando queremos acceder a la maquina remota.

ssh_copy_rsa.png

## Programar tareas con crontab

Vamos a anadir una linea de comando en el fichero etc/crontab para automatizar el clonado de la carpeta /var/wwww/ cada 3 min:

* */3 * * * * rsync -avz -e ssh medmolato@192.169.1.101:/var/www/ /var/www/

tal y como se puede ver en la siguiente imagen:

cron.png

las siguientes imagen nos permite comprobar que los ficheros han sido clonados correctamente:

#### contenido maquina1:

fich_maqu1.png

#### contenido maquina2: antes y despues de la ejecucion del cron:

fich_maqu2.png
