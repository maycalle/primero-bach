# 2. Conceptos básicos y tipos de redes

Hasta ahora, hemos explorado qué son las redes informáticas, su evolución histórica y los modelos de comunicación que permiten la conexión entre dispositivos. Ahora profundizaremos en aspectos más técnicos, pero esenciales para comprender cómo funcionan las redes en la práctica.

## 2.1 Conceptos básicos sobre redes

Ya hemos visto que las redes funcionan gracias a los protocolos de comunicación, que establecen reglas para el intercambio de datos. Vamos a ver algunos en detalle:

### 2.1.1 Protocolos de comunicación y su importancia

**TCP/IP: el lenguaje de Internet**

Este conjunto de protocolos, que ya conoces, es el estándar global en redes, y cada vez que usas Internet, estás utilizando TCP/IP.

- **TCP (*Transmission Control Protocol*):** se encarga de dividir los datos en paquetes, asegurarse de que lleguen sin errores y en el orden correcto.
- **IP (*Internet Protocol*):** se ocupa de enrutar esos paquetes para que lleguen a la dirección correcta.

📌 Ejemplo: Cuando envías un mensaje en WhatsApp, TCP divide el mensaje en fragmentos (paquetes) y los envía con la dirección IP del destinatario. Al llegar, TCP los reconstruye en el mensaje original.

**Otros protocolos esenciales**

Además de TCP/IP, existen otros protocolos fundamentales en el funcionamiento de Internet:

- **DNS (*Domain Name System*):** traduce nombres de dominio como *www.google.com* en direcciones IP numéricas. Cuando buscas una web, tu navegador usa DNS para traducir la dirección que escribes a una dirección IP específica del servidor donde está alojado el sitio.
- **HTTP  (*HyperText Transfer Protocol*) y HTTPS (HyperText Transfer Protocol Secure)**: los dos protocolos permiten la navegación web, pero existen diferencias importantes entre ellos.
    - **HTTP** es el protocolo estándar para la transferencia de información en la web. Sin embargo, tiene un problema: no cifra los datos, por lo que cualquier persona que intercepte la comunicación puede ver la información transmitida. Si inicias sesión en una página que usa HTTP, alguien en la misma red WiFi pública podría capturar tu contraseña y leerla sin dificultad.
    - **HTTPS** es una versión más segura de HTTP, ya que usa cifrado SSL/TLS para proteger la información y evitar que terceros la intercepten. Para saber si un sitio web usa HTTPS debes fijarte en la barra de direcciones del navegador. Si hay un candado cerrado 🔒, usa HTTPS y, por tanto, los datos viajan encriptados. 
    
    El cifrado SSL/TLS funciona convirtiendo los datos legibles (en texto plano) en un código incomprensible para cualquiera que no tenga la clave adecuada. En términos simples, tu navegador y el servidor primero acuerdan una clave secreta cuando se inicia la conexión segura (este proceso inicial se denomina handshake o “apretón de manos”). Una vez establecida esa clave compartida, toda la información que se envía se codifica usando dicha clave. Si alguien intercepta los datos en medio del camino, solo verá una serie de caracteres sin sentido. Solo el receptor legítimo, que posee la clave correcta, puede descifrar ese mensaje y leer la información original. En analogía, es como enviar una carta dentro de una caja cerrada con candado: cualquiera podría ver la caja, pero solo quien tiene la llave (el destinatario previsto) puede abrirla y entender el contenido de la carta. 
- **FTP (*File Transfer Protocol*)**: permite la transferencia de archivos entre un cliente (tu ordenador) y un servidor a través de una red, ya sea una red local o Internet. Imagina que estás diseñando una página web. Una vez terminada en tu computadora, necesitas subir los archivos al servidor donde estará publicada. Para esto, usas un programa FTP como FileZilla y envías los archivos al servidor.
- **SMTP/IMAP/POP3:** protocolos utilizados en el envío y recepción de correos electrónicos.
    - **SMTP (*Simple Mail Transfer Protocol*):** para enviar correos
    - **IMAP (*Internet Message Access Protocol*):** para recibir y gestionar correos en múltiples dispositivos.
    - **POP3 (*Post Office Protocol v3*):** para descargar correos en un solo dispositivo.


### 2.1.2 Direcciones IP y MAC: concepto y utilidad

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
