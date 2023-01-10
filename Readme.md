# Redes Virtuales Azure
*Diciembre 21 de 2022*, Ramón Peinado Ruiz



A continuación disponemos de una guía para la realización de una red virtual en Azure la cual constara con 2 maquinas virtuales las cuales se podran hacer ping entre ellas.

### PASO 1: Creacion de la RED

Accedemos a **All Services -> Networking -> Virtual Network** y creamos nuestra red a nuestro gusto

<img src="/img/1ºimagenn.png" alt="1ºimagenn" style="zoom: 80%;" />



| CONFIG                       | VALOR       |
| ---------------------------- | ----------- |
| Nombre                       | vnet1       |
| Espacio Direcciones          | 10.1.0.0/16 |
| Suscripción                  | Suscripción |
| Grupo de Recursos            | RGvnet      |
| Ubicación                    | East EEUU   |
| Subred - Nombre              | default     |
| Rango de dirección de subred | 10.1.0.0/24 |

<img src="/img/2ºimagenn.png" alt="2ºimagenn" style="zoom: 80%;" />



<img src="/img/4ºimagenn.png" alt="4ºimagenn" style="zoom: 80%;" />

Revisamos y creamos tras configurar los parámetros.

### PASO 2: Creación Maquinas

Accedemos a **All Services -> Compute -> Virtual Machine** y creamos las maquinas con los siguientes parámetros:

**BASICS:**

<img src="/img/5ºimagenn.png" alt="5ºimagenn" style="zoom: 80%;" />

**NETWORKING**

<img src="/img/6ºimagenn.png" alt="6ºimagenn" style="zoom: 80%;" />

La 2da maquina se crea con los mismos parámetros pero con  un distinto nombre

### PASO 3: Conexión entre maquinas

<img src="/img/7ºimagenn.png" alt="7ºimagenn" style="zoom: 80%;" />

Si probamos la conexión tal cual la petición del ping no se llevara a cabo debido al firewall, hemos de ejecutar un comando para activar la regla y poder realizar pings.

Introducimos el siguiente comando:

"New-NetFirewallRule –DisplayName “Allow ICMPv4-In” –Protocol ICMPv4"

<img src="/img/8ºimagenn.png" alt="8ºimagenn" style="zoom: 80%;" />



Comprobamos los pings entre las maquinas:

myvm1 a vm2

<img src="/img/9ºimagenn.png" alt="9ºimagenn" style="zoom: 80%;" />

vm2 a myvm1

<img src="/img/10ºimagenn.png" alt="10ºimagenn" style="zoom: 80%;" />
