# Practica 4 Asegurar la granja web

## Instalar un certificado SSL autofirmado para configurar el acceso por HTTPS

Tal y como se puede ver en la siguiente imagen se ha configurado el fichero defaults-ssl.conf del apache para anadir el certificado autofirmado:

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica4/configDefault-ssl.png)

### hacemos un reload al servicio apache.

tal y como se puede ver en la siguiente imagen.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica4/reloadApache2.png)

### Ahora comprobamos que el certificado autofirmado funciona de forma correcta

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica4/testHttps.png)

##  Configuración del cortafuegos

### vamos a crear un script que nos permite el acceso al sevidor web por HTTP y HTTPS:

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica4/scriptCortaFuego.png)

### A continuacion vamos a denegar el acceso por http y habilitar el HTTPS para ver que las reglas del cortafuegos funcionan correctamente.

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica4/testIptables.png)

###  Tal y como se puede ver en la imagen anterior el acceso por HTTP se queda pillado sin embargo el de HTTPS nos permite el acceso.

### En la siguiente imagen volvemos a habilitar el HTTP 

![imagen](https://github.com/med1015/SWAP2017/blob/master/practica4/testIptables2.png)

