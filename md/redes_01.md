# 1. Introducción a las redes informnáticas

Las redes informáticas son parte fundamental de nuestra vida diaria. Gracias a ellas, podemos comunicarnos, trabajar, estudiar y entretenernos. En esta unidad aprenderás cómo funcionan, cómo se conectan los dispositivos y cómo hacer que las redes sean seguras.

## 1.1 ¿Qué es una red informática?

Una **red informática** es un conjunto de dispositivos conectados entre sí que permiten enviar y recibir datos. Estos dispositivos pueden ser ordenadores, teléfonos, impresoras, servidores o incluso tu smartwatch.

📌 *Ejemplo sencillo:*
Imagina que en tu casa tienes varios dispositivos conectados al WiFi. Todos ellos pueden navegar por Internet y, en algunos casos, compartir archivos o impresoras. ¡Eso ya es una red!

### 1.1.1 ¿Para qué sirven las redes?
Las redes informáticas tienen muchísimos usos, pero algunos de los más importantes son:
- Compartir información (como documentos en la nube).
- Comunicarnos (correo electrónico, redes sociales, videollamadas).
- Jugar en línea (multijugador, descargas).
- Usar servicios en Internet (banca online, tiendas digitales).

## 1.2 ¿Cómo se comunican los dispositivos de una red?

Para que la información viaje correctamente en una red, hacen falta:

- Emisor (quien envía el mensaje).
- Mensaje (la información transmitida).
- Receptor (quien recibe el mensaje).

El canal de comunicación es el medio por donde circulan los datos:

- Cables (fibra óptica, Ethernet).
- Inalámbrico (WiFi, Bluetooth, 5G).

Para que todo funcione, los dispositivos deben hablar el mismo "idioma", es decir, seguir un **protocolo de comunicación**. El más usado en Internet es **TCP/IP**.

## 1.3 El origen de las redes informáticas

Las redes informáticas no surgieron de la nada, sino que fueron evolucionando a medida que la tecnología avanzaba y la necesidad de compartir información se hacía cada vez mayor.

### 1.3.1 Los primeros pasos: la prehistoria de las redes

Antes de que existieran las redes de ordenadores, los sistemas informáticos eran máquinas gigantescas (mainframes) que solo podían usarse de manera individual. Si alguien quería compartir información, tenía que hacerlo físicamente, llevando tarjetas perforadas, disquetes o impresiones en papel.

Pero los científicos se dieron cuenta de que, si lograban conectar varios ordenadores, podrían compartir información más rápido y sin necesidad de transportar datos físicamente.

📌 Dato curioso: En la década de 1950, algunas universidades empezaron a experimentar con la idea de conectar computadoras mediante cables, pero estas conexiones eran limitadas y muy lentas.

### 1.3.2 ARPANET: la red que cambió todo

En los años 60, en plena Guerra Fría, el Departamento de Defensa de EE.UU. buscaba una forma de comunicar computadoras a distancia sin que la información se perdiera en caso de un ataque enemigo. Así nació ARPANET, la primera red de computadoras.

**Momentos clave de ARPANET:**
- **1969** → Se envió el primer mensaje entre dos computadoras conectadas a ARPANET. Querían escribir "LOGIN", pero solo llegó "LO" antes de que el sistema fallara. 😅
- **1971** → Se envió el primer correo electrónico entre computadoras.
- **1983** → Se implementó el protocolo TCP/IP, lo que permitió la expansión de las redes y la creación de Internet.

📌 Dato curioso: En 1969, ARPANET envió su primer mensaje, pero… ¡falló en el segundo carácter! Querían escribir "LOGIN", pero solo llegó "LO" antes de que el sistema colapsara. 😅

### 1.3.3 La explosión de las redes en los años 80

En los años 80, las empresas comenzaron a descubrir las ventajas de conectar sus computadoras para compartir información y mejorar la productividad. Esto provocó un enorme crecimiento en la cantidad y el tamaño de las redes.

Sin embargo, hubo un problema: cada fabricante diseñaba su propia tecnología y no existía un estándar común. Esto significaba que, si una empresa tenía computadoras de diferentes marcas, muchas veces no podían comunicarse entre sí.

Para solucionar esto, en 1984, la Organización Internacional para la Estandarización (ISO) desarrolló el **modelo OSI** *(Open Systems Interconnection)*, que establecía una estructura estándar para la comunicación entre redes.

### 1.3.4 Internet: la red de redes

Mientras OSI sentaba las bases teóricas, el modelo TCP/IP se convirtió en el estándar real y funcional en el que se basa Internet.

- **Años 90:** la World Wide Web (WWW) hace que Internet sea accesible para todos, no solo para científicos y militares.
- **2000 en adelante:** con la llegada de la banda ancha, el WiFi y los dispositivos móviles, las redes evolucionaron a lo que conocemos hoy.

📌 Dato curioso: El primer sitio web de la historia fue creado en 1991 por Tim Berners-Lee. ¡Y todavía está en línea! Puedes verlo aquí 👉 http://info.cern.ch


### 1.3.5 Resumen de la evolución de las redes

- 1950-1960: ordenadores aislados, sin conexión entre sí.
- 1969: Nace ARPANET, la primera red de ordenadores.
- Años 70: aparece el correo electrónico y las primeras conexiones remotas.
- Años 80: crece el uso de redes en empresas, surge el modelo OSI y se adopta TCP/IP.
- Años 90-2000: Internet se vuelve global con la World Wide Web.
- Hoy: conexiones inalámbricas, redes inteligentes y tecnología en la nube.
- Futuro: redes más rápidas, seguras y con inteligencia artificial.

### 1.3.4 Modelos de referencia

Como hemos visto, cuando las redes comenzaron a expandirse en los años 80, surgió un problema: cada empresa creaba su propia tecnología, lo que hacía difícil conectar sistemas diferentes. Para solucionar esta incompatibilidad, se desarrollaron modelos de referencia, que ayudan a organizar la comunicación entre dispositivos sin importar qué tecnología utilicen.

Los dos modelos más importantes son:

#### 1.3.4.1 El modelo OSI: un mapa teórico de la comunicación en red

En 1984, la Organización Internacional para la Estandarización (ISO) creó el modelo OSI (Open Systems Interconnection), con el objetivo de establecer un estándar universal para el diseño de redes.

**¿Para qué sirve?**
El modelo OSI es una estructura teórica que divide la comunicación en 7 capas, cada una con una función específica. No es un protocolo en sí, sino una referencia que ayuda a entender cómo deben comunicarse las redes.

**Las 7 capas del modelo OSI**

<div align="center">
    <img src="/primero-bach/img/modelo_osi.png" width="50%">
</div>

Imagina que envías un mensaje por WhatsApp. Cada capa del modelo OSI se encarga de una parte del proceso:

- Capa física → transmite los datos en forma de señales eléctricas, ópticas o inalámbricas (cables, WiFi).
- Capa de enlace de datos → organiza los datos en pequeños paquetes y los dirige dentro de una red local.
- Capa de red → encuentra la mejor ruta para que los datos lleguen a su destino (aquí entra la dirección IP).
- Capa de transporte → se asegura de que los datos lleguen completos y sin errores.
- Capa de sesión → administra la comunicación entre los dispositivos.
- Capa de presentación → codifica y traduce los datos para que sean legibles (por ejemplo, convierte imágenes o videos).
- Capa de aplicación → es la que interactúa con el usuario (WhatsApp, navegador web, correo electrónico).

Si enviamos un mensaje por WhatsApp, este baja desde la Capa 7 (Aplicación) hasta la Capa 1 (Física), viaja por la red y luego sube por las capas hasta llegar al destinatario.

#### 1.3.4.2 El modelo TCP/IP: la base de Internet

Aunque OSI es un buen modelo teórico, el modelo que realmente usamos es TCP/IP. Se desarrolló en los años 70 y fue adoptado en 1983 como el estándar de Internet.

**¿Para qué sirve?**
TCP/IP define cómo viaja la información en Internet y es el conjunto de protocolos en el que se basa toda la red global.

**Las 4 capas del modelo TCP/IP**
A diferencia de OSI, TCP/IP tiene solo 4 capas que agrupan varias funciones:

- Capa de enlace → controla el hardware y la transmisión de datos por cables o WiFi.
- Capa de Internet → se encarga de encontrar la mejor ruta para los datos usando direcciones IP.
- Capa de transporte → divide los datos en paquetes y verifica que lleguen correctamente (TCP es clave aquí).
- Capa de aplicación → es donde los programas interactúan con la red (navegadores, correos, WhatsApp).

#### 1.3.4.3 Diferencias clave entre OSI y TCP/IP

