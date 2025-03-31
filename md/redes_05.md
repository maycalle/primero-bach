# 5. Diseño lógico y segmentación de una red local

## 5.1 ¿Qué es el diseño lógico de una red?

El **diseño lógico de una red local (LAN)** es la **planificación de cómo se organizan los dispositivos y cómo se comunican entre ellos**, sin fijarnos en los cables o conexiones físicas..

En otras palabras, es decidir  **qué direcciones IP usará cada equipo, cómo saldrán a Internet y si la red se dividirá en grupos más pequeños** (subredes).

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
- **Gateway:** dirección del router que da acceso al exterior (Ej: 192.168.1.1)

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

### 5.2.3 Limitaciones de no segmentar**
- Todo el tráfico circula por la misma red, lo que puede hacerla más lenta.
- No hay separación entre usuarios y personal, lo que puede afectar la seguridad.
- Administrar muchos dispositivos se vuelve complicado.

Por eso, en redes medianas o grandes, es recomendable dividir la red en subredes, usando subnetting. 

## 5.3 Diseño de redes con subredes (subnetting)

### 5.3.1 ¿Qué es el subnetting?

El **subnetting** es una técnica que permite dividir una red grande en varias redes más pequeñas, llamadas subredes. Cada subred funciona de forma independiente dentro de la red general.

#### ¿Por qué dividir una red?
- **Rendimiento:** menos tráfico por subred.
- **Seguridad:** se pueden aislar departamentos.
- **Organización:** se gestionan mejor las IPs.
- **Eficiencia:** se asignan solo las IPs necesarias a cada subred.

### 5.3.2 ¿Cómo se hace el subnetting?
Partimos de una red inicial (por ejemplo, 192.168.1.0/24) y la queremos dividir en partes más pequeñas.

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

> **Ejercicio 2.** La red base asignada a un campus educativo es 172.16.0.0/16. El campus tiene varios edificios y quiere crear 16 subredes iguales, una para cada área del centro. Divide la red usando subnetting clásico.


## 5.4 Subnetting con VLSM (máscara variable)

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

Supongamos que tienes la red 192.168.1.0/24 (esto nos da 256 direcciones totales, de las cuales 254 son utilizables), y necesitas asignar subredes a los siguientes grupos:
- Departamento A: 50 dispositivos
- Departamento B: 100 dispositivos
- Departamento C: 10 dispositivos
- Departamento D: 20 dispositivos

**Paso 1: Ordenar de mayor a menor**
Esto es importante porque las subredes más grandes necesitan más espacio, así que hay que asignarlas primero para no quedarse sin sitio.
1. Departamento B
2. Departamento A
3. Departamento D
4. Departamento C

**Paso 2: Calcular el tamaño de cada subred**
- Usa la fórmula: Nº de hosts útiles = 2^h - 2 (h = bits disponibles para hosts)
- Busca la mínima potencia de 2 que cubra cada grupo:

<table>
    <tr>
        <th>Departamento</th>
        <th>Necesita</th>
        <th>Potencia de 2 más próxima</th>
        <th>Nº IPs útiles</th>
        <th>CIDR</th>
    </tr>
    <tr>
        <td>B</td>
        <td>100</td>
        <td>128 → 2⁷</td>
        <td>126</td>
        <td>/25</td>
    </tr>
    <tr>
        <td>A</td>
        <td>50</td>
        <td>64 → 2⁶</td>
        <td>62</td>
        <td>/26</td>
    </tr>
    <tr>
        <td>D</td>
        <td>20</td>
        <td>32 → 2⁵</td>
        <td>30</td>
        <td>/27</td>
    </tr>
    <tr>
        <td>C</td>
        <td>10</td>
        <td>16 → 2⁴</td>
        <td>14</td>
        <td>/28</td>
    </tr>
</table>

**Paso 3: Asignar rangos sin solapamiento**
Ahora asignamos las subredes empezando desde 192.168.1.0, respetando el tamaño necesario de cada una:

<table>
    <tr>
        <th>Departamento</th>
        <th>CIDR</th>
        <th>Dirección de red</th>
        <th>Primer host</th>
        <th>Último host</th>
        <th>Broadcast</th>
    </tr>
    <tr>
        <td>B</td>
        <td>/25</td>
        <td>192.168.1.0</td>
        <td>192.168.1.1</td>
        <td>192.168.1.126</td>
        <td>192.168.1.127</td>
    </tr>
    <tr>
        <td>A</td>
        <td>/26</td>
        <td>192.168.1.128</td>
        <td>192.168.1.129</td>
        <td>192.168.1.190</td>
        <td>192.168.1.191</td>
    </tr>
    <tr>
        <td>D</td>
        <td>/27</td>
        <td>192.168.1.192</td>
        <td>192.168.1.193</td>
        <td>192.168.1.222</td>
        <td>192.168.1.223</td>
    </tr>
    <tr>
        <td>C</td>
        <td>/28</td>
        <td>192.168.1.224</td>
        <td>192.168.1.225</td>
        <td>192.168.1.238</td>
        <td>192.168.1.239</td>
    </tr>
</table>

Al final aún sobran direcciones:
192.168.1.240 - 192.168.1.255 → disponibles para futuro uso.

> **Ejercicio 3.**  Dispones de la red 192.168.10.0/24. Necesitas dividirla en subredes para los siguientes grupos utilizando VLSM:
> - Departamento de Administración: 30 dispositivos 
> - Sala de profesores: 14 dispositivos 
> - Conserjería: 6 dispositivos
> *Intrucciones:* 
> - Ordena los grupos de mayor a menor según el número de dispositivos.
> - Calcula cuántas IPs necesita cada grupo y el prefijo CIDR adecuado.
> - Asigna a cada grupo: dirección de red, primer y último host y dirección de broadcast.
> Asegúrate de que no hay solapamientos y de que todas las IPs encajan dentro del bloque 192.168.10.0/24.
> Recuerda usar potencias de 2 y la fórmula 2^h - 2.

> **Ejercicio 4.** Dispones de la red 10.0.0.0/24. Debes segmentarla para los siguientes servicios de un instituto utilizando VLSM:
> - Aulas de informática: 60 ordenadores
> - Administración: 25 ordenadores
> - Laboratorio de ciencias: 12 ordenadores
> - Dirección: 6 ordenadores
> - Red de invitados: 4 ordenadores

