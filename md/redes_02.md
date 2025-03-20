# 2. Tipos de redes y su estructura

Hasta ahora, hemos explorado qué son las redes informáticas, su evolución histórica y los modelos de comunicación que permiten la conexión entre dispositivos. Ahora profundizaremos en los diferentes tipos de redes, cómo se estructuran y los medios a través de los cuales transmiten información.

## 2.1 Dispositivos de red

Los dispositivos de red permiten la conexión, gestión y flujo de datos entre distintos equipos dentro de una red. Su función es esencial para garantizar la comunicación eficiente entre computadoras, servidores y otros dispositivos en redes domésticas, empresariales e industriales.

A continuación, se describen los principales dispositivos de red y su función:

### 2.1.1 Router


### 2.1.2 Switch


### 2.1.3 Hub


### 2.1.4 Punto de acceso


### 2.1.5 Firewall


### 2.1.6 Otros dispositivos

Módem
Repetidor wi-Fi
Proxy


Cada dispositivo de red cumple un papel esencial en la comunicación y seguridad de la red:
- Routers y módems conectan la red a Internet.
- Switches y hubs gestionan el tráfico dentro de la red.
- Access Points y repetidores Wi-Fi permiten la conectividad inalámbrica.
- Firewalls y servidores protegen y administran los datos.

## 2.2 Clasificación de las redes 

Las redes de comunicación pueden clasificarse según diferentes criterios:
- Según su área de cobertura
- Según su topología
- Según su medio de transmisión 
- Según su gestión y acceso. 

Cada una de estas clasificaciones determina la forma en que los dispositivos se conectan y cómo se comunican dentro de una red.

### 2.2.1 Según su área de cobertura

Este criterio clasifica las redes según la distancia que abarcan y el tamaño del área en la que operan. 
 
#### WAN (Wide Area Network - Red de Área Extensa) 
- Las **redes WAN** conectan dispositivos en áreas geográficas muy amplias, como **ciudades, países o incluso continentes**, utilizando una combinación de tecnologías para lograr esta conexión a gran escala. 
- La columna vertebral de las redes WAN son los cables de fibra óptica, especialmente los cables submarinos que cruzan los océanos, como el cable "Marea" que une Europa y Estados Unidos con una capacidad de 160 Terabits por segundo (Tbps). Para la conectividad en áreas urbanas y suburbanas, se emplean conexiones móviles (4G/5G) que utilizan torres de telecomunicaciones, con la tecnología 5G permitiendo velocidades de hasta 10 Gbps. En áreas remotas donde el cableado no es viable, como zonas rurales, barcos o aviones, se utilizan satélites de comunicaciones. 
- El ejemplo más representativo de una WAN es Internet, que interconecta millones de dispositivos a nivel global.

#### MAN (Metropolitan Area Network - Red de Área Metropolitana)
- Las **redes MAN** interconectan **edificios, universidades, hospitales o empresas dentro de una misma ciudad o región**. Se caracterizan por su alta velocidad y gran ancho de banda.
- Se construyen principalmente sobre fibra óptica, que proporciona la alta velocidad y ancho de banda necesarios para conectar múltiples ubicaciones dentro de una ciudad. Para extender la conectividad donde el cableado es difícil, se utiliza WiMAX, una tecnología inalámbrica que alcanza hasta 1 Gbps en distancias de hasta 50 km. Además, se emplean anillos de fibra óptica como FDDI y SDH/SONET, diseñados con redundancia para asegurar la disponibilidad continua de la red.
- Un ejemplo de MAN es una red de fibra óptica que conecta varias sedes de una empresa en una ciudad.

#### LAN (Local Area Network - Red de Área Local)
- Las **redes LAN** operan en espacios reducidos, como **hogares, oficinas o colegios**. Se caracterizan por ofrecer altas velocidades de transmisión en comparación con MAN y WAN.
- Las tecnologías que sustentan las redes LAN son diversas y permiten tanto conexiones cableadas como inalámbricas. Ethernet (IEEE 802.3) es el estándar para redes cableadas, utilizando cables de par trenzado o fibra óptica y alcanzando velocidades de 100 Mbps, 1 Gbps o incluso 10 Gbps. Por otro lado, Wi-Fi (IEEE 802.11) proporciona conectividad inalámbrica, con estándares como Wi-Fi 6 (802.11ax) y el futuro Wi-Fi 7, que mejoran la velocidad y la eficiencia. Adicionalmente, Powerline Communications (PLC) permite transmitir datos a través del cableado eléctrico existente, siendo una opción útil en entornos donde la instalación de cables de red es complicada.
- Un ejemplo de red LAN es la red de un colegio donde los ordenadores están conectados por cable Ethernet o Wi-Fi.

#### PAN (Personal Area Network - Red de Área Personal)
- Las **redes PAN** conectan dispositivos cercanos dentro de un radio de **pocos metros**, facilitando la comunicación entre periféricos y dispositivos personales.
- Se basan en tecnologías inalámbricas de corto alcance. Bluetooth (IEEE 802.15.1) permite conectar dispositivos a distancias de hasta 10 metros, siendo común en auriculares, teclados y ratones. NFC (Near Field Communication) posibilita la comunicación en distancias aún más cortas, ideales para pagos móviles y tarjetas de acceso. Por otro lado, Zigbee y Z-Wave son protocolos diseñados para domótica y automatización del hogar, permitiendo controlar luces, sensores y cerraduras de forma inalámbrica.
- Un ejemplo de red PAN es un smartphone conectado a auriculares Bluetooth o a un smartwatch

Cuando estas redes utilizan conexiones inalámbricas, se antepone la letra W (Wireless) al nombre de la red:
- WLAN (Wireless LAN): versión inalámbrica de una LAN, basada en WiFi.
- WPAN (Wireless PAN): versión inalámbrica de una PAN, como Bluetooth o NFC.

Cada tipo de red se adapta a diferentes necesidades y escalas, utilizando tecnologías específicas para garantizar velocidad, estabilidad y conectividad.

<table>
    <tr>
        <th>Tipo de red</th>
        <th>Cobertura</th>
        <th>Tecnologías clave</th>
        <th>Ejemplo</th>
    </tr>
    <tr>
        <td>WAN</td>
        <td>Global</td>
        <td>Fibra óptica submarina, satélites, 4G/5G</td>
        <td>Internet</td>
    </tr>
    <tr>
        <td>MAN</td>
        <td>Ciudad o región</td>
        <td>Fibra óptica, WiMax, FDDI</td>
        <td>Red de una universidad</td>
    </tr>
    <tr>
        <td>LAN</td>
        <td>Edificio o campus</td>
        <td>Ethernet, WiFi, PLC</td>
        <td>WiFi en una oficina</td>
    </tr>
    <tr>
        <td>PAN</td>
        <td>Pocos metros</td>
        <td>Bluetooth, NFC, Zigbee</td>
        <td>Smartwatch conectado al móvil</td>
    </tr>
</table>


### 2.2.2 Según su topología

En una red informática, la topología se refiere a la forma en que los dispositivos están conectados entre sí. A continuación, exploramos las más comunes:

#### Topología en estrella
En esta configuración, todos los dispositivos están conectados a un nodo central (como un switch o un router).
- El nodo central controla toda la comunicación.
- Si un dispositivo falla, el resto de la red sigue funcionando.
- Si el nodo central falla, la red completa deja de operar.

Ejemplo: Las redes WiFi domésticas donde todos los dispositivos se conectan a un router.

#### Topologia en bus
Todos los dispositivos están conectados a un único cable principal (bus o troncal), que transporta los datos en ambas direcciones.
- Es fácil y económica de implementar.
- Si el cable principal se daña, toda la red falla.
- A medida que se agregan más dispositivos, la velocidad disminuye por la congestión en el bus.

Ejemplo: Redes locales antiguas con cable coaxial en oficinas o escuelas.

#### Topología en anillo
Los dispositivos están conectados en círculo y los datos viajan en una sola dirección o en ambas.
- No hay nodo central, por lo que no depende de un único punto de fallo.
- Es eficiente para transmitir datos, pero si un dispositivo falla, toda la red se interrumpe.
- Puede ser lenta en redes grandes, ya que los datos deben pasar por cada nodo.

Ejemplo: Redes en estaciones de trabajo o antiguas redes de fibra óptica.

#### Topología en malla
Cada dispositivo está conectado a varios otros de forma redundante, lo que crea múltiples caminos para enviar los datos.
- Es muy fiable porque si un enlace falla, los datos encuentran otro camino.
- Alta velocidad y rendimiento.
- Es costosa y compleja de implementar por la cantidad de cables y conexiones necesarias.

Ejemplo: Internet en su conjunto funciona con una topología de malla parcial, donde hay múltiples rutas entre servidores y dispositivos.

#### Topología híbrida
Combina dos o más de las topologías anteriores, adaptándose a las necesidades específicas de la red.
- Es muy flexible y escalable.
- Puede integrar lo mejor de cada topología.
- Puede ser costosa y compleja de administrar.

Ejemplo: Redes empresariales donde los departamentos pueden tener topología en estrella, pero conectarse entre sí mediante malla o bus.

Cada topología tiene sus ventajas y desventajas, y la elección depende del costo, rendimiento y seguridad que se necesite. En la actualidad, las más utilizadas son estrella y malla, debido a su eficiencia y estabilidad.

### 2.2.3 Según su medio de transmisión

Las redes pueden clasificarse según el tipo de conexión utilizada para transmitir la información.

#### 2.2.3.1 Redes cableadas

Utilizan medios físicos para la transmisión de datos, como **cables de cobre o fibra óptica**. Son más estables que las redes inalámbricas, ya que no sufren interferencias externas con la misma facilidad.

##### Tipos de cableado

###### Cable coaxial
Fue ampliamente utilizado en las primeras redes de datos y sigue empleándose en **televisión por cable, sistemas de videovigilancia y telecomunicaciones**. Aunque su uso en redes informáticas ha disminuido, sigue siendo útil en ciertos entornos debido a su resistencia a interferencias.

###### Par trenzado

Está formado por **pares de hilos de cobre entrelazados**, lo que ayuda a **reducir interferencias electromagnéticas** y mejorar la calidad de la señal. Es el más utilizado en **redes Ethernet**, que son redes de comunicación cableadas que permiten la conexión de dispositivos como ordenadores, routers y switches dentro de una misma área, como hogares, oficinas o empresas.

**Tipos par trenzado**
- **UTP (*Unshielded Twisted Pair*):** sin blindaje adicional. Más económico y flexible, pero menos protegido contra interferencias. Se usa en redes domésticas y de oficina.
- **STP (*Shielded Twisted Pair*):** tiene un blindaje para proteger contra interferencias electromagnéticas externas, mejorando su rendimiento en entornos con muchos dispositivos electrónicos o instalaciones industriales.

**Categorías de cable de par trenzado**
Cada categoría indica el nivel de velocidad y rendimiento del cable:
- **Cat 5e:** hasta 1 Gbps en 100 metros. Mejor que el Cat 5 en reducción de interferencias.
- **Cat 6:** hasta 10 Gbps en 55 metros. Mayor aislamiento frente a interferencias.
- **Cat 7 y superiores:** mejor rendimiento, mayor velocidad y más blindaje. Usados en centros de datos y redes de alto rendimiento.

###### Fibra óptica

En lugar de cobre, usa **hilos delgados de vidrio o plástico** para transmitir datos mediante **pulsos de luz**, logrando velocidades más altas y mayores distancias sin pérdida de señal.

**Tipos de fibra óptica**
- **Monomodo (*SMF - Single Mode Fiber*):**  núcleo delgado que guía la luz en un solo camino, permitiendo mayores distancias (más de 100 km) y alta velocidad. Usada en conexiones entre ciudades o países.
- **Multimodo (*MMF - Multi Mode Fiber*):** núcleo más ancho que permite que la luz viaje en varios caminos, pero con más dispersión. Más económica y fácil de instalar, utilizada en redes dentro de edificios y centros de datos (hasta 2 km).

#### 2.2.3.2 Redes inalámbricas

Transmiten información a través de **ondas electromagnéticas**, eliminando la necesidad de cables físicos. Son más flexibles y permiten movilidad, aunque pueden ser más susceptibles a interferencias.

##### Tecnologías inalámbricas

###### Wi-Fi (Wireless Fidelity)
Usado en redes domésticas, empresas y lugares públicos. Su velocidad y alcance dependen de la versión:
- Wi-Fi 4 (802.11n): Hasta 600 Mbps.
- Wi-Fi 5 (802.11ac): Hasta 1.3 Gbps, mayor estabilidad.
- Wi-Fi 6 (802.11ax): Hasta 9.6 Gbps, mejor cobertura y menor latencia.
- Wi-Fi 7 (en desarrollo): mejor rendimiento y capacidad.

###### Bluetooth
Tecnología para comunicación de corto alcance entre dispositivos.
- Bluetooth 4.0 - 4.2: bajo consumo de energía, ideal para wearables.
- Bluetooth 5.0: mayor alcance (hasta 240 metros) y mejor rendimiento.

###### Zigbee y Z-Wave
Utilizados en automatización del hogar e Internet de las Cosas (IoT).
- Zigbee: Opera en la banda de 2.4 GHz, bajo consumo energético.  Ideal para sensores y dispositivos inteligentes.
- Z-Wave: Opera en 900 MHz, menos interferencias.

###### 5G y su impacto en redes
Tecnología de nueva generación para dispositivos móviles.
- Mayor velocidad de transmisión (hasta 10 Gbps).
- Menor latencia (respuesta más rápida, ideal para videojuegos y realidad virtual).
- Soporte para más dispositivos conectados simultáneamente.

#### 2.2.3.3 Redes mixtas

Las redes mixtas combinan conexiones cableadas e inalámbricas, aprovechando la estabilidad y velocidad del cableado junto con la flexibilidad y movilidad de las redes inalámbricas. Son muy utilizadas en oficinas, hogares, empresas y entornos industriales, ya que permiten conectar dispositivos de diferentes tipos sin comprometer la eficiencia de la red.

##### ¿Cómo funcionan las redes mixtas?

La señal de una red cableada (Ethernet) se amplía mediante dispositivos inalámbricos para permitir la conexión de equipos sin cables. Para esto, se pueden utilizar los siguientes métodos:

- **Punto de acceso (*Access Point, AP*):** dispositivo que conecta la red cableada con la red inalámbrica, actuando como puente entre ambas. Permite que dispositivos Wi-Fi accedan a la red sin necesidad de un cable físico.
- **Conexión ad hoc:** ocurre cuando los dispositivos se conectan directamente entre sí de forma inalámbrica, sin pasar por un punto de acceso o router. Se usa en casos como la conexión directa entre portátiles o impresoras sin infraestructura adicional.

##### Ejemplo de red mixta en la vida real

Una empresa puede tener servidores y ordenadores de escritorio conectados por cable Ethernet para garantizar máxima estabilidad, mientras que los empleados usan Wi-Fi para portátiles, teléfonos y tablets dentro de la oficina.

### 2.2.4 Según su nivel de acceso o privacidad

Las redes pueden clasificarse según el nivel de acceso permitido a los usuarios. Algunas están restringidas a ciertos grupos o instituciones, mientras que otras son de acceso libre. También existen redes híbridas que combinan ambas características.

#### Redes privadas
Son redes de acceso exclusivo, donde solo los usuarios autorizados pueden conectarse y utilizar sus servicios. Se utilizan en empresas, instituciones y organizaciones para garantizar seguridad, control y privacidad de la información.

Cuando una red privada ofrece servicios como páginas web, correo electrónico y almacenamiento de archivos, pero solo accesibles para sus miembros, se llama **Intranet**. Es común en empresas y centros educativos para compartir información interna de forma segura.

#### Redes públicas
Son redes de acceso libre, donde cualquier persona puede conectarse para comunicarse, compartir información y utilizar servicios sin restricciones.
Un ejemplo claro es Internet, la red pública global que conecta millones de dispositivos en todo el mundo. Otras redes públicas más pequeñas las encontramos cuando se ofrece Wi-Fi gratuito en aeropuertos, bibliotecas o cafeterías, o en redes móviles 4G/5G que permiten el acceso a internet sin restricciones.

#### Redes híbridas
Son aquellas que combinan elementos de redes privadas y públicas, permitiendo que algunas secciones sean accesibles para todos, mientras que otras están restringidas a usuarios específicos. Por ejemplo, una universidad que ofrece Wi-Fi público para estudiantes y visitantes, pero restringe el acceso a ciertos sistemas administrativos o bases de datos internas.

#### VPN (Virtual Private Network)
Una VPN o Red Privada Virtual es una tecnología que permite acceder de forma segura a una red privada a través de internet. Se usa para proteger datos y garantizar privacidad en conexiones remotas. La VPN crea un túnel seguro y cifrado entre el usuario y la red privada, evitando que terceros puedan interceptar la información.

Por ejemplo, un empleado de una empresa accede desde su casa a la red interna de la oficina mediante una VPN corporativa.


## 2.2 Dispositivos de red

Los dispositivos de red permiten la conexión y el flujo de datos entre distintos equipos dentro de una red. Entre los más importantes se encuentran:

Router: Dispositivo que conecta redes diferentes, como una red doméstica con Internet.

Switch: Administra el tráfico dentro de una red local (LAN), enviando datos solo a los dispositivos que los necesitan.

Hub: Similar a un switch, pero menos eficiente, ya que envía los datos a todos los dispositivos conectados.

Access Point (AP): Permite que dispositivos inalámbricos se conecten a una red cableada.

Firewall: Filtra y protege la red contra amenazas externas.






----

## 2.1 Protocolos de comunicación: el lenguaje de las redes

Los protocolos de comunicación son conjuntos de reglas que permiten la transferencia de datos entre dispositivos en una red. Sin estos protocolos, la comunicación en Internet y en las redes informáticas no sería posible.

### 2.1.1 El conjunto de protocolos TCP/IP

TCP/IP es el estándar global en redes, y cada vez que usas Internet, estás utilizando TCP/IP.

- **TCP (*Transmission Control Protocol*):** se encarga de dividir los datos en paquetes, asegurar de que lleguen sin errores y en el orden correcto.
- **IP (*Internet Protocol*):** se ocupa de enrutar esos paquetes para que lleguen a la dirección correcta.

Cuando envías un mensaje en WhatsApp, TCP divide el mensaje en fragmentos (paquetes) y los envía con la dirección IP del destinatario. Al llegar, TCP los reconstruye en el mensaje original.

### 2.1.2 Otros protocolos esenciales

Además de TCP/IP, existen otros protocolos fundamentales en el funcionamiento de Internet:

#### DNS (*Domain Name System*) 
El DNS es el protocolo que traduce nombres de dominio como *www.google.com* en direcciones IP numéricas, permitiendo que los navegadores localicen los servidores donde están alojadas las páginas web. Realmente se trata de una base de datos distribuida. Por ejemplo, cuando escribes www.wikipedia.org en tu navegador, el DNS traduce este nombre en una dirección IP específica (por ejemplo, 198.35.26.96), permitiendo que accedas al sitio web.

#### HTTP  (*HyperText Transfer Protocol*) y HTTPS (HyperText Transfer Protocol Secure)
Ambos protocolos permiten la navegación en la web, pero existen diferencias importantes en seguridad.

- **HTTP** 
    - Es el protocolo estándar para la transferencia de información en la web. 
    - No cifra los datos, por lo que cualquier persona que intercepte la comunicación puede ver la información transmitida. 
    - Si inicias sesión en una página que usa HTTP, alguien en la misma red WiFi pública podría capturar tu contraseña y leerla sin dificultad.

- **HTTPS** 
    - Versión más segura de HTTP, ya que usa cifrado SSL/TLS para proteger la información. 
    - Un sitio web usa HTTPS si en la barra de direcciones aparece un candado 🔒.
   
- **Cifrado SSL/TLS: ¿cómo protege los datos?**
    - El cifrado SSL/TLS convierte los datos en un código incomprensible para quien no tenga la clave adecuada. Su funcionamiento básico es el siguiente: 
        - Tu navegador y el servidor acuerdan una clave secreta (handshake o apretón de manos).
        - A partir de ese momento, toda la información se cifra antes de enviarse.
        - Si un atacante intercepta los datos, solo verá un conjunto de caracteres sin sentido.
    - Es como enviar una carta dentro de una caja con candado. Solo el destinatario tiene la llave para abrirla y leer el mensaje. 

#### FTP (*File Transfer Protocol*) 
FTP es un protocolo que permite la transferencia de archivos entre un cliente (ordenador) y un servidor a través de una red, ya sea una red local o Internet. Imagina que estás diseñando una página web. Una vez terminada en tu computadora, necesitas subir los archivos al servidor donde estará publicada. Para esto, usas un programa FTP como FileZilla y envías los archivos al servidor.

#### Protocolos de correo electrónico: SMTP/IMAP/POP3 
Son protocolos utilizados en el envío y recepción de correos electrónicos desde el remitente hasta el destinatario. 
- **SMTP (*Simple Mail Transfer Protocol*):** para enviar correos. Por ejemplo, cuando envías un correo desde Gmail, tu mensaje viaja a través del servidor SMTP de Google antes de llegar al destinatario.
- **IMAP (*Internet Message Access Protocol*):** permite acceder al correo electrónico directamente desde el servidor sin necesidad de descargar los mensajes. Si usas tu correo en el móvil y la computadora, IMAP sincroniza los mensajes para que puedas acceder a ellos desde cualquier dispositivo. Su principal ventaja es que no ocupa espacio en el dispositivo, ya que los correos permanecen en el servidor.
- **POP3 (*Post Office Protocol v3*):** descarga los correos en un dispositivo y, por defecto, los borra del servidor después de descargarlos. Si configuras tu correo en Outlook con POP3, los mensajes se almacenan en tu computadora, pero si accedes desde otro dispositivo, no los verás. Su principal ventaja es que permite acceder a los correos sin necesidad de estar conectado a Internet.

## 2.2 Direcciones IP y MAC: concepto y utilidad

Para que los dispositivos puedan comunicarse en una red, necesitan identificarse correctamente. Para ello, utilizan dos tipos de direcciones:
- Dirección IP: identifica un dispositivo dentro de una red y le permite conectarse a Internet.
- Dirección MAC: es un identificador único que distingue físicamente a cada dispositivo.

**Dirección IP: el domicilio de tu dispositivo**
La dirección IP *(Internet Protocol)* es el identificador lógico que se asigna a cada dispositivo en una red. Funciona como la dirección de tu casa: si alguien quiere enviarte información en Internet, necesita saber dónde encontrarte. 

- IPv4 (32 bits): formato clásico con números como 192.168.1.1. Limitado a unos 4,3 mil millones de direcciones.
- IPv6 (128 bits): nuevo estándar con muchas más combinaciones (2001:db8::ff00:42:8329).

📌 Ejemplo: Tu router tiene una dirección IP asignada por el proveedor de Internet, y dentro de tu casa, cada dispositivo (móvil, laptop, consola) recibe una dirección IP interna.

**Dirección MAC: la huella digital de tu dispositivo**
- Cada tarjeta de red tiene una dirección MAC *(Media Access Control)* única, establecida por el fabricante.
- Está formada por 6 pares de caracteres hexadecimales (ejemplo: 00:1A:2B:3C:4D:5E).
- No cambia, a diferencia de la IP, que puede ser dinámica.

📌 Diferencia clave:
- La dirección IP es como la dirección de tu casa (cambia si te mudas).
- La dirección MAC es como tu huella dactilar (única e inalterable).

### 2.1.3 Parámetros de calidad en redes: ancho de banda, latencia y otros parámetros de red.

Cuando usamos Internet, no solo importa que estemos conectados, sino cómo de buena es esa conexión. Aquí entran en juego varios factores clave:

**Ancho de Banda: la cantidad de datos que pueden viajar**
- Se mide en Mbps (megabits por segundo) o Gbps (gigabits por segundo).
- Cuanto mayor sea, más rápido podremos descargar y cargar información.

📌 Ejemplo:
- Una videollamada en HD necesita al menos 5 Mbps de ancho de banda.
- Ver Netflix en 4K puede requerir 25 Mbps o más.

**Latencia: el tiempo de respuesta de la red**
- Se mide en milisegundos (ms) y representa el tiempo que tarda un paquete en viajar de origen a destino.
- Cuanto menor sea la latencia, más rápida será la comunicación.

📌 Ejemplo:
- Un videojuego en línea necesita baja latencia (<50 ms) para evitar retrasos.
- En una videollamada, una alta latencia (>200 ms) hace que haya desfase en el audio y el video.

**Jitter: la variación en la llegada de paquetes**
- Si los paquetes de datos llegan con diferencias de tiempo irregulares, se produce jitter.
- Afecta especialmente a transmisiones en vivo y llamadas por Internet.

📌 Ejemplo: Si una videollamada va a saltos o con cortes, el jitter puede ser el problema.

**Pérdida de Paquetes: cuando la información no llega**
- Se expresa en porcentaje de paquetes perdidos.
- Puede ser causada por congestión en la red, mala señal WiFi o errores en la conexión.

📌 Ejemplo: En una partida online, si hay un 3-5% de pérdida de paquetes, el juego puede volverse injugable con personajes que "se teletransportan".


## 2.4 Introducción a la seguridad en las redes
- Amenazas básicas en redes (interceptación, suplantación, ataques de denegación de servicio)
- Concepto de firewall y VPN
