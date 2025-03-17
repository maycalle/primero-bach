# 2. Conceptos básicos y tipos de redes

Hasta ahora, hemos explorado qué son las redes informáticas, su evolución histórica y los modelos de comunicación que permiten la conexión entre dispositivos. Ahora profundizaremos en aspectos más técnicos, pero esenciales para comprender cómo funcionan las redes en la práctica.

## 2.1 Protocolos de comunicación: el lenguaje de las redes

Los protocolos de comunicación son conjuntos de reglas que permiten la transferencia de datos entre dispositivos en una red. Sin estos protocolos, la comunicación en Internet y en las redes informáticas no sería posible.

### 2.1.1 El conjunto de protocolos TCP/IP

TCP/IP es el estándar global en redes, y cada vez que usas Internet, estás utilizando TCP/IP.

- **TCP (*Transmission Control Protocol*):** se encarga de dividir los datos en paquetes, asegurar de que lleguen sin errores y en el orden correcto.
- **IP (*Internet Protocol*):** se ocupa de enrutar esos paquetes para que lleguen a la dirección correcta.

📌 Ejemplo: Cuando envías un mensaje en WhatsApp, TCP divide el mensaje en fragmentos (paquetes) y los envía con la dirección IP del destinatario. Al llegar, TCP los reconstruye en el mensaje original.

### 2.1.2 Otros protocolos esenciales

Además de TCP/IP, existen otros protocolos fundamentales en el funcionamiento de Internet:

#### DNS (*Domain Name System*) 
El DNS es el protocolo que traduce nombres de dominio como *www.google.com* en direcciones IP numéricas, permitiendo que los navegadores localicen los servidores donde están alojadas las páginas web. Por ejemplo, cuando escribes www.wikipedia.org en tu navegador, el DNS traduce este nombre en una dirección IP específica (por ejemplo, 198.35.26.96), permitiendo que accedas al sitio web.

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
El cifrado SSL/TLS convierte los datos en un código incomprensible para quien no tenga la clave adecuada. Su funcionamiento básico es el siguiente: 
        - Tu navegador y el servidor acuerdan una clave secreta (handshake o apretón de manos).
        - A partir de ese momento, toda la información se cifra antes de enviarse.
        - Si un atacante intercepta los datos, solo verá un conjunto de caracteres sin sentido.
Es como enviar una carta dentro de una caja con candado. Solo el destinatario tiene la llave para abrirla y leer el mensaje. 

#### FTP (*File Transfer Protocol*) 
FTP es un protocolo que permite la transferencia de archivos entre un cliente (ordenador) y un servidor a través de una red, ya sea una red local o Internet. Imagina que estás diseñando una página web. Una vez terminada en tu computadora, necesitas subir los archivos al servidor donde estará publicada. Para esto, usas un programa FTP como FileZilla y envías los archivos al servidor.

#### Protocolos de correo electrónico: SMTP/IMAP/POP3 
Son protocolos utilizados en el envío y recepción de correos electrónicos desde el remitente hasta el destinatario. 
- **SMTP (*Simple Mail Transfer Protocol*):** para enviar correos. Por ejemplo, cuando envías un correo desde Gmail, tu mensaje viaja a través del servidor SMTP de Google antes de llegar al destinatario.
- **IMAP (*Internet Message Access Protocol*):** permite acceder al correo electrónico directamente desde el servidor sin necesidad de descargar los mensajes. Si usas tu correo en el móvil y la computadora, IMAP sincroniza los mensajes para que puedas acceder a ellos desde cualquier dispositivo. Su principal ventaja es que no ocupa espacio en el dispositivo, ya que los correos permanecen en el servidor.
- **POP3 (*Post Office Protocol v3*):** descarga los correos en un dispositivo y, por defecto, los borra del servidor después de descargarlos. Si configuras tu correo en Outlook con POP3, los mensajes se almacenan en tu computadora, pero si accedes desde otro dispositivo, no los verás. Su principal ventaja es que permite acceder a los correos sin necesidad de estar conectado a Internet.

## 2.2 Direcciones IP y MAC: concepto y utilidad

Para que los dispositivos puedan comunicarse, necesitan identificarse dentro de la red. Aquí entran en juego dos tipos de direcciones:

**Dirección IP: el domicilio de tu dispositivo**
La dirección IP *(Internet Protocol)* es el identificador lógico que se asigna a cada dispositivo en una red. Existen dos versiones:

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

### 2.2.1 Según su área de cobertura
LAN, MAN, WAN

### 2.2.2 Según su topología
Estrella, bus, anillo, malla, híbrida 

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
