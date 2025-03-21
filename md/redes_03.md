# 3. Elementos y estructura de una red

## 3.1 Elementos de una red informática

Una red informática es un conjunto de dispositivos interconectados que permiten la comunicación y el intercambio de datos. Para que una red funcione, es necesario contar con varios elementos fundamentales, que se dividen en dispositivos finales, dispositivos de red y medios de transmisión.

### 3.1.1 Dispositivos finales

Son los equipos que los usuarios utilizan para enviar y recibir información en una red. Algunos ejemplos son:

- **Ordenadores (PCs y portátiles):** permiten acceder a internet, compartir archivos y ejecutar programas en red.
- **Teléfonos inteligentes y tablets:** se conectan a la red a través de WiFi o datos móviles para la comunicación y el acceso a servicios en línea.
- **Servidores:** equipos que almacenan y distribuyen información dentro de una red. Pueden alojar páginas web, bases de datos, archivos compartidos, etc.
- **Impresoras y otros periféricos en red:** permiten compartir recursos sin necesidad de conexión directa a cada dispositivo.

Todos estos dispositivos se conocen también como **hosts o nodos finales**, ya que son el punto de origen o destino de la información dentro de la red.

### 3.1.2 Dispositivos de red

Son los encargados de gestionar el tráfico de datos dentro de la red, asegurando que la información llegue a su destino.

#### 3.1.2.1 Básicos
Son esenciales para la creación y funcionamiento de una red informática.
- **Hub:** dispositivo simple que replica los datos a todos los dispositivos conectados. Ya no se usa mucho porque no optimiza el tráfico de la red.
- **Switch:** similar al hub, pero más inteligente. Solo envía los datos al dispositivo al que están destinados, mejorando la eficiencia de la red.

<div align="center">
    <figure>
        <img src="/primero-bach/img/switch.png" width="30%">
        <figcaption><i>Switch con 8 puertos Gigabit Ethernet (1000 Mbps)</i><figcaption>
    </figure>
</div>

- **Router:** permite conectar diferentes redes entre sí y gestionar la conexión a Internet. Es el dispositivo clave para el acceso a la red en hogares y empresas.
- **Módem:** dispositivo que convierte la señal del proveedor de Internet (fibra óptica, ADSL, cable, etc.) en una señal digital que los dispositivos pueden usar. En la mayoría de los casos, el módem está integrado dentro del router.

#### 3.1.2.2 Complementarios
Son dispositivos que mejoran la cobertura, estabilidad y alcance de la red.
- **Punto de acceso (*Access Point, AP*):** dispositivo que permite conectar dispositivos inalámbricos a una red cableada, ampliando la cobertura Wi-Fi y mejorando la conectividad en zonas con señal débil o inexistente. Se usa en oficinas, empresas y grandes espacios donde la cobertura de un router no es suficiente.
- **Repetidor Wi-Fi:** dispositivo que capta una señal WiFi existente y la retransmite para ampliar su cobertura en zonas con baja conectividad. A diferencia del punto de acceso, no se conecta por cable, lo que puede reducir su velocidad en algunos casos.
- **Firewall (cortafuegos):** dispositivo de seguridad que protege la red frente a accesos no autorizados y ciberataques, filtrando el tráfico de datos. Puede estar integrado en el router o ser un equipo independiente, aunque también existen versiones en software.

### 3.1.3 Medios de transmisión

Son los canales a través de los cuales viajan los datos en la red. Se dividen en medios cableados e inalámbricos.

#### 3.1.3.1 Medios cableados

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

Cuidado si contratáis un servicio de Internet de, por ejemplo, 600 Mbps, pero utilizáis un cable de categoría 5, ya que estaréis limitando la velocidad a la máxima que permite el cable (en este caso, 100 Mbps).

##### Fibra óptica 
En lugar de cobre, usa **hilos delgados de vidrio o plástico** para transmitir datos mediante **pulsos de luz**, lo que permite mayores velocidades y distancias sin pérdida de señal. Es la tecnología más usada hoy en día para conexiones de Internet rápidas, como las que instalan los operadores en hogares y empresas.

- **Fibra monomodo:** transmite un único haz de luz en línea recta sin rebotes, lo que reduce la pérdida de señal y permite alcanzar distancias superiores a 100 km con alta velocidad. Se usa en conexiones de larga distancia, como la comunicación entre distintas ciudades o países.
- **Fibra multimodo:** permite la transmisión de varios haces de luz simultáneamente, los cuales rebotan dentro del núcleo de la fibra. Es más económica y fácil de instalar, aunque pierde calidad con la distancia. Se utiliza en redes dentro de edificios, universidades, centros de datos y oficinas, con un alcance de hasta 2 km.

Para conectar la fibra óptica a los dispositivos de red, se utilizan diferentes tipos de conectores, según el tipo de instalación y equipo utilizado. Los más comunes son: SC, LC, ST, FC, entre otros.

#### 3.1.3.2 Medios inalámbricos

Transmiten información a través de **ondas electromagnéticas**, eliminando la necesidad de cables físicos. Son más flexibles y permiten movilidad, aunque pueden ser más vulnerables a interferencias y variaciones en la señal.

##### WiFi (Wireless Fidelity)
Tecnología que permite conectar dispositivos a Internet sin necesidad de cables. Se utiliza en hogares, oficinas y lugares públicos. Su velocidad y alcance dependen de la versión:
- Wi-Fi 4 (802.11n): Hasta 600 Mbps.
- Wi-Fi 5 (802.11ac): Hasta 1.3 Gbps, mayor estabilidad.
- Wi-Fi 6 (802.11ax): Hasta 9.6 Gbps, mejor cobertura y menor latencia.
- Wi-Fi 7 (en desarrollo): Mejor rendimiento y capacidad para entornos con múltiples dispositivos conectados.

Cuanto más reciente es la versión, mayor velocidad y mejor cobertura ofrece. No obstante, también depende del router y de si los dispositivos son compatibles con esa versión.

##### Bluetooth
Tecnología diseñada para la transmisión de datos a corta distancia, , donde no se necesita gran velocidad, pero sí comodidad y bajo consumo de energía. Por ejemplo como en auriculares, ratones, teclados inalámbricos y algunos dispositivos inteligentes.
- Bluetooth 4.0 - 4.2: bajo consumo de energía, ideal para wearables y accesorios inteligentes.
- Bluetooth 5.0: mayor alcance (hasta 240 metros) y mejor rendimiento en la transmisión de datos.

##### Redes móviles y satélites
Se utilizan en comunicaciones de larga distancia. Por ejemplo:
    - Redes móviles 4G y 5G, que permiten la conexión a Internet desde teléfonos y dispositivos móviles.
    - Internet por satélite, útil en zonas donde no llega la fibra óptica, como en áreas rurales o en barcos.

## 3.2 Estructura de una red local
- Diseño básico de una LAN.
- Subredes y segmentación de redes.
- Introducción a VLANs (Redes de Área Local Virtuales).

## 3.3 Protocolo de direccionamiento en redes
- Funcionamiento del direccionamiento IPv4 e IPv6.
- Subnetting: concepto y utilidad.
- DHCP: asignación dinámica de direcciones.

## 3.4 El acceso a Internet y redes WAN
- Cómo funciona el acceso a Internet (ISP, DNS, NAT)
- Conexiones de redes WAN: MPLS, VPN, enlaces satelitales, redes 5G


