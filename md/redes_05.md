# 5. Diseño y estructura lógica de una red local

## 5.1 ¿Qué es diseñar una red local (LAN)?

Diseñar una red local (LAN) consiste en planificar la estructura lógica y física de la red para que todos los dispositivos puedan comunicarse entre sí de forma eficiente, segura y, si es necesario, acceder a Internet.

#### Aspectos clave del diseño
- **Elección de dispositivos:** ordenadores, impresoras, router, switch, etc.
- **Tipo de conexión:** cableada (Ethernet), inalámbrica (WiFi), o mixta.
- **Asignación de direcciones IP:** cada dispositivo debe tener una dirección única en la red.
- **Salida a Internet:** configurar correctamente la puerta de enlace (gateway).
- **Segmentación lógica:** si es necesario, dividir la red en subredes por departamentos o zonas.

#### Parámetros básicos de configuración
Para que un dispositivo se conecte correctamente a la red y acceda a Internet, necesita estos tres parámetros:
- **Dirección IP:** identifica de forma única al dispositivo. Ej: 192.168.1.10
- **Máscara de red:** determina qué parte de la IP pertenece a la red y cuál al host. Ej: 255.255.255.0
- **Gateway:** dirección del router que da acceso al exterior (normalmente: 192.168.1.1)

#### ¿Qué puede salir mal?
- IP duplicada: dos dispositivos con la misma IP generan conflicto → sin conexión.
- IP fuera de la red: el dispositivo no podrá comunicarse con el resto ni con el router.
- Máscara incorrecta: no sabrá quién está en su red o fuera de ella.
- Falta de gateway: no tendrá acceso a Internet.


## 5.2 Diseño básico de una red sin segmentación

Antes de dividir una red en subredes, es importante entender cómo se diseña una red sencilla, con todos los dispositivos en el mismo segmento. Este tipo de red es común en hogares, aulas, pequeñas oficinas o laboratorios.

#### Elementos comunes
- **Router:** proporciona acceso a Internet y actúa como gateway.
- **Switch:** conecta los dispositivos entre sí (si la red es cableada).
- **Dispositivos finales:** ordenadores, impresoras, cámaras, etc.
- **Asignación IP:** manual o por DHCP.

#### Ejemplo: red de una biblioteca escolar
Supongamos que se necesita conectar:
- 1 router
- 1 impresora de red
- 6 ordenadores para usuarios
- 2 ordenadores para el personal

Se decide usar la red 192.168.10.0/24 (máscara: 255.255.255.0), sin segmentación, es decir, todos los dispositivos estarán en la misma red local.

Asignación IP sugerida
<table>
    <tr>
        <th>Dispositivo</th>
        <th>Dirección IP</th>
    </tr>
    <tr>
        <td>Router</td>
        <td>192.168.10.1</td>
    </tr>
    <tr>
        <td>Impresora</td>
        <td>192.168.10.10</td>
    </tr>
    <tr>
        <td>PC1 (usuario)</td>
        <td>192.168.10.20</td>
    </tr>
    <tr>
        <td>PC2 (usuario)</td>
        <td>192.168.10.21</td>
    </tr>
    <tr>
        <td>PC3 (usuario)</td>
        <td>192.168.10.22</td>
    </tr>
    <tr>
        <td>PC4 (usuario)</td>
        <td>192.168.10.23</td>
    </tr>
    <tr>
        <td>PC5 (usuario)</td>
        <td>192.168.10.24</td>
    </tr>
    <tr>
        <td>PC6 (usuario)</td>
        <td>192.168.10.25</td>
    </tr>
    <tr>
        <td>PC1 (personal)</td>
        <td>192.168.10.100</td>
    </tr>
    <tr>
        <td>PC2 (personal)</td>
        <td>192.168.10.101</td>
    </tr>
</table>

Todos los dispositivos usan:
- Máscara: 255.255.255.0
- Gateway: 192.168.10.1

Esto facilita la configuración, pero tiene limitaciones en redes grandes:
- Todo el tráfico se comparte, lo que ralentiza la red.
- No se puede aislar tráfico entre grupos (por seguridad o rendimiento).
- Se vuelve más difícil de administrar.

Por eso, para redes medianas o grandes, conviene dividir la red en subredes o usar VLANs.

## 5.3 Diseño de redes con subredes (subnetting)

### 5.3.1 ¿Qué es el subnetting?

El **subnetting** es una técnica que permite dividir una red grande en varias redes más pequeñas, llamadas subredes. Cada subred funciona de forma independiente dentro de la red general.

#### ¿Por qué dividir una red?
- Mejor rendimiento: se reduce la congestión.
- Mayor seguridad: se puede aislar tráfico entre áreas (por ejemplo, separar invitados del personal).
- Organización: facilita la administración de IPs.
- Aprovechamiento de IPs: se asigna solo lo necesario a cada grupo.

### 5.3.2 ¿Cómo se hace el subnetting?
Partimos de una red original (por ejemplo, 192.168.1.0/24) y la queremos dividir en partes más pequeñas.

**Conceptos clave:**
- **Bits prestados:** cuantos más bits tomemos del campo "host", más subredes tendremos, pero menos dispositivos cabrán en cada una.
- **CIDR (/n):** notación que indica cuántos bits están reservados para la parte de red. Por ejemplo, /24 significa que los primeros 24 bits de la IP pertenecen a la red.
- **Fórmulas útiles:**
    - Nº de subredes = 2^n (n: bits prestados)
    - Nº de hosts por subred = 2^h - 2 (h: bits de host)

### 5.3.3 Ejemplos 

#### Ejemplo 1: dividir una red en 2 subredes

Red: 192.168.1.0/24
Queremos: 2 subredes iguales
Solución: usar /25 → 25 bits para red, 7 bits para hosts.

<table>
    <tr>
        <th>Subred</th>
        <th>Dirección de red</th>
        <th>Rango de hosts</th>
        <th>Broadcast</th>
    </tr>
    <tr>
        <td>Subred 1</td>
        <td>192.168.1.0/25</td>
        <td>192.168.1.1 - 192.168.1.126</td>
        <td>192.168.1.127</td>
    </tr>
    <tr>
        <td>Subred 2</td>
        <td>192.168.1.128/25</td>
        <td>192.168.1.129 - 192.168.1.254</td>
        <td>192.168.1.255</td>
    </tr>
</table>

IMPORTANTE: no usar la primera (dirección de red) ni la última (broadcast) IP de cada subred.
Cada subred tiene 126 hosts disponibles (2^7 - 2)

#### Ejemplo 2: dividir 1 red en 4 subredes

Red: 192.168.1.0/24
Queremos: 4 subredes iguales
Solución: usar /26 → 26 bits para red, 6 bits para hosts. 

<table>
    <tr>
        <th>Subred</th>
        <th>Dirección de red</th>
        <th>Rango de hosts</th>
        <th>Broadcast</th>
    </tr>
    <tr>
        <td>Subred 1</td>
        <td>192.168.1.0/26</td>
        <td>192.168.1.1 - 192.168.1.62</td>
        <td>192.168.1.63</td>
    </tr>
    <tr>
        <td>Subred 2</td>
        <td>192.168.1.64/26</td>
        <td>192.168.1.65 - 192.168.1.126</td>
        <td>192.168.1.127</td>
    </tr>
    <tr>
        <td>Subred 3</td>
        <td>192.168.1.128/26</td>
        <td>192.168.1.129 - 192.168.1.190</td>
        <td>192.168.1.191</td>
    </tr>
    <tr>
        <td>Subred 4</td>
        <td>192.168.1.192/26</td>
        <td>192.168.1.193 - 192.168.1.254</td>
        <td>192.168.1.255</td>
    </tr>
</table>

IMPORTANTE: no usar la primera (dirección de red) ni la última (broadcast) IP de cada subred.
Cada subred tiene 64 hosts disponibles (2^6 - 2)

> **Ejercicio 1.** Divide la red 192.168.10.0/24 en 4 subredes y completa la tabla
> <table>
>    <tr>
>        <th>Subred</th>
>        <th>Dirección de red</th>
>        <th>Rango de hosts</th>
>        <th>Broadcast</th>
>    </tr>
>    <tr>
>        <td>Subred 1</td>
>        <td></td>
>        <td></td>
>        <td></td>
>    </tr>
>    <tr>
>        <td>Subred 2</td>
>        <td></td>
>        <td></td>
>        <td></td>
>    </tr>
>    <tr>
>        <td>Subred 3</td>
>        <td></td>
>        <td></td>
>        <td></td>
>    </tr>
>    <tr>
>        <td>Subred 4</td>
>        <td></td>
>        <td></td>
>        <td></td>
>    </tr>
> </table>

## 5.4 Segmentación lógica con VLANs

Hasta ahora hemos visto cómo dividir una red en subredes a nivel IP (usando el subnetting). Sin embargo, también se puede dividir lógicamente una red física usando una tecnología llamada VLAN (Virtual LAN).

#### ¿Qué es una VLAN?
Una VLAN es una red virtual que permite separar el tráfico de red dentro de una misma infraestructura física (por ejemplo, un switch o router). Es decir: “Varias redes independientes funcionando sobre el mismo cableado”.

#### ¿Por qué usar VLANs?
- Separar departamentos o grupos de trabajo (por ejemplo, profesorado ≠ alumnado).
- Mejorar la seguridad: solo los dispositivos de la misma VLAN pueden comunicarse entre sí.
- Optimizar el tráfico de red: evita que los datos innecesarios circulen por toda la red.
- Facilitar la administración: permite aplicar políticas por grupo, sin necesidad de nuevos cables.

#### Ejemplo: red de un instituto
Un instituto tiene una red física común (un switch central), pero quiere separar el tráfico de estos tres grupos:
Administración
Profesorado
Alumnado

Con VLANs, se pueden crear tres redes virtuales:
- VLAN 10: Administración
- VLAN 20: Profesorado
- VLAN 30: Alumnado

--- 

#### Ejemplo práctico: LAN sencilla con 4 equipos
Imagina que eres el encargado o encargada de configurar la red local de un aula de informática en tu instituto. En el aula hay:
- Un router que proporciona conexión a Internet.
- Tres ordenadores para el alumnado (PC1, PC2 y PC3).
- Una impresora compartida para que todos puedan imprimir.

Todos los dispositivos estarán conectados al router mediante cables de red.

Sabes que la red que se utilizará es la **192.168.1.0/24**, lo que significa que:
- Las direcciones IP válidas para los dispositivos van de 192.168.1.1 a 192.168.1.254.
- La máscara de red es 255.255.255.0.
- La dirección IP del router (puerta de enlace) será 192.168.1.1.

**TAREA:** asigna una dirección IP a cada uno de los siguientes dispositivos (PC1, PC2, PC3 e impresora), asegurándote de que:
- No se repitan direcciones IP.
- Todas estén dentro de la red 192.168.1.0/24.
- Todos los dispositivos puedan comunicarse entre sí y acceder a Internet.

Completa la siguiente tabla con la IP, la máscara de red y la puerta de enlace para cada dispositivo:

<table>
    <tr>
        <th>Dispositivo</th>
        <th>Dirección IP</th>
        <th>Máscara de red</th>
        <th>Puerta de enlace</th>
    </tr>
    <tr>
        <td>Router</td>
        <td>192.168.1.1</td>
        <td>255.255.255.0</td>
        <td>---</td>
    </tr>
    <tr>
        <td>PC1</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>PC2</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>PC3</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Impresora</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>    
</table>

Contesta a las siguientes preguntas:
- ¿Cuál es la dirección de red de esta LAN?
- ¿Cuál sería la dirección de broadcast?
- ¿Qué pasaría si dos dispositivos tuvieran la misma dirección IP?

### 3.2.2 Subredes y segmentación de redes.
Aunque todos los dispositivos puedan estar conectados entre sí, organizar la red en partes más pequeñas llamadas subredes permite:
- Mejorar el rendimiento.
- Aumentar la seguridad.
- Hacer más fácil la administración.
Esta división de una red en subredes es lo que llamamos **segmentación**.**

Cada subred tiene su propia dirección de red, y los dispositivos dentro de ella comparten el mismo prefijo IP (por ejemplo, 192.168.1.X).

### 3.2.3 Introducción a VLANs (Redes de Área Local Virtuales).

## 3.3 Protocolo de direccionamiento en redes
- Funcionamiento del direccionamiento IPv4 e IPv6.
- Subnetting: concepto y utilidad.
- DHCP: asignación dinámica de direcciones.


--- 
# Análisis y configuración de redes

## 4.1 Herramientas de análisis de redes

## 4.2 Configuración básica de una red en Packet Tracer



