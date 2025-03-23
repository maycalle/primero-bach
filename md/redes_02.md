# 2. Tipos de redes

Vivimos en un mundo hiperconectado. Móviles, ordenadores, tablets, smartwatches… Todos estos dispositivos pueden comunicarse entre sí gracias a las redes informáticas. Pero no todas las redes son iguales: hay distintos tipos según el espacio que abarcan, cómo están organizadas o quién puede acceder a ellas.

## 2.1 Según su área de cobertura

Este criterio clasifica las redes según la distancia que abarcan y el tamaño del área en la que operan. No es lo mismo conectar dos dispositivos en una habitación que unir miles en distintos países.
 
### 2.1.1 WAN (Wide Area Network, Red de Área Extensa) 
- Las **redes WAN** son las más grandes que existen. Sirven para conectar dispositivos que están **muy alejados geográficamente**, incluso en **países o continentes distintos**. Su principal objetivo es permitir la comunicación a gran escala.
- Para lograr estas conexiones enormes, se utilizan diferentes tecnologías:
    - **Cables submarinos de fibra óptica**, ruzan océanos y mares llevando datos de un continente a otro.     
    - **Redes móviles 4G y 5G**, muy comunes en ciudades y pueblos. Permiten velocidades de hasta 10 Gbps.
    - **Satélites de comunicaciones**, para zonas remotas o de difícil acceso donde el cableado no es viable.    
- Internet es la red WAN más conocida y utilizada. Gracias a ella, millones de personas pueden navegar, enviar mensajes o hacer videollamadas desde cualquier rincón del mundo.

***Curiosidad tecnológica:*** Actualmente hay más de 500 cables que cruzan océanos y mares conectando países. Si quieres ver cómo es esa red invisible que sostiene Internet, puedes visitar esta web interactiva: 👉 https://www.submarinecablemap.com/. Ahí puedes explorar un mapa en tiempo real de todos los cables submarinos activos, en construcción o planificados. Por ejemplo, el cable “Marea”, que conecta España (Bilbao) con Estados Unidos (Virginia), tiene una capacidad de 160 terabits por segundo. Fue financiado por empresas como Microsoft y Facebook y recorre más de 6.600 kilómetros por el fondo del océano Atlántico.

### 2.1.2 MAN (Metropolitan Area Network, Red de Área Metropolitana)
- Las **redes MAN** conectan **varios edificios dentro de una misma ciudad**. Son más grandes que una red LAN, pero más pequeña que una WAN.
- Las tecnologías que usan son las siguientes: 
    - **Fibra óptica**, que permite enviar grandes cantidades de datos a alta velocidad.
    - **WiMAX**, una tecnología inalámbrica capaz de cubrir hasta 50 km sin necesidad de cables.     
- Se utiliza, por ejemplo, para unir diferentes edificios de una empresa, hospitales, bibliotecas, ayuntamientos o facultades universitarias que están en distintas partes de una ciudad.

***Curiosidad tecnológica***: Barcelona es una de las ciudades más avanzadas en el uso de tecnologías para gestionar servicios urbanos de forma eficiente y sostenible. Entre sus iniciativas destacan: contenedores inteligentes (avisan cuando están llenos), farolas adaptativas (ajustan su luz según la presencia de personas), riego automático (según la humedad del suelo), aparcamiento inteligente (con sensores que muestran plazas libres en una app). Todo esto funciona gracias a una infraestructura de red urbana que combina **redes MAN** con otras redes inalámbricas para dispositivos IoT, como **LoRa** o **NB-IoT**.

### 2.1.3 LAN (Local Area Network, Red de Área Local)
- Las **redes LAN** se utilizan para conectar dispositivos dentro de un **espacio pequeño, como una casa, un aula, una oficina o un laboratorio**. Son las redes más comunes en el día a día. Permiten compartir archivos, impresoras, conexión a Internet o jugar en red local con gran velocidad y poco retraso.
- Las tecnologías más habituales son:
    - **Ethernet (cable)**, conexión por cable de par trenzado o fibra óptica. Es estable y muy rápida.
    - **Wi-Fi (inalámbrica)** permite conectar dispositivos sin cables. Hoy se usan estándares como **Wi-Fi 6**, y pronto llegará **Wi-Fi 7**, aún más rápido y eficiente.
    - **PLC**, tecnología que permite enviar datos a través del cableado eléctrico de casa o del edificio.
- La red de un instituto donde los ordenadores de las aulas están conectados al mismo router por Ethernet o Wi-Fi es una LAN. También lo es la red doméstica de una casa con varios móviles, ordenadores y una Smart TV conectados al mismo Wi-Fi.

### 2.1.4 PAN (Personal Area Network, Red de Área Personal)
- Una **red PAN** conecta dispositivos personales que están **muy cerca unos de otros**, normalmente a menos de 10 metros de distancia. Aunque pueden ser cableadas, lo habitual es que sean inalámbricas. 
- Se basan en tecnologías inalámbricas de corto alcance:
    - **Bluetooth** muy común en móviles, portátiles, relojes inteligentes, altavoces, teclados, ratones, etc. Funciona sin cables y permite la transferencia de datos a corta distancia (hasta 10 metros, en condiciones normales).. 
    - **NFC (*Near Field Communication*)** funciona a una distancia aún más corta (menos de 4 cm), pero es extremadamente rápida. Se usa para pagar con el móvil, acceder a edificios con tarjetas sin contacto o compartir archivos entre teléfonos con solo acercarlos.     
- Tu smartphone conectado por Bluetooth a unos auriculares o a una pulsera de actividad es una red PAN. También cuando usas el móvil para pagar en una tienda mediante NFC estás usando una red PAN.

***Curiosidad tecnológica***: ¿Sabías que el nombre *“Bluetooth”* viene del rey Harald "Blåtand" Gormsson de Dinamarca, que en el siglo X unificó varias tribus escandinavas?
Los creadores de la tecnología eligieron ese nombre porque Bluetooth une diferentes dispositivos, igual que aquel rey unió pueblos. De hecho, el logotipo de Bluetooth combina dos runas nórdicas que representan sus iniciales: H y B. 

<div align="center">
    <img src="/primero-bach/img/tipos_redes_extension.png" width="60%">
</div>

Cuando estas redes utilizan conexiones inalámbricas, se antepone la letra W (Wireless) al nombre de la red. Por ejemplo:
- **WWAN ( Wireless WAN):** es una red de área extensa sin cables. Usa tecnologías móviles como 4G o 5G para ofrecer conexión a Internet en grandes zonas, incluso en movimiento.Por ejemplo, cuando te conectas a Internet desde el móvil usando datos, estás usando una WWAN. 
- **WLAN (Wireless LAN):** es una red de área local inalámbrica. Lo que normalmente llamamos Wi-Fi en casa, en clase o en una cafetería.

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

La topología de red describe la forma física o lógica en la que se conectan los dispositivos entre sí. Es como el plano o el esquema de la red.

### 2.2.1 Topologia en bus
- Todos los dispositivos están conectados a un **único cable central (llamado “bus” o “troncal”)**, por donde circulan todos los datos en ambas direcciones.
- **Ventajas:**
    - Es económica y fácil de instalar.
- **Inconvenientes:** 
    - Si el cable principal se rompe, toda la red deja de funcionar.
    - Cuantos más dispositivos se conectan, más lenta se vuelve por la congestión.
- **Ejemplo:** redes antiguas en escuelas u oficinas que usaban cable coaxial. Hoy casi no se utiliza.

### 2.2.2 Topología en estrella
- Todos los dispositivos están conectados a un nodo central (como un switch o un router). Ese nodo dirige todo el tráfico de datos.
- **Ventajas:** 
    - Si un dispositivo falla, la red sigue funcionando con normalidad.
    - Fácil de gestionar.
- **Inconvenientes:**
    - Si el nodo central falla, la red completa deja de operar.
- **Ejemplo:** la mayoría de redes domésticas: todos los móviles, portátiles y consolas se conectan al router Wi-Fi.

### 2.2.3 Topología en anillo
- En esta topología, los dispositivos están conectados formando un círculo cerrado. Cada uno se comunica con el siguiente, y los datos viajan de nodo en nodo hasta llegar a su destino. El envío puede ser en una sola dirección (anillo simple) o en ambas (anillo doble).
- **Ventajas:**
    - No necesita un nodo central, por lo que no depende de un único punto de fallo, como en la topología en estrella.     
    - El tráfico de datos es ordenado y predecible, lo que puede mejorar la eficiencia en redes pequeñas.
- **Inconvenientes:**
    - Si un solo dispositivo o conexión falla, toda la red puede quedar inutilizada.
    - En redes grandes, puede ser más lenta, ya que los datos deben pasar por muchos nodos hasta llegar al destino.
    - La instalación y el mantenimiento pueden ser más complejos que en otras topologías.
- **Ejemplo:** algunas antiguas redes de fibra óptica o estaciones de trabajo especializadas. Hoy en día están casi en desuso, pero se siguen estudiando por su valor histórico y conceptual.

### 2.2.4 Topología en malla
En una topología en malla, cada dispositivo está conectado a varios otros dispositivos dentro de la red. Esto crea múltiples caminos posibles para enviar los datos. No hay una única ruta: los datos pueden circular por diferentes caminos, lo que hace que la red sea muy resistente y eficiente.
- **Ventajas:**
    - Es muy fiable porque si una conexión falla, los datos pueden tomar otra ruta.
    - Ofrece alta velocidad y buen rendimiento, ya que el tráfico se reparte por distintos caminos.
    - Ideal para entornos donde la disponibilidad constante es fundamental.
- **Inconvenientes:**
    - Es costosa y compleja de implementar por la cantidad de cables y conexiones necesarias.
    - Necesita una gestión más avanzada.
- **Ejemplo:** la estructura de Internet se basa en una malla parcial, donde los servidores y routers de todo el mundo están interconectados por múltiples rutas. Así, si una parte de la red falla (por ejemplo, un cable submarino), los datos pueden redirigirse automáticamente por otro camino.

### 2.2.5 Topología híbrida
La topología híbrida combina dos o más topologías diferentes (como estrella, bus, anillo o malla) dentro de una misma red. Se diseña así para adaptarse mejor a las necesidades reales de una organización o sistema. 
- **Ventajas:**
    - Es muy flexible y escalable: se adapta fácilmente al crecimiento o a nuevas necesidades.
    - Permite aprovechar lo mejor de cada topología según el caso.
    - Ideal para redes grandes o complejas, como las de empresas, universidades o instituciones públicas.
- **Inconvenientes:**
    - Puede ser más costosa y compleja de diseñar, configurar y mantener.
    - Requiere una planificación cuidadosa para que todos los componentes se integren correctamente.
- **Ejemplo:** en una empresa grande, cada departamento puede tener una red en estrella (con todos los dispositivos conectados a un switch), y luego todos los departamentos están conectados entre sí mediante una red en malla o en bus, formando una topología híbrida.

<div align="center">
    <img src="/primero-bach/img/topologias-de-red-1.jpg" width="80%">
</div>

Cada topología tiene sus ventajas y desventajas, y la elección depende del costo, rendimiento y seguridad que se necesite. En la actualidad, las más utilizadas son estrella y malla, debido a su eficiencia y estabilidad.

## 2.3 Según su nivel de acceso o privacidad

Las redes no solo se diferencian por su tamaño o forma, sino también por quién puede acceder a ellas. Algunas redes están cerradas y protegidas, mientras que otras son abiertas para cualquiera. También existen redes mixtas, que combinan zonas públicas y privadas. Y por último, tenemos las VPN, una herramienta que ayuda a conectarse a redes privadas de forma segura desde cualquier lugar.

### 2.3.1 Redes privadas
Son redes cerradas y seguras, donde solo los usuarios autorizados pueden acceder y utilizar sus servicios. Se usan en empresas, hospitales, instituciones y organizaciones para garantizar privacidad y control. Por ejemplo, la red interna de una empresa a la que solo pueden acceder empleados desde sus oficinas.

Si esta red privada incluye servicios como correo, páginas web internas o almacenamiento solo accesible desde dentro, se llama **Intranet**.

### 2.3.2 Redes públicas
Son abiertas a cualquier usuario, permitiendo la comunicación y el intercambio de información sin restricciones de acceso. Son muy prácticas, pero hay que tener cuidado: como están abiertas a todos, también son más vulnerables a ataques, virus o robo de datos.

Ejemplos: 
- Internet, en general, es la mayor red pública del mundo.
- Wi-Fi gratuito en cafeterías, bibliotecas o aeropuertos.
- Redes móviles 4G/5G accesibles sin credenciales especiales.

📌 **Consejo:** nunca envíes información personal o sensible desde una red pública sin protección adicional.

### 2.3.3 Redes híbridas
Son redes que combinan partes públicas y privadas. Algunas zonas están abiertas a todos, y otras están protegidas y requieren usuario y contraseña. Por ejemplo, una universidad que ofrece Wi-Fi público para estudiantes y visitantes, pero restringe el acceso a ciertos sistemas administrativos o bases de datos internas solo para empleados.

### 2.3.4 VPN (Virtual Private Network)
Una VPN no es una red en sí misma, sino una tecnología que crea un canal seguro para acceder a una red privada a través de Internet. Se usa para proteger datos y garantizar privacidad en conexiones remotas. La VPN crea un túnel seguro y cifrado entre el usuario y la red privada, evitando que terceros puedan interceptar la información.

Por ejemplo, un empleado que trabaja desde casa usa una VPN corporativa para conectarse a la red privada de su empresa y acceder a documentos internos como si estuviera en la oficina. También se usa para navegar con mayor privacidad, ya que impide que otros (como hackers o tu propio proveedor de Internet) rastreen lo que haces online.

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


