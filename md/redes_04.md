# 4. Fundamentos lógicos de las redes
Para que una red funcione correctamente, no basta con conectar cables o activar el Wi-Fi. Detrás hay una estructura lógica que permite que cada dispositivo tenga una dirección única, sepa a quién puede hablar directamente, y cuándo necesita ayuda para salir a Internet. Esa lógica es la que vamos a descubrir en esta unidad.

## 4.1 ¿Cómo se identifican los dispositivos en una red?
Cada dispositivo conectado a una red necesita una identificación única dentro de esa red. Esta identificación se realiza mediante la dirección IP, junto con otros elementos como la máscara de red y el gateway. Estos valores permiten que los dispositivos puedan comunicarse entre sí de forma eficiente y que sepan a quién deben enviar los datos.

### 4.1.1 Dirección IP: qué es y por qué es necesaria
La **dirección IP (Internet Protocol)** es un número que identifica de forma única a cada dispositivo dentro de una red. Funciona como si fuera la dirección postal de una casa: si no tienes dirección, no puedes recibir cartas. Del mismo modo, si un dispositivo no tiene dirección IP, no puede enviar ni recibir datos en una red.

Es importante asignar y gestionar bien las direcciones IP, ya que si dos dispositivos comparten la misma, se produce un conflicto de red que impide su correcto funcionamiento.

Existen dos versiones principales de direcciones IP: IPv4 e IPv6.

#### IPv4
Una dirección IPv4 se representa así:
**Ejemplo:** 192.168.1.25

Está compuesta por **cuatro números separados por puntos**, y cada número puede ir **de 0 a 255**. Internamente, cada uno representa **8 bits**, lo que da un total de **32 bits por dirección IP**. 

Esto permite generar más de 4 mil millones de direcciones únicas. Parece mucho, pero con tantos dispositivos conectados en el mundo (móviles, ordenadores, tablets, relojes, frigoríficos...), ¡se nos han quedado cortas!

#### IPv6
Para solucionar el problema del agotamiento de direcciones IPv4, se creó IPv6, una versión mejorada que permite muchísimas más direcciones.

Una dirección IPv6 se ve muy diferente:
**Ejemplo:** 2001:0db8:85a3:0000:0000:8a2e:0370:7334

Tiene un formato **hexadecimal** (usa letras y números), separada por **dos puntos (:)**. Internamente, usa **128 bits** en lugar de 32. Esto permite un número tan grande de direcciones, que prácticamente nunca se acabarán. El número total es de 2^128 direcciones: una cifra con 39 dígitos, ¡prácticamente inagotable!

Algunas redes ya lo están utilizando, especialmente en grandes proveedores y servicios como Google o Facebook. Pero IPv4 aún se sigue usando muchísimo, sobre todo en redes locales. Por eso es importante conocer ambas versiones.

### 4.1.2 Máscara de red
La **máscara de red** es un número que se utiliza junto con la dirección IP para determinar qué parte de la IP identifica a la red y qué parte identifica al dispositivo (host) dentro de esa red.

Es fundamental para que un equipo sepa si otro está en su misma red local (puede comunicarse directamente) o en otra red (necesita usar el gateway).

Tiene el mismo formato que una dirección IP:
**Ejemplo:** 255.255.255.0

Esto significa que los tres primeros grupos de números (24 bits) identifican la red, y el último grupo (8 bits) se usa para numerar a los dispositivos dentro de esa red.

**Ejemplo práctico:**
- Dirección IP: 192.168.1.25
- Máscara de red: 255.255.255.0

Con esta máscara, todos los dispositivos que comparten los tres primeros números (192.168.1) estarán en la misma red local, y podrán comunicarse directamente. Si, en cambio, un equipo tiene esta IP: 192.168.2.10, ya no estará en la misma red, porque cambia el tercer número. En ese caso, se necesita usar un gateway para comunicar ambos dispositivos.

**Importante:**
- La máscara no identifica a un dispositivo.
- No se puede repetir en la misma red una máscara incompatible.
- Ayuda a dividir redes grandes en redes más pequeñas, lo que mejora la organización y el rendimiento.

### 4.1.3 Gateway
El **gateway** (también llamado **puerta de enlace**) es la dirección IP del dispositivo que actúa como intermediario entre la red local y otras redes, como por ejemplo, Internet.

Cuando un dispositivo necesita comunicarse con otro que no está en su misma red local, el mensaje debe salir de la red. Para eso, se envía al gateway, que se encarga de reenviarlo al destino correcto.

El gateway suele ser el router de la red.

**Importante:**
- Todos los dispositivos de la red deben tener configurado el mismo gateway (normalmente el router).
- Si no se configura el gateway, el dispositivo no podrá comunicarse con el exterior (solo dentro de la red local).

### 4.1.4 Dirección de red 
La **dirección de red** es una dirección especial que representa a toda una red. No es de un equipo, sino que identifica al conjunto de dispositivos conectados a la misma red. Se calcula usando la dirección IP del dispositivo y la máscara de red. La parte de red queda igual, y la parte de host se pone a ceros.

**Ejemplo:**
- IP del equipo: 192.168.1.25
- Máscara: 255.255.255.0
- Dirección de red: 192.168.1.0

Todos los equipos con IP que empiece por 192.168.1. estarán en la misma red.

### 4.1.5 Dirección de broadcast
La **dirección de broadcast** es una dirección IP especial que se utiliza para enviar un mensaje a todos los dispositivos de una red local al mismo tiempo.

La dirección de broadcast se obtiene tomando:
- La dirección de red (por ejemplo, 192.168.1.0)
- La máscara de red (por ejemplo, 255.255.255.0)
- Y poniendo todos los bits de la parte de host en 1 (es decir, el número más alto posible dentro de la red)

**Ejemplo:**
- *Red:* 192.168.1.0
- *Máscara de red:* 255.255.255.0 (/24). Esto significa que los últimos 8 bits son para los dispositivos (hosts).
- La dirección de broadcast será entonces: 192.168.1.255 

Eso quiere decir que si enviamos un mensaje a 192.168.1.255, todos los dispositivos con IPs desde 192.168.1.1 hasta 192.168.1.254 lo recibirán.

¡IMPORTANTE! No se debe asignar la dirección de broadcast a ningún dispositivo, porque no es un equipo, ¡es una dirección especial!

### 4.1.6 Clases de direcciones IP y notación CIDR
Antes del sistema actual, las direcciones IP se organizaban en clases (A, B y C) según el tamaño de la red y la cantidad de dispositivos que podía albergar. 

Este sistema fue útil inicialmente, pero tenía un problema importante: era muy poco flexible porque cada clase reservaba una cantidad fija de bits para la parte de red y otra para los dispositivos (hosts), y muchas veces se asignaban rangos enormes a redes que solo necesitaban unas pocas direcciones, lo que provocaba desperdicio de IPs. Por ejemplo, una empresa que necesitaba 200 direcciones tenía que usar una red de clase B con más de 65.000.

Aun así, conocer estas clases nos ayuda a entender cómo se estructuran las direcciones IP y por qué existen ciertos rangos reservados.

<table>
    <tr>
        <th>Clase</th>
        <th>Rango de IPs</th>
        <th>Nº de dispositivos disponibles</th>
        <th>Uso común</th>
    </tr>
    <tr>
        <td>A</td>
        <td>1.0.0.0 – 126.255.255.255</td>
        <td>Más de 16 millones</td>
        <td>Grandes redes (ISPs)</td>
    </tr>
    <tr>
        <td>B</td>
        <td>128.0.0.0 – 191.255.255.255</td>
        <td>Hasta 65.534</td>
        <td>Universidades, empresas</td>
    </tr>
    <tr>
        <td>C</td>
        <td>192.0.0.0 – 223.255.255.25</td>
        <td>Hasta 254</td>
        <td>Redes domésticas o pequeñas</td>
    </tr>
    <tr>
        <td>D</td>
        <td>224.0.0.0 a 239.255.255.255</td>
        <td>No se asigna a dispositivos individuales</td>
        <td>Usada para multicast (enviar información a varios dispositivos a la vez).</td>
    </tr>
    <tr>
        <td>E</td>
        <td>240.0.0.0 a 255.255.255.255</td>
        <td>No se asigna a dispositivos actualmente.</td>
        <td>Reservada para investigación y uso futuro (no se usa comúnmente).</td>
    </tr>
</table>

La IP **127.0.0.1 no pertenece a ninguna clase**. Es una dirección especial llamada **localhost** (la usamos para referirnos a nosotros mismos). 

Con el tiempo, el sistema por clases se quedó corto. Por eso se creó una forma más flexible de gestionar direcciones IP: la **notación CIDR (Classless Inter-Domain Routing)**.

CIDR permite especificar con precisión cuántos bits se usan para la red y cuántos para los dispositivos, sin necesidad de encajar en una clase fija. Se representa añadiendo una barra y un número al final de la dirección IP.

**Ejemplo:** 192.168.1.0/24
- Ese /24 significa que los primeros 24 bits se usan para la parte de red, y los restantes (8 bits) para los hosts. Es decir, es equivalente a la máscara 255.255.255.0.

<table>
    <tr>
        <th>Notación CIDR</th>
        <th>Máscara equivalente</th>
        <th>Nº de hosts disponibles</th>
    </tr>
    <tr>
        <td>/24</td>
        <td>255.255.255.0</td>
        <td>254</td>        
    </tr>
    <tr>
        <td>/25</td>
        <td>255.255.255.128</td>
        <td>126</td>        
    </tr>
    <tr>
        <td>/26</td>
        <td>255.255.255.192</td>
        <td>62</td>        
    </tr>
    <tr>
        <td>/30</td>
        <td>255.255.255.252</td>
        <td>2</td>        
    </tr>
</table>

Cuanto mayor es el número tras la barra, menos direcciones están disponibles para hosts (la red es más pequeña).

Gracias a CIDR, es posible crear redes del tamaño exacto que se necesita, sin ajustarse a clases fijas.

📌 En resumen:
- **Sistema por clases:** fijo, limitado y con desperdicio de IPs.
- **CIDR:** flexible, eficiente y el sistema más utilizado actualmente.

## 4.2 Tipos de direcciones IP
Las direcciones IP se pueden clasificar de varias formas, según cómo se usan y cómo se asignan. Conocer estos tipos nos ayuda a entender mejor cómo se organizan las redes y cómo se conectan con el exterior, como por ejemplo, con Internet.

### 4.2.1 Direcciones públicas y privadas

#### IP privadas
Las **direcciones IP privadas** son aquellas que solo se utilizan dentro de redes locales: en una casa, un centro educativo, una empresa, etc. No pueden usarse directamente en Internet.

Por ejemplo, en tu casa, el móvil, el portátil o la impresora usan IPs privadas como: 192.168.1.5 ó 10.0.0.23

Estas IPs las asigna el router y no son visibles desde fuera de la red.

<table>
    <caption>Rangos reservados para IP privadas</caption>
    <tr>
        <th>Clase</th>
        <th>Rango privado</th>
    <tr>
    <tr>
        <td>A</td>
        <td>10.0.0.0 – 10.255.255.255</td>
    </tr>
    <tr>
        <td>B</td>
        <td>172.16.0.0 – 172.31.255.255</td>
    </tr>
    <tr>
        <td>C</td>
        <td>192.168.0.0 – 192.168.255.255</td>
    </tr>
</table>

Cualquier dirección fuera de estos rangos no se considera privada.

#### IP públicas
Las **direcciones IP públicas** son las que se usan para comunicarse a través de Internet. Son únicas a nivel mundial y permiten que los dispositivos sean accesibles desde fuera de la red local.

Por ejemplo, el router de tu casa tiene una IP pública asignada por tu proveedor de Internet (ISP). Desde fuera, se puede acceder a tu red a través de esa dirección.

**Ejemplo de IP pública:** 85.120.45.33

### 4.2.2 Direcciones estáticas vs dinámicas

#### IP estática
Una **IP estática** es una dirección que se asigna manualmente a un dispositivo y permanece fija en el tiempo. Siempre será la misma, aunque se reinicie el dispositivo o se desconecte de la red.

Se usa en casos donde es importante que la IP no cambie, como:
- Servidores
- Impresoras en red
- Cámaras de seguridad

#### IP dinámica
Una **IP dinámica** es una dirección que se asigna automáticamente a un dispositivo cada vez que se conecta a la red. Esta dirección puede cambiar con el tiempo.

La asignación la realiza un **servidor DHCP**, que normalmente es el propio router en redes domésticas.

El **DHCP** ***(Dynamic Host Configuration Protocol)*** es un servicio que se encarga de dar una IP automáticamente a cada dispositivo que se conecta, sin necesidad de configurarla manualmente.
Es como si el router fuera un “repartidor de direcciones” que entrega una IP libre a cada nuevo dispositivo que entra en la red.

En casa, la mayoría de tus dispositivos (móvil, portátil, tablet…) usan IP dinámica gracias al DHCP.

### 4.2.3 Rango de IPs disponibles según la máscara

La máscara de red define cuántas direcciones IP pueden usarse dentro de una red. Cuanto más grande es la red, más bits se reservan para los dispositivos (hosts).

**¿Cómo se calcula?**
- Se parte de una dirección IP y una máscara.
- La máscara indica cuántos bits están dedicados a la red (los primeros) y cuántos a los hosts (los últimos).
- El número de IPs disponibles para dispositivos es:
  - 2^n - 2, donde n es el número de bits para hosts.
  - (Se restan 2: una para la dirección de red y otra para broadcast)

**Ejemplo práctico**
- Dirección IP: 192.168.1.0
- Máscara: 255.255.255.0 → /24
- IP de red: 192.168.1.0
- Broadcast: 192.168.1.255

IPs válidas: de 192.168.1.1 a 192.168.1.254 (254 direcciones disponibles)

# Ejercicios

**1. Comprensión básica (tipo test o respuesta corta)**
- ¿Qué función cumple una dirección IP en una red?
- ¿Qué diferencia hay entre una dirección IP pública y una privada?
- Una dirección IPv4 está formada por:
    - a) 16 bits
    - b) 128 bits
    - c) 32 bits
    - d) 64 bits
- Verdadero o falso (si es falso, justifica la respuesta)    
    - ___ La dirección de broadcast se puede asignar a un dispositivo.
    - ___ El gateway solo se usa dentro de la red local.
    - ___ El rango 10.0.0.0 – 10.255.255.255 es un rango de IP privadas.
    - ___ La máscara de red define cuántos bits se usan para la dirección MAC.

**2. Ejercicios prácticos con IPs (cálculo y análisis)**
- Dada la siguiente información de un dispositivo: dirección IP: 192.168.1.45 y máscara de red: 255.255.255.0
    - a) ¿Cuál es la dirección de red?
    - b) ¿Cuál es la dirección de broadcast?
    - c) ¿Este dispositivo puede comunicarse directamente con uno con IP 192.168.2.20?

- ¿Cuántos hosts (dispositivos) puedes tener en una red con máscara /12? ¿Y con /28?

- ¿Qué dirección IP es válida dentro de esta red? Dirección de red: 172.16.0.0/16 (Justifica tu respuesta)
    - a) 172.16.25.5
    - b) 172.32.0.10
    - c) 172.16.255.254
    - d) 192.168.0.1

**3. Identificación y clasificación**
- Clasifica las siguientes direcciones como privadas o públicas:
    - 10.0.0.5
    - 172.20.15.33
    - 85.23.90.1
    - 192.168.100.100
    - 200.45.0.1

- Clasifica las siguientes IPs según su clase (A, B o C) y especifica el número máximo aproximado de hosts: 
    - 9.12.255.10
    - 150.25.34.7
    - 192.168.2.55

**4. Aplicación de CIDR**
- ¿Cuál es la máscara equivalente a /25? ¿Y cuántos dispositivos permite?
- Escribe una red completa en notación CIDR si sabes que:
    - Dirección IP: 192.168.10.0
    - Máscara: 255.255.255.192