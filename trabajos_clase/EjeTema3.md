# Ejercicio 1:

## Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el enrutamiento del tráfico de un servidor para pasar el tráfico desde una subred a otra.

### LINUX:
Para configurar el enrutamiento del tráfico de un servidor podemos usar la herramienta ROUTE por ejemplo el siguiente comando indica que los paquetes con destino la 192.168.0.0/24 tienen que pasar por la pasarela 112.65.123.3.

* route add -net 192.168.0.0/24 gw 112.65.123.3 *

### WINDOWS :

Para configurar el enrutamiento del tráfico de un servidor podemos usar la herramienta NetRouteView que tiene interfaz grafica bastante intuitiva de usar tal y como se puede ver en la siguiente imagen:

![imagen](https://github.com/med1015/SWAP2017/blob/master/trabajo_clase/netrouteview.png)
