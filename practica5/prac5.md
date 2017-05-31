# Practica 5  Replicación de bases de datos MySQL


##  Crear una BD con al menos una tabla y algunos datos.

Vamos a crear una base de datos en la maquina uno con el nombre "contactos" con una tabla datos que tiene 2 campos el primero 'nombre' y otro 'tlf'.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/CreateDB.png)

A continuacion vamos a insertar algunos datos y mostrarlos para asegurarnos que han sido insertado correctamente.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/InsertSelectSql.png)

## Realizar la copia de seguridad de la BD completa usando mysqldump.

Vamos a clonar nuestra base de datos usando la herramienta mysqldump, pero primero antes de hacer la copia de seguridad en el archivo vamos a bloquear la base de datos con el comando FLUSH TABLES WITH READ LOCK mientras hacemos el clonado para que no haya perdida de datos y luego volvemos a desbloquear con el comando UNLOCK TABLES.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/lockCloneUnlock.png)

## Restaurar dicha copia en la segunda máquina (clonado manual de la BD).

A continuacion tenemos que llevar el fichero clonado a nuestra maquina 2 con 'scp' y hacer el despliegue de la BD.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/transContactos.png)

y ahora hacer el despliegue de los datos en la base datos previamente creada.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/repBDmaq2.png)

la siguiente imagen nos muestra que la base de datos ha sido replicada con exito.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/comparacion.png)

##  Realizar la configuración maestro-esclavo de los servidores MySQL para que la replicación de datos se realice automáticamente.

Lo primero que debemos hacer es la configuración de mysql del maestro. Para ello editamos, como root, el /etc/mysql/mysql.conf.d/mysqld.cnf para
realizar las modificaciones necesarios tal y como se ven en la siguiente imagen.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/configMaq1.png)

A continuacion vamos a crear el usuario esclavo en la maquina 1 y darle los privilegios para poder hacer las replicas desde la maquina 2.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/userMaestro.png)

Ahora volvemos a la máquina 2 'esclava', entramos en mysql y le damos los datos del maestro.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/userEsclavo.png)

Ahora nos aseguramos de que todo funciona perfectamente y que el esclavo
no tiene ningún problema para replicar la información, nos vamos al esclavo y con la siguiente orden:
mysql> SHOW SLAVE STATUS\G
revisamos si el valor de la variable “Seconds_Behind_Master” es distinto de “null”. En ese caso, todo estará funcionando perfectamente.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/esclavoSeconds.png)

la siguiente imagen nos muestra que la base de datos ha sido replicada de forma automatica con exito.


![imagen](https://github.com/med1015/SWAP2017/blob/master/practica5/maestroEsclavo.png)


