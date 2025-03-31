# 5. Diseño lógico y segmentación de una red local

## 5.1 ¿Qué es el diseño lógico de una red?

El **diseño lógico de una red local (LAN)** es la **planificación de cómo se organizan los dispositivos y cómo se comunican entre ellos**, sin tener en cuenta los cables o aparatos físicos.

En otras palabras, es pensar **qué IP tendrá cada equipo, cómo se conectan a Internet y si se van a dividir en grupos** (subredes).

### 5.1.1 ¿Qué decisiones se toman en el diseño lógico?
Al diseñar una red, se deben planificar cosas como:
- Qué direcciones IP usarán los dispositivos
- Qué dispositivos habrá (ordenadores, impresoras, routers, etc.)
- Si todos estarán en la misma red o en subredes separadas
- Cómo saldrán a Internet (por qué puerta de enlace o router)
- Qué dispositivos deben comunicarse entre sí, y cuáles conviene mantener separados (por ejemplo: separar el tráfico del personal del tráfico del alumnado)

En este curso aprenderemos a hacer esa organización mediante segmentación, una forma sencilla y muy útil de dividir una red en partes más pequeñas.

### 5.1.2 Ejemplo simple de diseño lógico
Imagina que queremos conectar los dispositivos de una oficina:
- Red IP elegida: 192.168.10.0/24
- Router (salida a Internet): 192.168.10.1
- Impresora con IP fija: 192.168.10.10
- Servidor de archivos con IP fija: 192.168.10.20
- Ordenadores de los empleados: reciben IP automáticamente entre 192.168.10.100 y 192.168.10.200 (por DHCP)

Todos están en la misma red y pueden comunicarse entre sí.

### 5.1.3 Parámetros básicos que necesita cada dispostivo
Para que un dispositivo funcione bien en la red y tenga acceso a Internet, necesita:
- **Dirección IP:** identifica de forma única al dispositivo. Ej: 192.168.1.10
- **Máscara de red:** determina qué parte de la IP pertenece a la red y cuál al host. Ej: 255.255.255.0
- **Gateway:** dirección del router que da acceso al exterior (normalmente: 192.168.1.1)

### 5.1.4 Errores comunes en una red mal diseñada
- **IP duplicada:** dos dispositivos con la misma IP entran en conflicto → ninguno se conecta bien.
- **IP fuera del rango definido por la red y su máscara.:** el dispositivo no podrá hablar con los demás ni con el router.
- **Máscara incorrecta:** el equipo no sabrá quién está dentro de su red → no se comunica.
- **Falta de gateway:** el dispositivo no podrá salir a Internet.

## 5.2 Diseño básico de una red sin segmentación

Antes de aprender a dividir una red, es importante entender cómo se diseña una red sencilla, donde **todos los dispositivos están conectados en el mismo grupo o segmento**. Este tipo de red se utiliza habitualmente en hogares, aulas, pequeñas oficinas o laboratorios.

### 5.2.1 Elementos comunes en una red local simple
- **Router:** proporciona acceso a Internet y actúa como puerta de enlace (gateway).
- **Switch:** conecta los dispositivos entre sí (si la red es cableada).
- **Dispositivos finales:** ordenadores, impresoras, cámaras, etc.
- **Asignación IP:** puede hacerse manualmente o mediante DHCP.

### 5.2.2 Ejemplo: red de una biblioteca escolar
Supongamos que se necesita conectar:
- 1 router
- 1 impresora de red
- 6 ordenadores para usuarios
- 2 ordenadores para el personal

Se decide usar la red 192.168.10.0/24 (máscara: 255.255.255.0), sin segmentación, es decir, todos los dispositivos estarán en la misma red local.

**Asignación IP sugerida**
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

### 5.2.3 Limitaciones de este diseño sin segmentación**
- Todo el tráfico circula por la misma red, lo que puede hacerla más lenta.
- No hay separación entre usuarios y personal, lo que puede afectar la seguridad.
- Administrar muchos dispositivos se vuelve complicado.

Por eso, en redes medianas o grandes, es recomendable dividir la red en subredes, usando subnetting. 

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

Antes de comenzar, es importante entender algunos **conceptos clave**:
- Cuando dividimos una red, tomamos bits del campo de host para crear más subredes. A estos bits se les llama **"bits prestados"**. Cuantos más bits prestemos, más subredes podemos crear, pero menos dispositivos podrá tener cada subred.
- La **notación CIDR (/n)** indica cuántos bits están reservados para la parte de red. Por ejemplo, /24 significa que los primeros 24 bits de la IP pertenecen a la red, y el resto son para los hosts.
- Para **calcular subredes y hosts**, usamos estas fórmulas:
  - Nº de subredes = 2^n (donde n es el número de bits prestados)
  - Nº de hosts por subred = 2^h - 2 (donde h es la cantidad de bits que quedan para los hosts)

Una vez entendido esto, seguimos estos pasos:

**Paso 1: Determina cuántas subredes necesitas**
- Supongamos que queremos crear 4 subredes. 
- Usa la fórmula: Nº de subredes = 2^n,  para calcular cuántos bits necesito prestar (busca el valor de n que te permita alcanzar o superar la cantidad de subredes requeridas)
- 2² = 4 → necesitas 2 bits prestados del campo de host.

**Paso 2: Calcula el nuevo prefijo CIDR**
- Tu red original era /24. 
- Si prestas 2 bits: 24 + 2 = /26
- Esto significa que los primeros 26 bits ahora identifican la subred.

**Paso 3: Calcula cuántos hosts puedes tener por subred**
- Con /26, quedan 6 bits para hosts
- Nº de hosts = 2^6 - 2 = 62 hosts por subred
(Se restan 2: una IP para red y otra para broadcast)

**Paso 4: Divide la red en subredes**
- En /26, el bloque de IPs se mueve de 64 en 64 (porque 2⁶ = 64). 

Entonces las subredes serían:

<table>
    <tr>
        <th>Subred</th>        
        <th>Dirección de red</th>
        <th>Rango de IPs disponibles</th>
        <th>Broadcast</th>
    </tr>
    <tr>
        <td>1</td>
        <td>192.168.1.0</td>
        <td>192.168.1.1 - 192.168.1.62</td>        
        <td>192.168.1.63</td>
    </tr>
     <tr>
        <td>2</td>
        <td>192.168.1.64</td>
        <td>192.168.1.65 - 192.168.1.126</td>        
        <td>192.168.1.127</td>
    </tr>
     <tr>
        <td>3</td>
        <td>192.168.1.128</td>
        <td>192.168.1.129 - 192.168.1.190</td>        
        <td>192.168.1.191</td>
    </tr>
     <tr>
        <td>4</td>
        <td>192.168.1.192</td>
        <td>192.168.1.193 - 192.168.1.254</td>       
        <td>192.168.1.255</td>
    </tr>
</table>

Cada subred tiene 62 IPs útiles.

Como ves, el proceso de subnetting sigue una lógica clara: identificas cuántas subredes necesitas, prestas bits, y divides el espacio de direcciones de forma ordenada.

> **Ejercicio 1.** Tienes la red 192.168.10.0/24 y necesitas dividirla en 8 subredes iguales.
> - ¿Cuántos bits debes tomar prestados del campo de host?
> - ¿Cuál será el nuevo prefijo CIDR?
> - ¿Cuántas direcciones IP podrá tener cada subred?
> - Enumera las 8 subredes indicando:
>   - Dirección de red
>   - Rango de IPs disponibles para hosts
>   - Dirección de broadcast 

## 5.4 Subnetting con VLSM

Cuando usamos subnetting básico (como en el ejemplo anterior), dividimos la red en subredes del mismo tamaño. Esto a veces desperdicia direcciones IP, especialmente si algunos grupos necesitan pocas y otros muchas.

**VLSM (Variable Length Subnet Masking)** permite usar **subredes de distintos tamaños**, adaptadas a lo que necesita cada grupo.

<table>
    <tr>
        <th>Subnetting clásico (fijo)</th>
        <th>VLSM (máscara variable)</th>
    </tr>
    <tr>
        <td>Todas las subredes tienen el mismo tamaño</td>
        <td>Cada subred puede tener el tamaño que necesite</td>
    </tr>
    <tr>
        <td>Fácil de calcular</td>
        <td>Requiere más planificación</td>
    </tr>
    <tr>
        <td>Puede desperdiciar IPs</td>
        <td>Ahorra espacio de direcciones</td>
    </tr>
    <tr>
        <td>Buena para redes simples</td>
        <td>Ideal para redes organizadas por grupos</td>
    </tr>
</table>

### 5.4.1 Ejemplo con VLSM

Supongamos que tienes la red 192.168.1.0/24 y necesitas asignar subredes a los siguientes grupos:
- Departamento A: 100 dispositivos
- Departamento B: 50 dispositivos
- Departamento C: 20 dispositivos
- Departamento D: 10 dispositivos

**Paso 1: Ordenar de mayor a menor**
Se empieza por el grupo más grande para no solaparse.

**Paso 2: Calcula la máscara necesaria para cada grupo**
Usa la fórmula: Nº de hosts útiles = 2^h - 2 (h = bits disponibles para hosts)

Completa esta tabla:

<table>
    <tr>
        <th>Departamento</th>
        <th>Necesita</th>
        <th>Máscara (CIDR)</th>
        <th>Nº IP útiles</th>
        <th>Rango asignado</th>
    </tr>
    <tr>
        <td>A</td>
        <td>100</td>
        <td>/25</td>
        <td>126</td>
        <td>192.168.1.0 - 192.168.1.127</td>
    </tr>
    <tr>
        <td>B</td>
        <td>50</td>
        <td>/26</td>
        <td>62</td>
        <td>192.168.1.128 - 192.168.1.191</td>
    </tr>
    <tr>
        <td>C</td>
        <td>20</td>
        <td>/27</td>
        <td>30</td>
        <td>192.168.1.192 - 192.168.1.223</td>
    </tr>
    <tr>
        <td>D</td>
        <td>10</td>
        <td>/28</td>
        <td>14</td>
        <td>192.168.1.224 - 192.168.1.239</td>
    </tr>
</table>

Aún sobran direcciones en el bloque 192.168.1.240 - 192.168.1.255 para futuras ampliaciones.

