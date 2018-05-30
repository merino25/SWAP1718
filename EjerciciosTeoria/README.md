# Ejercicios de Clase SERVIDORES WEB DE ALTAS PRESTACIONES. UGR

## 1.Ejercicio Tema 1.

### Buscar información sobre las tareas o servicios web para los que se usan más los programas que comentamos al principio de la sesión:

**Apache:** El servidor HTTP Apache es un servidor web HTTP de código abierto, para plataformas Unix (BSD, GNU/Linux, etc.), Microsoft Windows, Macintosh y otras, que implementa el protocolo HTTP/1.1

**Nginx:** es un servidor web de código abierto que, desde su éxito inicial como servidor web, ahora también es usado como proxy inverso, cache de HTTP, y balanceador de carga.

**Thttpd:**  es un servidor web de código libre disponible para la mayoría de las variantes de Unix.

Se caracteriza por ser simple, pequeño, portátil, rápido, y seguro, ya que utiliza los requerimientos mínimos de un servidor HTTP. Esto lo hace ideal para servir grandes volúmenes de información estática.

**Cherokee:** es un servidor web multiplataforma.2​ Su objetivo es ser rápido y completamente funcional, sin dejar de ser liviano comparado con otros servidores web.

Es muy útil a la hora de administrar múltiples servidores web, por lo cual es ideal para ser utilizado en sistemas orientados a proveer de hosting y servicios de alojamiento compartido.

**Node.js:** es un entorno en tiempo de ejecución multiplataforma, de código abierto, para la capa del servidor (pero no limitándose a ello) basado en el lenguaje de programación ECMAScript, asíncrono, con I/O de datos en una arquitectura orientada a eventos y basado en el motor V8 de Google. Fue creado con el enfoque de ser útil en la creación de programas de red altamente escalables, como por ejemplo, servidores web.

## 2.Ejercicios Tema 2

### Ejercicio T2.1: Calcular la disponibilidad del sistema si tenemos dos réplicas de cada elemento (en total 3 elementos en cada subsistema).

Vamos a ponernos siempre en el peor caso para este cálculo, que comprendería el hecho de que los componentes fuesen fallando de forma sucesiva uno tras otro.

Para estudiar este porcentaje con 1 única unidad de cada componente: `As = Ac1 * Ac2 * Ac3 * ... * Acn`

La disponibilidad inicial equivale a: `As = 85% * 90% * 99'9% * 98% * 85% * 99% * 99'99% * 95% = 59'86%`


Ahora bien con componentes replicados, el valor de disponibilidad aproximada de éste sistema equivale a la siguiente ecuación: `As = Ac1 + ( (1 - Ac1) * Ac2 )`

Si replicamos el componente web la disponibilidad sería:
`As = 85% + ( (1 - 85%) * 85% ) = 97'75%`


Con 3 elementos del subsistema:
COMPONENTE 
Web        --> 99'6625%
App        --> 99'9%
Database   --> 99'999999%
DNS        --> 99'9992%
Firewall   --> 99'6625%
Switch     --> 99'9999%
Data Center--> 99'999999%
ISP	       --> 99'9875%
TOTAL	   --> 99'2135%

### Ejercicio T2.2: Buscar frameworks y librerías para diferentes lenguajes que permitan hacer aplicaciones altamente disponibles con relativa facilidad. Como ejemplo, examina PM2 https://github.com/Unitech/pm2 que sirve para administrar clústeres de NodeJS.

MySQL Router para balancear bases de datos MySQL 

### Ejercicio T2.3: ¿Cómo analizar el nivel de carga de cada uno de los subsistemas en el servidor? Buscar herramientas y aprender a usarlas.

Ejecutando `top` en la terminal, nos muestra el uso de la memoria y procesador.

El comando linux `df`  nos informa acerca del espacio total, ocupado y libre en nuestro sistema.


### Ejercicio T2.4: Buscar ejemplos de balanceadores software y hardware (productos comerciales). Buscar productos comerciales para servidores de aplicaciones. Buscar productos comerciales para servidores de almacenamiento.

Balanceador Software: Haproxy
Balanceador Hardware: Local Director (Cisco), BigIP (F5)
Servidor de almacenamiento: Balanceador de carga Barracuda
Balanceador de aplicaciones: LoadMaster de KEMP


## 3.Ejercicios Tema 3

### Ejercicio T3.1: Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el enrutamiento del tráfico de un servidor para pasar el tráfico desde una subred a otra.

Con el Comando route tanto para linux como windows

### Ejercicio T3.2: Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el filtrado y bloqueo de paquetes.

Linux: con la configuración de nuestro cortafuegos con iptables.
Windows: con el cortafuegos de windows

## 4.Ejercicios Tema 4

### Ejercicio T4.1: Buscar información sobre cuánto costaría en la actualidad un mainframe. Comparar precio y potencia entre esa máquina y una granja web de unas prestaciones similares.
-

### Ejercicio T4.2: Buscar información sobre precio y características de balanceadores hardware específicos. Compara las prestaciones que ofrecen unos y otros.
-

### Ejercicio T4.3: Buscar información sobre los métodos de balanceo que implementan los dispositivos recogidos en el ejercicio 4.2

Van desde el mas simple, round-robin hasta los mas sofisticados vistos en el tema

### Ejercicio T4.4: Instala y configura en una máquina virtual el balanceador ZenLoadBalancer.
-
### Ejercicio T4.5: Probar las diferentes maneras de redirección HTTP. ¿Cuál es adecuada y cuál no lo es para hacer balanceo de carga global? ¿Por qué?

301 y el 302:
301 – Moved Permanently: la página solicitada por el agente de usuario estará disponible de manera permanente bajo la URL redireccionada. La antigua URL será, por lo tanto, inválida.
302 – Moved Temporarily: la página solicitada por el agente de usuario está temporalmente disponible bajo la nueva URL. A diferencia de la redirección 301, la antigua dirección sigue siendo válida.

A diferencia de la redirección 301, el código de estado 302 le comunica al crawler que la URL original debe seguir siendo indexada.

### Ejercicio T4.6: Buscar información sobre los bloques de IP para los distintos países o continentes. Implementar en JavaScript o PHP la detección de la zona desde donde se conecta un usuario
-
### Ejercicio T4.7: Buscar información sobre métodos y herramientas para implementar GSLB (global server load balancing).
-
## 5.Ejercicios Tema 5

### Ejercicio T5.1: Buscar información sobre cómo calcular el número de conexiones por segundo. 
Utilizando Apache, `apache2ctl status | grep request`


### Ejercicio T5.2: Revisar los análisis de tráfico que se ofrecen en: http://bit.ly/1g0dkKj Instalar wireshark y observar cómo fluye el tráfico de red en uno de los servidores web mientras se le hacen peticiones HTTP.
-
### Ejercicio T5.3: Buscar información sobre características, disponibilidad para diversos SO, etc de herramientas para monitorizar las prestaciones de un servidor. Para empezar, podemos comenzar utilizando las clásicas de Linux:top, vmstat, netstat
**Netdata** es una aplicación gratuita y de código abierto desarrollada para ofrecer a los usuarios un monitor en tiempo real del rendimiento de un sistema Linux,
**iStat Menus** esta aplicación concentra toda la información (incluso aquella que no da Monitor de Actividad, como la temperatura que los sensores de cada componente proporciona) en varios menús que se colocan en la barra superior de OS X.

## 6.Ejercicios Tema 6

## Ejercicio T6.1: Aplicar con iptables una política de denegar todo el tráfico en una de las máquinas de prácticas. Comprobar el funcionamiento. Aplicar con iptables una política de permitir todo el tráfico en una de las máquinas de prácticas. Comprobar el funcionamiento.
Bloqueamos todo con:

```
iptable -F
iptables -P INPUT DROP
iptables -P OUTPUT DROP
iptables -P FORWARD DROP
```

Cuando denegamos todo el tráfico no nos permite hacer ping al resto de máquinas servidoras ni a internet.

Permitimos todo:

```
iptables -F
iptables -I INPUT -j ACCEPT
```

Volvemos a tener conexión.

### Ejercicio T6.2: Comprobar qué puertos tienen abiertos nuestras máquinas, su estado, y qué programa o demonio lo ocupa.
-
### Ejercicio T6.3: Buscar información acerca de los tipos de ataques más comunes en servidores web (p.ej. secuestros de sesión). Detallar en qué consisten, y cómo se pueden evitar.
**Ataques de inyección:**, más específicamente sqli (Structured Query Language Injection) es una técnica para modificar una cadena de consulta de base de datos mediante la inyección de código en la consulta.

**DDoS:** La Denegación de Servicio consiste en congelar el funcionamiento de un sitio web. Estos son los intentos de inundar un sitio con solicitudes externas, por lo que ese sitio no podría estar disponible para los usuarios reales. Los ataques de denegación de servicio por lo general se dirigen a puertos específicos, rangos de IP o redes completas, pero se pueden dirigir a cualquier dispositivo o servicio conectado.

**Fuerza Bruta:** intenta “romper” todas las combinaciones posibles de nombre de usuario + contraseña en una página web. Los ataques de fuerza bruta buscan contraseñas débiles para ser descifradas y tener acceso de forma facil.
**Cross Site Scripting:** inyectar scripts maliciosos en lo que serían sitios web inofensivos. Debido a que estos scripts parecen provenir de sitios web de confianza, el navegador de los usuarios finales casi siempre ejecuta la secuencia de comandos, la concesión de los piratas informáticos el acceso a la información contenida en las cookies o tokens de sesión utilizados con ese sitio. El XSS generalmente se utiliza para obtener acceso de un usuario de la cuenta.

**
## 7.Ejercicios Tema 7

### Ejercicio T7.1: ¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 0 a partir de dos discos de 100 GB y 100 GB?
Sumamos los discos:
100GB  + 100 GB = 200 GB
### ¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 0 a partir de tres discos de 200 GB cada uno?
Sumamos los discos:

200 GB  + 200 GB + 200 GB = 600GB
### Ejercicio T7.2: ¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 1 a partir de dos discos de 100 GB y 100 GB? 
100GB es RAID1 es espejo.
### ¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 1 a partir de tres discos de 200 GB cada uno?
200GB es RAID1 es espejo.
# Ejercicio T7.4: Buscar información sobre los sistemas de ficheros en red más utilizados en la actualidad y comparar sus características. Hacer una lista de ventajas e inconvenientes de todos ellos, así como grandes sistemas en los que se utilicen. Configurar en una máquina virtual un servidor NFS. Montar desde otra máquina virtual en la misma subred la carpeta exportada y comprobar que ambas pueden acceder a la misma para lectura y escritura.

**SMB/CIFS:** Es el sistema nativo de Windows.
Permite navegar por los recursos ofrecidos y está orientado al funcionamiento en LAN.

**NFS:** Es el sistema nativo de Unix.
No está pensado para navegar por los recursos y funciona en WAN.

**Coda:** El cliente guarda de forma local los ficheros de trabajo, para asegurar la disponibilidad cuando no existe conexión de red.

**Intermezzo:** Inspirado en Coda pero diseñado de nuevo.

**Lustre:** Nuevo desarrollo destinado a supercomputación. Para grandes clusters o procesadores masivamente paralelos (MPP).
