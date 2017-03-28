## Ejercicio 1:

    Calcular la disponibilidad del sistema si tenemos dos réplicas de cada elemento :
    
    > Con un elemento en cada subsistema:
    
    | Component | Availibility |
    | :-------: | :----------: |
    | Web       | 85%          |
    | APP       | 90%          |
    | D.B       | 99,9%        |
    | DNS       | 98%          |
    | Firewall  | 85%          |
    | Switch    | 99%          |
    |Data Center| 99,99%       |
    | ISP       | 95%          |
    
    ##### Disponibilidad: 59,866% 
    
    > Con dos elementos en cada subsistema:
    
    | Component | Availibility |
    | :-------: | :----------: |
    | Web       | 97,75%       |
    | APP       | 99%          |
    | D.B       | 99,9999%     |
    | DNS       | 99,96%       |
    | Firewall  | 97,75%       |
    | Switch    | 99,99%       |
    |Data Center| 99,99%       |
    | ISP       | 99,75%       |
    
    ##### Disponibilidad: 94,30% 
    
    > Con tres elementos en cada subsistema:
    
    | Component | Availibility |
    | :-------: | :----------: |
    | Web       | 99,6625%     |
    | APP       | 99,9%        |
    | D.B       | 99,9999999%  |
    | DNS       | 99,9992%     |
    | Firewall  | 99,6625%     |
    | Switch    | 99,9999%     |
    |Data Center| 99,999999%   |
    | ISP       | 99,9875%     |
    
    ##### Disponibilidad: 99,2135% 
    
## Ejercicio 2:
    Buscar frameworks y librerias para diferentes lenguajes que permitan hacer aplicaciones altamente disponibles con relativa facilidad. 

    > Symfony
    > Django
    > Flask
    > Sinatra
    
## Ejercicio 3:
    Como analizar el nivel de carga de cada uno de los subsistemas en el servidor?
    
    > Nagios
    > Munin
    > Cacti

## Ejercicio 4:
    Ejemplos de balanceadores software y hardware (productos comerciales).
    
    > balanceadores software:
        Haproxy
        Nginx
        Pen
    
    > Balanceadores Hardware:
        LoadMaster 2600
        Barracuda Load Balancer 640
