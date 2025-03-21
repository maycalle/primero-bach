# 2. Tipos de redes

En el mundo actual, cada vez más conectado, las redes informáticas permiten la comunicación y el intercambio de datos entre todo tipo de dispositivos. Sin embargo, no todas las redes son iguales.  En esta unidad, exploraremos los diferentes tipos de redes según su **área de cobertura**, su **topología** y su **privacidad**.

Cada una de estas clasificaciones determina cómo se conectan los dispositivos y cómo circula la información dentro de la red.

## 2.1 Según su área de cobertura

Este criterio clasifica las redes según la distancia que abarcan y el tamaño del área en la que operan. 
 
### 2.1.1 WAN (Wide Area Network, Red de Área Extensa) 
- Las **redes WAN** conectan dispositivos que se encuentran en **grandes áreas geográficas**, como ciudades, países o incluso continentes.
- Utilizan una combinación de tecnologías para lograr esta conexión a gran escala: 
    - **Cables de fibra óptica**, como los cables submarinos (por ejemplo, el cable “Marea” que conecta Europa con Estados Unidos, con una capacidad de 160 Terabits por segundo).
    - **Redes móviles 4G y 5G**, en áreas urbanas y suburbanas, que permiten velocidades de hasta 10 Gbps.
    - **Satélites de comunicaciones**, para zonas remotas o de difícil acceso donde el cableado no es viable.    
- El ejemplo más representativo de una WAN es Internet, que interconecta millones de dispositivos a nivel global.

### 2.1.2 MAN (Metropolitan Area Network, Red de Área Metropolitana)
- Las **redes MAN** conectan **varios edificios** (como oficinas, centros de salud, campus universitarios…) dentro de una misma ciudad o región.
- Suelen utilizar **fibra óptica** para ofrecer alta velocidad y gran capacidad de transmisión.
- También se emplean tecnologías como **WiMAX** (inalámbrica, hasta 50 km) o **anillos de fibra** con protocolos como FDDI o SDH/SONET.
- Un ejemplo de MAN sería una red de fibra óptica que conecta las distintas sedes de una empresa en una ciudad.

### 2.1.3 LAN (Local Area Network, Red de Área Local)
- Las **redes LAN** funcionan en **espacios reducidos**, como hogares, aulas, oficinas o laboratorios.
- Permiten velocidades muy altas y son fáciles de gestionar.
- Las tecnologías más habituales son:
    - **Ethernet (IEEE 802.3)** con cables de par trenzado o fibra óptica.
    - **Wi-Fi (IEEE 802.11)** para conexiones inalámbricas, con estándares como Wi-Fi 6 (802.11ax) y el futuro Wi-Fi 7, que mejoran la velocidad y la eficiencia.
    - **PLC**, que transmite datos a través del cableado eléctrico.
- Un ejemplo de red LAN es la red de un colegio donde los ordenadores están conectados por cable Ethernet o por Wi-Fi.

### 2.1.4 PAN (Personal Area Network, Red de Área Personal)
- Las **redes PAN** conectan dispositivos cercanos dentro de un radio de **pocos metros**, facilitando la comunicación entre periféricos y dispositivos personales.
- Se basan en tecnologías inalámbricas de corto alcance:
    - **Bluetooth (IEEE 802.15.1)** permite conectar dispositivos a distancias de hasta 10 metros, siendo común en auriculares, teclados y ratones. 
    - **NFC (Near Field Communication)** posibilita la comunicación en distancias aún más cortas, ideales para pagos móviles y tarjetas de acceso.     
- Un ejemplo de red PAN es un smartphone conectado a auriculares Bluetooth o a un smartwatch.

<div align="center">
    <img src="/primero-bach/img/tipos_redes_extension.png" width="40%">
</div>

Cuando estas redes utilizan conexiones inalámbricas, se antepone la letra W (Wireless) al nombre de la red:
- **WLAN (Wireless LAN):** versión inalámbrica de una LAN, basada en WiFi.
- **WPAN (Wireless PAN):** versión inalámbrica de una PAN, como Bluetooth o NFC.

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


## 2.2 Según su topología

La topología de una red especifica la forma física que tendrá. A continuación, exploramos las más comunes:

### 2.2.1 Topologia en bus
Todos los dispositivos están conectados a un único cable principal (bus o troncal), que transporta los datos en ambas direcciones.
- Es fácil y económica de implementar.
- Si el cable principal se daña, toda la red falla.
- A medida que se agregan más dispositivos, la velocidad disminuye por la congestión en el bus.

Ejemplo: Redes locales antiguas con cable coaxial en oficinas o escuelas.

### 2.2.2 Topología en estrella
En esta configuración, todos los dispositivos están conectados a un nodo central (como un switch o un router).
- El nodo central controla toda la comunicación.
- Si un dispositivo falla, el resto de la red sigue funcionando.
- Si el nodo central falla, la red completa deja de operar.

Ejemplo: Las redes WiFi domésticas donde todos los dispositivos se conectan a un router.

### 2.2.3 Topología en anillo
Los dispositivos están conectados en círculo y los datos viajan en una sola dirección o en ambas.
- No hay nodo central, por lo que no depende de un único punto de fallo.
- Es eficiente para transmitir datos, pero si un dispositivo falla, toda la red se interrumpe.
- Puede ser lenta en redes grandes, ya que los datos deben pasar por cada nodo.

Ejemplo: Redes en estaciones de trabajo o antiguas redes de fibra óptica.

### 2.2.4 Topología en malla
Cada dispositivo está conectado a varios otros de forma redundante, lo que crea múltiples caminos para enviar los datos.
- Es muy fiable porque si un enlace falla, los datos encuentran otro camino.
- Alta velocidad y rendimiento.
- Es costosa y compleja de implementar por la cantidad de cables y conexiones necesarias.

Ejemplo: Internet en su conjunto funciona con una topología de malla parcial, donde hay múltiples rutas entre servidores y dispositivos.

### 2.2.5 Topología híbrida
Combina dos o más de las topologías anteriores, adaptándose a las necesidades específicas de la red.
- Es muy flexible y escalable.
- Puede integrar lo mejor de cada topología.
- Puede ser costosa y compleja de administrar.

Ejemplo: Redes empresariales donde los departamentos pueden tener topología en estrella, pero conectarse entre sí mediante malla o bus.


<div align="center">
    <img src="/primero-bach/img/topologias-de-red-1.jpg" width="60%">
</div>

Cada topología tiene sus ventajas y desventajas, y la elección depende del costo, rendimiento y seguridad que se necesite. En la actualidad, las más utilizadas son estrella y malla, debido a su eficiencia y estabilidad.

## 2.3 Según su nivel de acceso o privacidad

Las redes pueden clasificarse según el nivel de acceso permitido a los usuarios. Algunas están restringidas a ciertos grupos o instituciones, mientras que otras son de acceso libre. También existen redes híbridas que combinan ambas características.

### 2.3.1 Redes privadas
Son redes cerradas y seguras, donde solo los usuarios autorizados pueden acceder y utilizar sus servicios. Se usan en empresas, instituciones y organizaciones para garantizar privacidad y control. Por ejemplo, la red interna de una empresa a la que solo pueden acceder empleados desde sus oficinas.

Si la red privada ofrece servicios como páginas web, correo electrónico o almacenamiento de archivos solo accesibles para sus miembros, se denomina **Intranet**. Es común en universidades, hospitales y corporaciones.

### 2.3.2 Redes públicas
Son abiertas a cualquier usuario, permitiendo la comunicación y el intercambio de información sin restricciones de acceso. Sin embaro, pueden ser menos seguras, ya que cualquier usuario puede conectarse sin autenticación.

- Internet, la red pública global.
- Wi-Fi gratuito en cafeterías, bibliotecas o aeropuertos.
- Redes móviles 4G/5G accesibles sin credenciales especiales.

### 2.3.3 Redes híbridas
Combinan elementos de redes privadas y públicas. Algunas partes son accesibles para cualquier usuario, mientras que otras requieren autorización. Por ejemplo, una universidad que ofrece Wi-Fi público para estudiantes y visitantes, pero restringe el acceso a ciertos sistemas administrativos o bases de datos internas solo para empleados.

### 2.3.4 VPN (Virtual Private Network)
Una VPN no es una red en sí misma, sino una tecnología que crea un canal seguro para acceder a una red privada a través de Internet. Se usa para proteger datos y garantizar privacidad en conexiones remotas. La VPN crea un túnel seguro y cifrado entre el usuario y la red privada, evitando que terceros puedan interceptar la información.

Por ejemplo, un empleado que trabaja desde casa usa una VPN corporativa para conectarse a la red privada de su empresa y acceder a documentos internos como si estuviera en la oficina. También se usa para mejorar la privacidad en redes públicas, evitando que los proveedores de Internet o hackers puedan rastrear la actividad del usuario.

## 2.4 Ejercicios

**1. Preguntas de comprensión (respuesta breve)**
- ¿Qué diferencia principal hay entre una red LAN y una red WAN?
- Pon un ejemplo real de una red MAN y explica por qué se clasifica como tal.
- ¿Cuál es la diferencia entre Wi-Fi y Bluetooth? ¿En qué tipo de red se usa cada uno?
- ¿Por qué las redes públicas pueden ser menos seguras que las privadas?
- ¿Qué ventaja tiene una topología en estrella frente a una topología en bus?

**2. Verdadero o falso (justifica si es falso)**
- Las redes WAN solo se usan dentro de edificios pequeños.
- La red de una universidad que conecta varios campus es un ejemplo de red MAN.
- Una red PAN utiliza tecnologías de largo alcance como 4G o satélite.
- En una topología en malla, los datos solo pueden ir por un único camino.
- Las redes híbridas combinan características de redes públicas y privadas.

**3. Relaciona columnas**
Relaciona correctamente cada concepto con su descripción o ejemplo.

<table>
    <tr>
        <th>Concepto</th>
        <th>Descripción o ejemplo</th>
    </tr>
    <tr>
        <td>WiMax</td>
        <td>A. Comunicación inalámbrica de muy corto alcance</td>
    </tr>
    <tr>
        <td>VPN</td>
        <td>B. Canal seguro para acceder a una red privada</td>
    </tr>
    <tr>
        <td>NFC</td>
        <td>c: Tecnología usada en redes MAN (hasta 50km)</td>
    </tr>
    <tr>
        <td>LAN</td>
        <td>D. Red dentro de un edificio como una oficina</td>
    </tr>
    <tr>
        <td>Topología en anillo</td>
        <td>E. Dispositivos conectados en círculo</td>
    </tr>    
</table>


