# 2. Conceptos básicos y tipos de redes

Hasta ahora, hemos explorado qué son las redes informáticas, su evolución histórica y los modelos de comunicación que permiten la conexión entre dispositivos. Ahora profundizaremos en aspectos más técnicos, pero esenciales para comprender cómo funcionan las redes en la práctica.

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

## 2.2 Clasificación de las redes 

Las redes de comunicación pueden clasificarse según diferentes criterios, como su área de cobertura, topología, medio de transmisión y gestión de acceso.

### 2.2.1 Según su área de cobertura

Este criterio clasifica las redes según la distancia que abarcan y el tamaño del área en la que operan. Cada tipo de red emplea tecnologías específicas para su funcionamiento.
 
**WAN (Wide Area Network - Red de Área Extensa)** 
- Las redes WAN conectan dispositivos en áreas geográficas muy amplias, como ciudades, países o incluso continentes, utilizando una combinación de tecnologías para lograr esta conexión a gran escala. 
- La columna vertebral de las redes WAN son los cables de fibra óptica, especialmente los cables submarinos que cruzan los océanos, como el cable "Marea" que une Europa y Estados Unidos con una capacidad de 160 Terabits por segundo (Tbps). Para la conectividad en áreas urbanas y suburbanas, se emplean conexiones móviles (4G/5G) que utilizan torres de telecomunicaciones, con la tecnología 5G permitiendo velocidades de hasta 10 Gbps. En áreas remotas donde el cableado no es viable, como zonas rurales, barcos o aviones, se utilizan satélites de comunicaciones. 
- El ejemplo más representativo de una WAN es Internet, que interconecta millones de dispositivos a nivel global.

**MAN (Metropolitan Area Network - Red de Área Metropolitana)** 
- Las redes MAN interconectan edificios, universidades, hospitales o empresas dentro de una misma ciudad o región. Se caracterizan por su alta velocidad y gran ancho de banda.
- Se construyen principalmente sobre fibra óptica, que proporciona la alta velocidad y ancho de banda necesarios para conectar múltiples ubicaciones dentro de una ciudad. Para extender la conectividad donde el cableado es difícil, se utiliza WiMAX, una tecnología inalámbrica que alcanza hasta 1 Gbps en distancias de hasta 50 km. Además, se emplean anillos de fibra óptica como FDDI y SDH/SONET, diseñados con redundancia para asegurar la disponibilidad continua de la red.
- Un ejemplo de MAN es una red de fibra óptica que conecta varias sedes de una empresa en una ciudad.

**LAN (Local Area Network - Red de Área Local)** 
- Las redes LAN operan en espacios reducidos, como hogares, oficinas o colegios. Se caracterizan por ofrecer altas velocidades de transmisión en comparación con MAN y WAN.
- Las tecnologías que sustentan las redes LAN son diversas y permiten tanto conexiones cableadas como inalámbricas. Ethernet (IEEE 802.3) es el estándar para redes cableadas, utilizando cables de par trenzado o fibra óptica y alcanzando velocidades de 100 Mbps, 1 Gbps o incluso 10 Gbps. Por otro lado, Wi-Fi (IEEE 802.11) proporciona conectividad inalámbrica, con estándares como Wi-Fi 6 (802.11ax) y el futuro Wi-Fi 7, que mejoran la velocidad y la eficiencia. Adicionalmente, Powerline Communications (PLC) permite transmitir datos a través del cableado eléctrico existente, siendo una opción útil en entornos donde la instalación de cables de red es complicada.
- Un ejemplo de red LAN es la red de un colegio donde los ordenadores están conectados por cable Ethernet o Wi-Fi.

**PAN (Personal Area Network - Red de Área Personal)** 
- Las redes PAN conectan dispositivos cercanos dentro de un radio de pocos metros, facilitando la comunicación entre periféricos y dispositivos personales.
- Las redes PAN se basan en tecnologías inalámbricas de corto alcance. Bluetooth (IEEE 802.15.1) permite conectar dispositivos a distancias de hasta 10 metros, siendo común en auriculares, teclados y ratones. NFC (Near Field Communication) posibilita la comunicación en distancias aún más cortas, ideales para pagos móviles y tarjetas de acceso. Por otro lado, Zigbee y Z-Wave son protocolos diseñados para domótica y automatización del hogar, permitiendo controlar luces, sensores y cerraduras de forma inalámbrica.
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

En una red informática, la topología se refiere a la forma en que los dispositivos están conectados entre sí. Existen diferentes tipos de topologías, cada una con sus ventajas y desventajas. A continuación, exploramos las más comunes:

**Topología en estrella**
En esta configuración, todos los dispositivos están conectados a un nodo central (como un switch o un router).
- El nodo central controla toda la comunicación.
- Si un dispositivo falla, el resto de la red sigue funcionando.
- Si el nodo central falla, la red completa deja de operar.

Ejemplo: Las redes WiFi domésticas donde todos los dispositivos se conectan a un router.

**Topologia en bus**
Todos los dispositivos están conectados a un único cable principal (bus o troncal), que transporta los datos en ambas direcciones.
- Es fácil y económica de implementar.
- Si el cable principal se daña, toda la red falla.
- A medida que se agregan más dispositivos, la velocidad disminuye por la congestión en el bus.

Ejemplo: Redes locales antiguas con cable coaxial en oficinas o escuelas.

**Topología en anillo**
Los dispositivos están conectados en círculo y los datos viajan en una sola dirección o en ambas.
- No hay nodo central, por lo que no depende de un único punto de fallo.
- Es eficiente para transmitir datos, pero si un dispositivo falla, toda la red se interrumpe.
- Puede ser lenta en redes grandes, ya que los datos deben pasar por cada nodo.

Ejemplo: Redes en estaciones de trabajo o antiguas redes de fibra óptica.

**Topología en malla**
Cada dispositivo está conectado a varios otros de forma redundante, lo que crea múltiples caminos para enviar los datos.
- Es muy fiable porque si un enlace falla, los datos encuentran otro camino.
- Alta velocidad y rendimiento.
- Es costosa y compleja de implementar por la cantidad de cables y conexiones necesarias.

Ejemplo: Internet en su conjunto funciona con una topología de malla parcial, donde hay múltiples rutas entre servidores y dispositivos.

**Topología híbrida**
Combina dos o más de las topologías anteriores, adaptándose a las necesidades específicas de la red.
- Es muy flexible y escalable.
- Puede integrar lo mejor de cada topología.
- Puede ser costosa y compleja de administrar.

Ejemplo: Redes empresariales donde los departamentos pueden tener topología en estrella, pero conectarse entre sí mediante malla o bus.

Cada topología tiene sus ventajas y desventajas, y la elección depende del costo, rendimiento y seguridad que se necesite. En la actualidad, las más utilizadas son estrella y malla, debido a su eficiencia y estabilidad.

### 2.2.3 Según su medio de transmisión
cableadas, inlámbricas, mixtas

### 2.2.4 Según su gestión y acceso
Redes privadas, públicas, híbridas

## 2.3 Redes cableadas vs redes inalámbricas
- Ventajas e incovenientes
- Tipos de cableado: coaxial, par trenzado, fibra óptica
- Wi-Fi, Bluetooth y otras tecnologías inalámbricas

## 2.4 Introducción a la seguridad en las redes
- Amenazas básicas en redes (interceptación, suplantación, ataques de denegación de servicio)
- Concepto de firewall y VPN
