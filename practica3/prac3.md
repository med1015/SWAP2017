# Practica 3

## Instalacion y configuracion de la nueva maquina balanceadora nginx.


Tal y como se puede ver en la siguiente imagen se ha creado una maquina balanceadora y se ha instalado Nginx para ello:

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/install&startNginx.png)

## configuracion del balanceador Nginx para distribuir las peticiones a los dos servidores apaches, con las condiciones por defecto "weight = 1" :

tal y como se puede ver en la siguiente imagen.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/configNginx.png)

### resultado para la configuracion por defecto: 
![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/balanceadorSimple.png)

## configuracion del balanceador Nginx para distribuir las peticiones a los dos servidores apaches, con las condiciones "weight = 1" para la maquina1 y "weight=2" para la maquina2 :

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/configBalanceWeight.png)

### resultado para la configuracion con pesos diferentes "weight=1" para la maquina1 y "weight=2" para la maquina2. 

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/balanceWeight.png)

## configuracion del balanceador Nginx para distribuir las peticiones a los dos servidores apaches poniendo restriccion en la IP :

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/configBalanceIpHash.png)

### resultado para la configuracion con IP_HASH
![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/balanceIpHash.png)

## De la misma forma vamos a crear una nueva maquina y configurar el balanceador Haproxy para distribuir las peticiones a los dos servidores apaches, con las condiciones por defecto :
tal y como se puede ver en la siguiente imagen.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/confighaproxy.png)

### resultado para la configuracion por defecto: 
![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/haproxySimple.png)

## A continuacion vamos a someter nuestros balanceadores a un test de stress usando la heramienta AB de Apache desde la maquina anfitriona:

### test de stress para Nginx 100000 peticiones con una concurrencia de 100 con la orden "ab -n 100000 -c 100 http://192.168.1.84/index.html ": 

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/abNginx1png.png)

## A continuacion vamos a someter nuestros balanceadores a un test de stress usando la heramienta AB de Apache desde la maquina anfitriona:

### test de stress para Haproxy 100000 peticiones con una concurrencia de 500 con la orden "ab -n 100000 -c 500 http://192.168.1.85/index.html ": 

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica3/abHaproxy.png)
