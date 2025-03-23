# 3. Elementos físicos de una red

## 3.1 Introducción 

Para que una red funcione correctamente, se necesita una serie de elementos que pueden clasificarse en tres grandes grupos:
- **Dispositivos finales (o nodos):** los que usamos directamente, como ordenadores o móviles.
- **Dispositivos de red:** gestionan el tráfico de datos entre los dispositivos.
- **Medios de transmisión:** los canales por donde viaja la información, como cables o señales inalámbricas.

## 3.2 Dispositivos de una red

### 3.2.1 Dispositivos finales

Son los usuarios finales de la red, es decir, los equipos con los que interactuamos directamente.
- **Ordenadores (de sobremesa y portátiles):** permiten navegar por Internet, acceder a archivos en red o comunicarse con otros equipos. 
- **Teléfonos inteligentes y tablets:** acceden a la red mediante Wi-Fi o redes móviles para chatear, ver vídeos o usar apps.
- **Servidores:** almacenan información para que otros dispositivos la consulten. Por ejemplo, un servidor web almacena páginas web.
- **Impresoras y periféricos en red:** pueden ser compartidos por varios usuarios sin conexión física directa.

Estos dispositivos se llaman también **hosts o nodos finales**. Son los puntos donde nace o termina la información que circula por la red.

### 3.2.2 Dispositivos de red

Son los intermediarios que hacen posible la conexión y la comunicación entre dispositivos finales. Se encargan de dirigir y controlar el flujo de datos para que llegue al destino correcto.

#### Básicos
Son esenciales para la creación y funcionamiento de una red informática.
- **Hub:** envía los datos a todos los dispositivos conectados. No es eficiente, por eso hoy casi no se usa.
- **Switch:** mucho más inteligente que el hub. Envía los datos solo al destinatario correcto, mejorando el rendimiento de la red. existen distintos tipos de switches según sus características y usos:
    - **Switch no gestionable:** es el más sencillo y económico, no requiere configuración y funciona automáticamente, por lo que es ideal para redes domésticas o pequeñas oficinas. 
    - **Switch gestionable:** permite configurar opciones avanzadas como VLANs y control de tráfico, siendo apropiado para redes profesionales o educativas que necesitan mayor control y seguridad.
    - **Switch con PoE (Power over Ethernet):** puede alimentar dispositivos como cámaras IP o puntos de acceso WiFi a través del mismo cable de red que transmite los datos, lo que lo hace muy útil en instalaciones donde no se dispone de tomas de corriente cerca de los dispositivos.
- **Router:** conecta distintas redes entre sí (por ejemplo, una red local con Internet). También reparte direcciones IP dentro de la red.
- **Módem:** convierte la señal de Internet del proveedor (fibra, ADSL, cable) en señal digital para nuestros dispositivos. A menudo está integrado dentro del router.

#### Complementarios
Son dispositivos que mejoran la cobertura, estabilidad y alcance de la red.
- **Punto de acceso (*Access Point, AP*):** dispositivo que permite conectar dispositivos inalámbricos a una red cableada, ampliando la cobertura Wi-Fi y mejorando la conectividad en zonas con señal débil o inexistente. Se usa en oficinas, empresas y grandes espacios donde la cobertura de un router no es suficiente.
- **Repetidor Wi-Fi:** dispositivo que capta una señal WiFi existente y la retransmite para ampliar su cobertura en zonas con baja conectividad. A diferencia del punto de acceso, no se conecta por cable, lo que puede reducir su velocidad en algunos casos.
- **Firewall (cortafuegos):** dispositivo de seguridad que protege la red frente a accesos no autorizados y ciberataques, filtrando el tráfico de datos. Puede estar integrado en el router o ser un equipo independiente, aunque también existen versiones en software.

## 3.3 Medios de transmisión

Son los canales a través de los cuales viajan los datos en la red. Se dividen en medios cableados e inalámbricos.

#### 3.3.1 Medios cableados

Los datos se transmiten a través de cables físicos, como **cables de cobre o fibra óptica**, ofreciendo una conexión más estable y segura.

##### Cable coaxial
Antiguamente se usaba en redes locales, pero hoy en día se emplea más en televisión por cable y sistemas de videovigilancia. Tiene una buena resistencia a interferencias, pero ha sido reemplazado en muchas redes por otros tipos de cable de mejor rendimiento y más fáciles de instalar.

<div align="center">
    <img src="/primero-bach/img/coaxial.jpg" width="30%">
</div>

##### Par trenzado
Es el cable más utilizado en redes Ethernet (las que usan cable para conectarse a Internet). Está compuesto por pares de hilos de cobre trenzados, lo que ayuda a reducir interferencias. Se conecta a los dispositivos mediante conectores RJ-45 y se clasifica según su tipo de apantallamiento y categoría de rendimiento. Estos vienen impresos en la propia cubierta de plástico del cable, por lo que es posible identificarlos con solo echar un vistazo.

Según su tipo de apantallamiento, los cables de par trenzado pueden ser:
- **UTP (*Unshielded Twisted Pair*):** sin apantallamiento adicional, solo protege por el trenzado de los hilos. Es el más común en redes domésticas y de oficina.
- **FTP (*Foiled Twisted Pair*):** tiene una lámina de aluminio que cubre todos los pares, ofreciendo mayor protección sin perder flexibilidad. Se usa en lugares con cableado eléctrico cercano.
- **STP (*Shielded Twisted Pair*):** cada par de hilos tiene su propia malla metálica, lo que brinda la mejor protección contra interferencias. Se usa en entornos industriales o con muchos dispositivos electrónicos.
- **SFTP (*Shielded and Foiled Twisted Pair*):** combina una lámina de aluminio general que recubre todos los pares (como el FTP) y una malla metálica individual para cada par (como el STP). Ofrece una protección superior frente a interferencias electromagnéticas y de radiofrecuencia. Es ideal para entornos muy exigentes donde la integridad de la señal es crítica, como centros de datos o instalaciones con alta densidad de equipos electrónicos.

<div align="center">
    <img src="/primero-bach/img/par_trenzado.webp" width="40%">
</div>

La categoría indica el nivel de velocidad y rendimiento del cable:
- **Cat 5e:** hasta 1 Gbps en 100 metros. Mejor que el Cat 5 en reducción de interferencias.
- **Cat 6:** hasta 10 Gbps en 55 metros. Mayor aislamiento frente a interferencias.
- **Cat 7 y superiores:** mejor rendimiento, mayor velocidad y más blindaje. Usados en centros de datos y redes de alto rendimiento.

⚠️ **Dato importante:** cuidado si contratas un servicio de Internet de, por ejemplo, 600 Mbps, pero utilizáis un cable de categoría 5, ya que estarás limitando la velocidad a la máxima que permite el cable (en este caso, 100 Mbps).

##### Fibra óptica 
En lugar de cobre, usa **hilos delgados de vidrio o plástico** para transmitir datos mediante **pulsos de luz**, lo que permite mayores velocidades y distancias sin pérdida de señal. Es la tecnología más usada hoy en día para conexiones de Internet rápidas, como las que instalan los operadores en hogares y empresas.

- **Fibra monomodo:** transmite un único haz de luz en línea recta sin rebotes, lo que reduce la pérdida de señal y permite alcanzar distancias superiores a 100 km con alta velocidad. Se usa en conexiones de larga distancia, como la comunicación entre distintas ciudades o países.
- **Fibra multimodo:** permite la transmisión de varios haces de luz simultáneamente, los cuales rebotan dentro del núcleo de la fibra. Es más económica y fácil de instalar, aunque pierde calidad con la distancia. Se utiliza en redes dentro de edificios, universidades, centros de datos y oficinas, con un alcance de hasta 2 km.

<div align="center">
    <img src="/primero-bach/img/tipos_fibra.webp" width="40%">
</div>

Para conectar la fibra óptica a los dispositivos de red, se utilizan diferentes tipos de conectores, según el tipo de instalación y equipo utilizado. Los más comunes son: SC, LC, ST, FC, entre otros.

#### 3.3.2 Medios inalámbricos

Transmiten información a través de **ondas electromagnéticas**, eliminando la necesidad de cables físicos. Son más flexibles y permiten movilidad, aunque pueden ser más vulnerables a interferencias y variaciones en la señal.

##### WiFi (Wireless Fidelity)
Tecnología que permite conectar dispositivos a Internet sin necesidad de cables. Se utiliza en hogares, oficinas y lugares públicos. Su velocidad y alcance dependen de la versión:
- **Wi-Fi 4:** Hasta 600 Mbps.
- **Wi-Fi 5:** Hasta 1.3 Gbps, mayor estabilidad.
- **Wi-Fi 6:** Hasta 9.6 Gbps, mejor cobertura y menor latencia.
- **Wi-Fi 7 (en desarrollo):** Mejor rendimiento y capacidad para entornos con múltiples dispositivos conectados.

Cuanto más reciente es la versión, mayor velocidad y mejor cobertura ofrece. No obstante, también depende del router y de si los dispositivos son compatibles con esa versión.

##### Bluetooth
Tecnología diseñada para la transmisión de datos a corta distancia, , donde no se necesita gran velocidad, pero sí comodidad y bajo consumo de energía. Por ejemplo como en auriculares, ratones, teclados inalámbricos y algunos dispositivos inteligentes.
- **Bluetooth 4.0 - 4.2:** bajo consumo de energía, ideal para wearables y accesorios inteligentes.
- **Bluetooth 5.0:** mayor alcance (hasta 240 metros) y mejor rendimiento en la transmisión de datos.

##### Redes móviles y satélites
Se utilizan en comunicaciones de larga distancia. Por ejemplo:
- **Redes móviles 4G y 5G**, que permiten la conexión a Internet desde teléfonos y dispositivos móviles.
- **Internet por satélite**, útil en zonas donde no llega la fibra óptica, como en áreas rurales o en barcos.

# Ejercicios

**1. Comparativa de switches**. Investiga al menos tres modelos de switches que se venden actualmente. Anota:
- Marca y modelo
- Foto y enlace a la web donde lo has encontrado 
- Número de puertos
- Velocidad (100 Mbps, 1 Gbps…)
- Si son gestionables o no
- Precio aproximado
- Ejemplo de búsqueda: “switch 8 puertos Gigabit Amazon” o en la web de fabricantes como TP-Link, D-Link o Cisco.

**2. Busca un router doméstico**. Anota sus características principales:
- Marca y modelo
- Foto y enlace a la web donde lo has encontrado
- Version Wi-Fi que ofrece
- Número de puertos LAN
- Si integra módem o no

**3. Sobre cableado**. Encuentra un cable Cat 6 y un Cat 5e en una tienda online. Compara:
- Foto y enlace a la web donde lo has encontrado
- Precio por metro
- Diferencias visibles o especificaciones destacadas
- ¿Por qué el Cat 6 es más caro?

**4. Sobre par trenzado**. Lee cada una de las siguientes situaciones y elige el tipo de cable de par trenzado más adecuado (UTP, FTP, STP o SFTP). Justifica tu elección brevemente con una frase.<br>
A. Una vivienda particular donde solo se va a conectar un router al ordenador mediante cable de red y no hay interferencias eléctricas cerca.<br>
B. Una oficina con impresoras y ordenadores donde el cableado pasa muy cerca de tubos fluorescentes y enchufes múltiples.<br>
C. Una fábrica con maquinaria industrial y motores eléctricos que generan muchas interferencias electromagnéticas.<br>
D. Un centro de datos de alto rendimiento, donde hay cientos de servidores y switches en armarios de red muy próximos entre sí.<br>








