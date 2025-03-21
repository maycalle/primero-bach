# 2. Tipos de redes y su estructura

Hasta ahora, hemos explorado qué son las redes informáticas, su evolución histórica y los modelos de comunicación que permiten la conexión entre dispositivos. Ahora profundizaremos en los diferentes tipos de redes, cómo se estructuran y los medios a través de los cuales transmiten información.

## 2.1 Dispositivos de red

Los dispositivos de red permiten la conexión, gestión y flujo de datos entre distintos equipos dentro de una red. Su función es esencial para garantizar la comunicación eficiente entre computadoras, servidores y otros dispositivos en redes domésticas, empresariales e industriales.

A continuación, se describen los principales dispositivos de red y su función:

### 2.1.1 Hub
Un hub es un dispositivo de red que permite conectar múltiples dispositivos dentro de una misma red local (LAN). Su función principal es recibir los datos de un dispositivo y enviarlos a todos los demás dispositivos conectados, sin distinguir el destinatario correcto. Cuantos más dispositivos estén conectados, más tráfico se genera, lo que puede ralentizar la red.

Aunque fue común en las primeras redes, hoy en día ha sido sustituido por switches, que son más rápidos y optimizados.

#### Funciones principales
- Conectar dispositivos en una LAN: permite que ordenadores, impresoras y otros dispositivos puedan comunicarse entre sí dentro de la misma red.
- Repetir la señal: recibe datos de un dispositivo y los retransmite a todos los demás dispositivos conectados, sin filtrar destinatarios.
- Extender la red: se usa para ampliar el número de dispositivos que pueden conectarse a una red cuando hay pocos puertos disponibles.

### 2.1.2 Switch
Un switch es un dispositivo de red que conecta múltiples dispositivos dentro de una misma red local (LAN) y permite que intercambien datos de manera eficiente. Se encarga de recibir, procesar y enviar paquetes de datos solo al dispositivo de destino correcto, optimizando el tráfico y evitando colisiones. Por ejemplo, en una oficina con varios ordenadores, impresoras y servidores, el switch permite que todos se comuniquen entre sí sin interferencias, mejorando la velocidad y el rendimiento de la red.

#### Funciones principales
- Interconectar dispositivos en una red local (LAN): permite que ordenadores, impresoras, cámaras de seguridad y otros dispositivos se comuniquen directamente sin necesidad de acceder a Internet.
- Optimizar el tráfico de datos: a diferencia de un hub, que envía los datos a todos los dispositivos conectados, el switch identifica la dirección del destinatario y solo envía la información a quien corresponde, evitando tráfico innecesario.
- Asignar ancho de banda de manera eficiente: un switch administra la velocidad de cada conexión para que los dispositivos reciban el ancho de banda necesario sin sobrecargar la red.

### 2.1.3 Router
Un router es un dispositivo de red que dirige el tráfico de datos entre diferentes dispositivos y redes, permitiendo la conexión a Internet y la comunicación dentro de una red local. Cuando te conectas al Wi-Fi de casa, tu móvil o portátil se comunica con el router, y este se encarga de enviar y recibir datos de Internet.

#### Funciones principales
- Conectar dispositivos a Internet: actúa como un intermediario entre los dispositivos de una red local (móvil, ordenador, Smart TV, etc.) e Internet. Recibe la señal de Internet del proveedor (por fibra óptica, ADSL o cable) y la distribuye a los dispositivos.
- Asignar direcciones IP internas: para que los dispositivos dentro de una misma red puedan comunicarse, el router les asigna direcciones IP privadas mediante un sistema llamado DHCP.
Esto evita que haya conflictos de direcciones IP y organiza el tráfico de datos dentro de la red.
- Dirigir los datos de manera eficiente: analiza los datos que recibe y decide la mejor ruta para enviarlos a su destino, asegurando que la información llegue de forma rápida y sin interferencias.
- Proporcionar conexión inalámbrica (Wi-Fi): la mayoría de los routers incluyen una función de punto de acceso Wi-Fi, permitiendo que los dispositivos se conecten sin cables.
También pueden funcionar con redes cableadas (Ethernet), que son más estables y rápidas.
- Seguridad y control de la red: incluyen firewalls y sistemas de cifrado para proteger la red contra accesos no autorizados. Permiten configurar contraseñas Wi-Fi, control parental y restricciones de acceso para mejorar la seguridad.

#### Partes de un router
- Puertos Ethernet: Para conectar dispositivos mediante cable.
- Antenas Wi-Fi: Emiten la señal inalámbrica.
- Puerto WAN: Se conecta al módem o a la red del proveedor de Internet.
- Fuente de alimentación: Proporciona energía al dispositivo.
- Botón de reinicio (Reset): Permite restaurar la configuración en caso de fallos.

### 2.1.4 Punto de acceso
Un Punto de Acceso (AP) es un dispositivo que permite conectar dispositivos inalámbricos a una red cableada, ampliando la cobertura Wi-Fi y mejorando la conectividad en zonas con señal débil o inexistente.

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

La topología de una red especifica la forma física que tendrá. A continuación, exploramos las más comunes:

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

### 2.2.4 Según su nivel de acceso o privacidad

Las redes pueden clasificarse según el nivel de acceso permitido a los usuarios. Algunas están restringidas a ciertos grupos o instituciones, mientras que otras son de acceso libre. También existen redes híbridas que combinan ambas características.

#### Redes privadas
Son redes cerradas y seguras, donde solo los usuarios autorizados pueden acceder y utilizar sus servicios. Se usan en empresas, instituciones y organizaciones para garantizar privacidad y control. Por ejemplo, la red interna de una empresa a la que solo pueden acceder empleados desde sus oficinas.

Si la red privada ofrece servicios como páginas web, correo electrónico o almacenamiento de archivos solo accesibles para sus miembros, se denomina **Intranet**. Es común en universidades, hospitales y corporaciones.

#### Redes públicas
Son abiertas a cualquier usuario, permitiendo la comunicación y el intercambio de información sin restricciones de acceso. Sin embaro, pueden ser menos seguras, ya que cualquier usuario puede conectarse sin autenticación.

- Internet, la red pública global.
- Wi-Fi gratuito en cafeterías, bibliotecas o aeropuertos.
- Redes móviles 4G/5G accesibles sin credenciales especiales.

#### Redes híbridas
Combinan elementos de redes privadas y públicas. Algunas partes son accesibles para cualquier usuario, mientras que otras requieren autorización. Por ejemplo, una universidad que ofrece Wi-Fi público para estudiantes y visitantes, pero restringe el acceso a ciertos sistemas administrativos o bases de datos internas solo para empleados.

#### VPN (Virtual Private Network)
Una VPN no es una red en sí misma, sino una tecnología que crea un canal seguro para acceder a una red privada a través de Internet. Se usa para proteger datos y garantizar privacidad en conexiones remotas. La VPN crea un túnel seguro y cifrado entre el usuario y la red privada, evitando que terceros puedan interceptar la información.

Por ejemplo, un empleado que trabaja desde casa usa una VPN corporativa para conectarse a la red privada de su empresa y acceder a documentos internos como si estuviera en la oficina. También se usa para mejorar la privacidad en redes públicas, evitando que los proveedores de Internet o hackers puedan rastrear la actividad del usuario.


