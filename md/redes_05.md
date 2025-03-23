# 5. Diseño y estructura lógica de una red local

## 5.1 ¿Qué es diseñar una red local (LAN)?

Diseñar una red local (LAN) consiste en organizar y configurar los dispositivos para que puedan comunicarse entre sí y, normalmente, acceder a Internet. Esto incluye:
- **Elegir los dispositivos:** ordenadores, impresoras, router, switch, etc.
- **Determinar el tipo de conexión:** por cable (Ethernet) o inalámbrica (WiFi).
- **Asignar direcciones IP** para que cada dispositivo tenga una “identidad” dentro de la red.
- **Establecer reglas** de comunicación y salida a Internet.

Cuando conectamos un dispositivo a una red, necesita tres datos básicos para poder funcionar correctamente:
- **Dirección IP:** es un número único que identifica a cada dispositivo dentro de la red. Ejemplo de dirección IP: 192.168.1.25
- **Máscara de red:** indica cuántos bits de la dirección IP pertenecen a la parte de red y cuántos a la parte del dispositivo (host).
Esto nos permite saber qué dispositivos están en la misma red. Ejemplo: 255.255.255.0 → significa que los tres primeros números (192.168.1) son la red, y el último (.25) es el número del dispositivo.
- **Gateway o puerta de enlace:** es la salida de la red local hacia otras redes, como Internet, normalmente es la dirección IP del router. Ejemplo: 192.168.1.1 suele ser el router que da acceso a Internet.

#### ¿Qué pasa si hay errores?
- Si dos dispositivos tienen la misma IP, la red dará error (conflicto de IP).
- Si la IP no está en la misma red que el router, no habrá conexión a Internet.
- Si no se pone bien la máscara o el gateway, el equipo no podrá comunicarse con otros.


## 5.2 Dirección IP + máscara + gateway en la práctica
Ejemplos simples de configuración manual

## 5.3 Dirección de red y broadcast (con ejercicios)

## 5.4 Diseño básico de una red sin segmentación
Asignación IP manual
Diagrama de red sencilla

## 5.5 Diseño de redes con subredes
Segmentación por áreas funcionales
Ejemplos con tablas

## 5.6 Introducción a VLANs

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



