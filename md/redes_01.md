# 1. Introducción a las redes informnáticas

Las redes informáticas son parte fundamental de nuestra vida diaria. Gracias a ellas, podemos comunicarnos, trabajar, estudiar y entretenernos. En esta unidad aprenderás cómo funcionan, cómo se conectan los dispositivos y cómo hacer que las redes sean seguras.

## 1.1 ¿Qué es una red informática?

Una **red informática** es un conjunto de dispositivos conectados entre sí que permiten enviar y recibir datos. Estos dispositivos pueden ser ordenadores, teléfonos, impresoras, servidores o incluso tu smartwatch.

📌 Imagina que en tu casa tienes varios dispositivos conectados al WiFi. Todos ellos pueden navegar por Internet y, en algunos casos, compartir archivos o impresoras. ¡Eso ya es una red!

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

Estos mainframes ocupaban salas enteras, generaban mucho calor y requerían personal especializado para operarlos. Debido a su elevado coste y mantenimiento, solo unas pocas universidades, empresas y gobiernos tenían acceso a ellos.

#### El Harvard Mark I: el inicio de la computación automatizada

Uno de los primeros mainframes de la historia fue el **Harvard Mark I (1944)**, una enorme máquina electromecánica diseñada para realizar cálculos matemáticos complejos de manera automática. Sin embargo, su uso no era nada sencillo.

Si quieres saber más sobre la Harvard Mark I, puedes consultar el siguiente [vídeo](https://www.youtube.com/watch?v=VE3eAKytjUc)

<div align="center">
    <figure>
        <img src="/primero-bach/img/mark1_2.jpg" width="50%">
        <figcaption><i>El Harvard Mark I (1944) fue un ordenador electromecánico creado por IBM y la Universidad de Harvard. Ubicado Massachusetts, usaba tarjetas perforadas y relés para automatizar cálculos matemáticos complejos.</i><figcaption>
    </figure>
</div>

**¿Cómo trabajaba un programador en el Mark I?**

Imaginemos a un programador de los años 40 intentando ejecutar su programa en el Harvard Mark I:

- **Escribir el código:** no existía un teclado ni pantalla como hoy en día. En su lugar, el programador tenía que escribir las instrucciones a mano y convertirlas en una serie de comandos específicos para la máquina.

- **Perforar tarjetas de papel:** una vez listo el programa, era necesario perforar cada una de las instrucciones en tarjetas de papel. Cada perforación representaba una instrucción o un dato. Si te equivocabas, había que repetir todo el proceso con una nueva tarjeta.

- **Ir a la mesa de control:** cualquiera no podía usar el Mark I. Había que esperar el turno y entregar las tarjetas perforadas a un operador, que se encargaba de introducirlas en la máquina.

- **Ejecutar el programa:** el operador colocaba las tarjetas en un lector especial y ponía en marcha el Mark I desde una mesa de control llena de interruptores, luces y diales. La máquina empezaba a trabajar, moviendo engranajes y relés electromagnéticos con un sonido rítmico característico.

- **Esperar el resultado:** como no existían pantallas, el Mark I imprimía los resultados en una máquina de escribir eléctrica o generaba nuevas tarjetas perforadas que luego debían interpretarse manualmente.

- **Corregir errores:** si algo salía mal, había que revisar todas las tarjetas perforadas y corregirlas una por una. No existía un "botón de borrar", y el proceso podía tardar horas o incluso días en completarse.

📌 **Dato curioso:** El Mark I tardaba seis segundos en multiplicar dos números y su sistema de relés electromecánicos lo hacía muy ruidoso. ¡Parecía una sala de máquinas de un barco en plena marcha!

Pronto, los científicos se dieron cuenta de que conectar varios ordenadores permitiría compartir información de forma más rápida y sin necesidad de transportar datos físicamente. En la década de 1950, algunas universidades comenzaron a experimentar con conexiones entre computadoras mediante cables, aunque eran muy lentas y limitadas.

Los mainframes marcaron el inicio de la informática moderna y sentaron las bases de lo que, años después, daría origen a las redes de ordenadores e Internet.

### 1.3.2 ARPANET: la red que cambió todo

En los años 60, en plena Guerra Fría, el Departamento de Defensa de EE.UU. buscaba una forma de comunicar computadoras a distancia sin que la información se perdiera en caso de un ataque enemigo. Así nació ARPANET, la primera red de computadoras.

**Momentos clave de ARPANET:**
- **1969** → Se envió el primer mensaje entre dos computadoras conectadas a ARPANET. 
- **1971** → Se envió el primer correo electrónico entre ordenadores.
- **1973** → ARPANET se hace internacional, conectando por primera vez ordenadores en Noruega y Reino Unido. Este fue un gran paso hacia la globalización de Internet.
- **1983** → Se implementa el protocolo TCP/IP, permitiendo la interconexión de redes y la expansión de lo que luego sería Internet.
- **1990** → ARPANET se apaga oficialmente, después de haber servido como el cimiento de la actual Internet. Su tecnología y estructura dieron paso a la red que hoy conecta al mundo.

📌 Dato curioso: En 1969, ARPANET envió su primer mensaje, pero… ¡falló en el segundo carácter! Querían escribir "LOGIN", pero solo llegó "LO" antes de que el sistema colapsara. 😅

### 1.3.3 La explosión de las redes en los años 80

En los años 80, las empresas comenzaron a descubrir las ventajas de conectar sus computadoras para compartir información y mejorar la productividad. Esto provocó un enorme crecimiento en la cantidad y el tamaño de las redes.

Sin embargo, hubo un problema: cada fabricante diseñaba su propia tecnología y no existía un estándar común. Esto significaba que, si una empresa tenía computadoras de diferentes marcas, muchas veces no podían comunicarse entre sí.

Para solucionar esto, en 1984, la Organización Internacional para la Estandarización (ISO) desarrolló el **modelo OSI** *(Open Systems Interconnection)*, que establecía una estructura estándar para la comunicación entre redes.

### 1.3.4 Internet: la red de redes

Mientras OSI sentaba las bases teóricas, el modelo TCP/IP se convirtió en el estándar real y funcional en el que se basa Internet.

- **Años 90:** la World Wide Web (WWW) hace que Internet sea accesible para todos, no solo para científicos y militares.
- **2000 en adelante:** con la llegada de la banda ancha, el WiFi y los dispositivos móviles, las redes evolucionaron a lo que conocemos hoy.

📌 Dato curioso: El primer sitio web de la historia fue creado en 1991 por Tim Berners-Lee. ¡Y todavía está en línea! Puedes verlo 👉 [aquí](http://info.cern.ch)

### 1.3.5 Modelos de referencia

Como hemos visto, cuando las redes comenzaron a expandirse en los años 80, surgió un problema: cada empresa creaba su propia tecnología, lo que hacía difícil conectar sistemas diferentes. Para solucionar esta incompatibilidad, se desarrollaron modelos de referencia, que ayudan a organizar la comunicación entre dispositivos sin importar qué tecnología utilicen.

Los dos modelos más importantes son:

#### 1.3.5.1 El modelo OSI: un mapa teórico de la comunicación en red

En 1984, la Organización Internacional para la Estandarización (ISO) creó el modelo OSI (Open Systems Interconnection), con el objetivo de establecer un estándar universal para el diseño de redes.

**¿Para qué sirve?**
El modelo OSI es una estructura teórica que divide la comunicación en 7 capas, cada una con una función específica. No es un protocolo en sí, sino una referencia que ayuda a entender cómo deben comunicarse las redes.

**Las 7 capas del modelo OSI**

<div align="center">
    <img src="/primero-bach/img/modelo_osi2.png" width="50%">
</div>

Imagina que envías un mensaje por WhatsApp. Cada capa del modelo OSI se encarga de una parte del proceso:

- **Capa física** → transmite los datos en forma de señales eléctricas, ópticas o inalámbricas (cables, WiFi).
- **Capa de enlace de datos** → organiza los datos en pequeños paquetes y los dirige dentro de una red local.
- **Capa de red** → encuentra la mejor ruta para que los datos lleguen a su destino (aquí entra la dirección IP).
- **Capa de transporte** → se asegura de que los datos lleguen completos y sin errores.
- **Capa de sesión** → administra la comunicación entre los dispositivos.
- **Capa de presentación** → codifica y traduce los datos para que sean legibles (por ejemplo, convierte imágenes o videos).
- **Capa de aplicación** → es la que interactúa con el usuario (WhatsApp, navegador web, correo electrónico).

Si enviamos un mensaje por WhatsApp, este baja desde la Capa 7 (Aplicación) hasta la Capa 1 (Física), viaja por la red y luego sube por las capas hasta llegar al destinatario.

#### 1.3.5.2 El modelo TCP/IP: la base de Internet

Aunque OSI es un buen modelo teórico, el modelo que realmente usamos es TCP/IP. Se desarrolló en los años 70 y fue adoptado en 1983 como el estándar de Internet.

**¿Para qué sirve?**
TCP/IP define cómo viaja la información en Internet y es el conjunto de protocolos en el que se basa toda la red global.

**Las 4 capas del modelo TCP/IP**
A diferencia de OSI, TCP/IP tiene solo 4 capas que agrupan varias funciones:

- **Capa de enlace** → controla el hardware y la transmisión de datos por cables o WiFi.
- **Capa de Internet** → se encarga de encontrar la mejor ruta para los datos usando direcciones IP.
- **Capa de transporte** → divide los datos en paquetes y verifica que lleguen correctamente (TCP es clave aquí).
- **Capa de aplicación** → es donde los programas interactúan con la red (navegadores, correos, WhatsApp).

Los modelos OSI y TCP/IP han permitido que diferentes dispositivos y tecnologías se comuniquen sin problemas. Gracias a ellos, hoy podemos navegar por Internet, enviar correos, ver videos en streaming y chatear desde cualquier lugar del mundo

# Resumen de la evolución de las redes

- **1950-1960:** ordenadores aislados, sin conexión entre sí.
- **1969:** nace ARPANET, la primera red de ordenadores.
- **Años 70:** aparece el correo electrónico y las primeras conexiones remotas.
- **Años 80:** crece el uso de redes en empresas, surge el modelo OSI y se adopta TCP/IP.
- **Años 90-2000:** Internet se vuelve global con la World Wide Web.
- **Hoy:** conexiones inalámbricas, redes inteligentes y tecnología en la nube.
- **Futuro:** redes más rápidas, seguras y con inteligencia artificial.
