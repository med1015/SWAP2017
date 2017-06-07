# Practica 6  Discos en RAID


##  realizar la configuración de dos discos en RAID 1 bajo Ubuntu, automatizando el montaje del dispositivo creado al inicio del sistema. 

Vamos a crear 2 discos más, que serán el /dev/sdb y el /dev/sdc
![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/creacionDeDiscos.png)

Ahora arrancamos la máquina y entramos para instalar el software necesario para configurar el RAID1

En mi caso no ha sido necesario porque el software mdadm ya esta instalado.

A continuación vamos a listar las particiones para ver que identificador tiene los nuevos discos. 

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/fdisk-l.png)

en la imagen anterior podemos ver que los identificadores de los nuevos discos
son sdb y sdc.

Ahora ya podemos crear el RAID 1, usando el dispositivo /dev/md0, indicando el
número de dispositivos a utilizar , así como su ubicación: 

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/mdadmDevices.png)

Ahora que hemos creado el dispositivo RAID1, a formatear nuestro dev/md0 con mkfs que incializa el dispositivo de almacenamiento con el formato ext2 para luego crear el directorio en el que se montara la unidad del RAID:

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/mkfs&mount.png)

y comprobamos que le montaje se ha realizado con exito:

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/comprobarMount.png)

y comprobar el estado del Raid1 tambien:

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/comprobarMdadm.png)

Ahora tenemos que hacer que el montaje se haga de forma automatica en el arranque de la maquina y para eso tenemos que configurar el fichero /etc/fstab y añadir la línea correspondiente para montar automáticamente dicho dispositivo para aquello vamos necesitar el identificador del dispositivo:

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/listDev.png)

Ahora que tenemos nuestro id podemos anadir la linea correspondiente en nuesrto fichero tal y como se puede ver en la siguiente imagen:

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/nano.png)

Ahora reiniciamos la maquina y comprobamos que el montaje se hace de forma automatica:

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/comprobarMountDespues.png)

## Simular un fallo en uno de los discos del RAID (mediante comandos con el mdadm), retirarlo “en caliente”, comprobar que se puede acceder a la información que hay almacenada en el RAID, y por último, añadirlo al conjunto y comprobar que se reconstruye correctamente.

 simulando un fallo en uno de los discos:

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/simuloFallo.png)

 retirar “en caliente” el disco que está marcado como que ha fallado:
 
 ![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/remove.png)
  
añadir, también “en caliente”, un nuevo disco que vendría a reemplazar al disco que hemos retirado: 

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica6/addDevice.png)
