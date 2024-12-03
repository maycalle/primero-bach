# 1. Primeros pasos con Pygame Zero

¡Bienvenidos a **Pygame Zero**! Si te gusta la idea de crear videojuegos 2D y ya sabes un poquito de Python, estás en el lugar correcto. Pygame Zero es una herramienta que te permitirá dar vida a tus ideas de videojuegos de forma muy sencilla y divertida. 

## 1.1 ¿Qué es Pygame Zero?

**Pygame Zero** es una versión simplificada de otra biblioteca más completa para crear juegos 2D, llamada **Pygame**. Está diseñada para que puedas empezar a programar videojuegos fácilmente y sin complicaciones. Al estar basada en Python, ¡te resultará muy familiar!

Una de las **ventajas de Pygame Zero** es que se ocupa automáticamente de aspectos técnicos, como configurar la ventana del juego o crear un bucle principal (el "motor" que mantiene el juego en marcha). Así, puedes concentrarte en lo más divertido: diseñar personajes, dibujar escenarios y añadir interacción en pantalla.

**¿Qué tipo de juegos puedes crear?**

Con Pygame Zero, puedes hacer un montón de juegos diferentes. Aquí tienes algunas ideas:
* **Juego de plataformas tipo Super Mario:** un personaje que salta, recoge monedas y esquiva enemigos.
* **Juego de disparos:** donde controlas una nave espacial que destruye enemigos mientras evita obstáculos.
* **Juego de carreras:** con coches que se mueven en una pista, acelerando y esquivando otros vehículos.
* **Puzzles** al estilo Tetris o juegos de combinar piezas.
* **Aventuras gráficas:** juegos donde puedes interactuar con objetos y personajes usando el ratón, como en clásicos de los 90.

## 1.2 ¿Cómo empezar?

Lo primero que necesitas es **instalar Pygame Zero**. Es muy fácil:
1. Abre la consola  (haz clic en el **menú de Inicio** y escribe **cmd**)
2. Escribe este comando:

```py
pip install pgzero
```

¡Y listo! Ya tienes Pygame Zero instalado.

> **NOTA:** El comando PIP permite instalar herramientas adicionales en Python. En este caso, para obtener Pygame Zero, pero lo puedes usar para instalar otras muchas herramientas (es como una *"tienda de aplicaciones"* para Python).

## 1.3 Sistema de coordenadas en PyGame Zero

Antes de empezar a ver la estructura básica de una aplicación de *Pygame Zero*, conviene entender cómo funciona su sistema de coordenadas, ya que es esencial para posicionar y mover elementos en la pantalla.

* **Origen:** el punto (0, 0) está en la esquina superior izquierda de la pantalla.
* **Eje X (horizontal):** aumenta de izquierda a derecha. Cuanto mayor sea el valor de x, más a la derecha estará el punto en la pantalla.
* **Eje Y (vertical):** aumenta de arriba hacia abajo, al contrario de los sistemas de coordenadas en matemáticas. Cuanto mayor sea el valor de y, más abajo estará el punto en la pantalla.
* **Tamaño de la ventana:** se define con `WIDTH` y `HEIGHT`. Por ejemplo, en una ventana de 800x600, el punto (800, 600) estaría en la esquina inferior derecha.
* **Centro de la pantalla:** se puede calcular con (`WIDTH` // 2, `HEIGHT` // 2).

Cualquier elemento en *Pygame Zero* (como texto, formas o imágenes) se posiciona según este sistema. Por ejemplo, (100, 50) colocaría un elemento a 100 píxeles de la izquierda y a 50 píxeles de la parte superior.

## 1.4 Estructura básica de un juego 

### 1.4.1 Dibujar un círculo la pantalla

Vamos a empezar con algo sencillo: **dibujar un círculo en la pantalla** de nuestro juego. Para ello, necesitas familiarizarte con dos elementos clave: la función `draw()` y el objeto `screen`.
    
* `draw()` es la función que dibuja todo lo que aparece en la pantalla (personajes, fondos, objetos, etc). No tienes que llamarla, Pygame Zero lo hace automáticamente cada vez que necesita actualizar el dibujo. 

* `screen` es como un *"lienzo"* donde dibujas todo. Cada vez que quieras mostrar algo, lo harás a través de este objeto y sus funciones asociadas (¡tiene muchas!). 

Para dibujar un círculo, usamos la función `screen.draw.circle()`, que acepta las coordenadas (x, y), el tamaño (radio) y el color del círculo. Aquí tienes un ejemplo:      

```py
# Importa la librería
import pgzrun

# Define el tamaño de la ventana del juego
WIDTH = 800
HEIGHT = 600

def draw():
    screen.clear()  # Limpia la pantalla
    screen.draw.circle((400, 300), 30, 'white')  # Dibuja un círculo blanco

pgzrun.go()  # Inicia el juego
```

> **Ejercicio 1.**
> * Cambia el color del círculo y observa el resultado.
> * Modifica las coordenadas (x, y) para mover el círculo a otra posición en la pantalla.
> * Prueba con diferentes radios para ver cómo afecta el tamaño.

### 1.4.2 Dibujar otras formas y texto

Una vez que domines los círculos, puedes experimentar con otras formas y texto. Aquí tienes algunos comandos adicionales que puedes probar:

* `screen.fill(color)`: llena la pantalla con un color sólido.
* `screen.draw.filled_circle((x, y), radio, color)`: dibuja un círculo relleno.
* `screen.draw.line((x1, y1), (x2, y2), color)`: dibuja una línea entre dos puntos.
* `screen.draw.rect(Rect((x, y), (ancho, alto)), color)`: dibuja un rectángulo con las dimensiones especificadas por (ancho, alto) en la posición (x, y).
* `screen.draw.text("Texto", (x, y), color='white', fontsize=40)`: escribe texto en la pantalla con el formato que le indiques: *fontsize* (tamaño del texto), *color* (color del texto), *shadow* (coordenada de desplazamiento del sombreado) y *scolor* para especificar el color de la sombra.

Prueba el siguiente ejemplo, observa el resultado y dónde se colocan las formas: 

```py
# Importa la librería
import pgzrun

# Define el tamaño de la ventana del juego
WIDTH = 800
HEIGHT = 600

def draw():
    screen.clear()  # Limpia la pantalla
    screen.fill('skyblue')  # Pinta el fondo de azul cielo

    # Dibuja un rectángulo
    screen.draw.filled_rect(Rect((150, 200), (500, 50)), 'green')

    # Dibuja un círculo
    screen.draw.filled_circle((400, 300), 50, 'orange')

    # Dibuja líneas de un extremo al otro
    screen.draw.line((0, 0), (WIDTH, HEIGHT), 'red')
    screen.draw.line((0, HEIGHT), (WIDTH, 0), 'purple')

    # Dibuja texto en la pantalla
    screen.draw.text('¡Bienvenidos a Pygame Zero!', (150, 100), color='white', fontsize=50, shadow=(2,2), scolor="#202020")
    screen.draw.text('Experimenta dibujando formas', (200, 450), color='yellow', fontsize=30)

pgzrun.go() # Inicia el juego
```

> **Ejercicio 2.**
> * Cambia los colores y posiciones de cada forma.
> * Dibuja dos rectángulos y cambia su tamaño.
> * Dibuja una línea roja y un círculo amarillo.
> * Dibuja un texto en la parte superior.
> * Añade texto en diferentes ubicaciones de la pantalla. 

### 1.4.3 Mostrar una imagen

Para mostrar una imagen, guárdala primero en una carpeta especial llamada **images**, ubicada en el mismo directorio que tu archivo de código.

* El nombre del archivo debe estar en minúsculas y sin espacios. Si tiene varias palabras, usa guiones bajos (por ejemplo, mi_imagen.png).

* Para mostrar la imagen en pantalla, usa: `screen.blit('nombre_imagen', (x, y))`.

Descarga [esta imagen](img/mapache_genial.png) y prueba este ejemplo:

```py
import pgzrun

# Definir el tamaño de la ventana del juego
WIDTH = 800
HEIGHT = 600

def draw():
    screen.clear()  # Limpiar la pantalla
    screen.fill('lightblue')  # Fondo color azul claro

    # Mostrar la imagen divertida
    screen.blit('mapache_genial.png', (220, 200))

    # Texto para acompañar la imagen
    screen.draw.text("¡Mira esta imagen divertida!", (200, 100), color='black', fontsize=40)

pgzrun.go() # Inicia el juego
```

> **Ejercicio 3.**  
> * Limpia la pantalla.
> * Rellena la pantalla con un color de fondo.
> * Carga una imagen en una posición específica

### 1.4.4 Agregando movimiento

Ahora que ya sabes dibujar y mostrar imágenes, vamos a incorporar el movimiento. Para ello, utilizaremos la función `update()`, que se ejecuta constantemente. Aquí colocaremos la lógica que controla el comportamiento del juego, como mover personajes, detectar colisiones, o cambiar el estado del juego.

**Ejemplo: moviendo el círculo**

Vamos a modificar el código para que el círculo se mueva hacia la derecha.

```py
# Importa la librería
import pgzrun

# Define el tamaño de la ventana del juego
WIDTH = 800
HEIGHT = 600

# Define la posición inicial del círculo
circle_x = 400
circle_y = 300

def draw():
    screen.clear()  # Limpia la pantalla
    screen.draw.circle((circle_x, circle_y), 30, 'white')  # Dibuja el círculo 

def update():
    global circle_x
    circle_x += 2  # Mueve el círculo 2 píxeles hacia la derecha en cada actualización

pgzrun.go()  # Inicia el juego
```

¡Nuestro círculo ya se está moviendo por la pantalla! Te explico algunos detalles: 

* **Coordenadas iniciales:** las variables `circle_x` y `circle_y` definen las coordenadas iniciales del círculo, colocándolo en el centro de la pantalla.
* **Función `draw()`:** dibuja el círculo en la posición definida en las coordenadas `circle_x` y `circle_y`. 
* **Función `update()`:** incrementa `circle_x` en 2 píxeles cada vez que se ejecuta, moviendo el círculo hacia la derecha.
* **Uso de global:** utilizamos `global circle_x` en `update()` para modificar `circle_x` dentro de la función.

Pygame Zero llama automáticamente a `draw()` y `update()` muchas veces por segundo para mantener el círculo actualizado en pantalla.

**Ejemplo: mapache en movimiento**

Ahora que tenemos un círculo en movimiento, vamos a darle vida a una imagen de una mapache para que se desplace de lado a lado en la pantalla. En este ejemplo, la imagen se moverá hacia la derecha, y cuando llegue al borde derecho, reaparecerá por el borde izquierdo, creando un efecto de desplazamiento continuo.

```py
import pgzrun

# Define el tamaño de la ventana del juego
WIDTH = 800
HEIGHT = 600

# Define la posición inicial de la imagen
mapache_x = 100
mapache_y = 300

def draw():
    screen.clear()  # Limpia la pantalla
    screen.blit('mapache_genial', (mapache_x, mapache_y))  # Dibuja la imagen 

def update():
    global mapache_x
    mapache_x += 2  # Mueve la imagen 2 píxeles hacia la derecha en cada actualización

    # Si el mapache sale de la pantalla, vuelve hacia a la izquierda
    if mapache_x > WIDTH:
        mapache_x = -100  # Hace que reaparezca desde el lado izquierdo

pgzrun.go()  # Iniciar el juego
```

En este código, hemos logrado que el mapache salga de la pantalla por la derecha y aparezca por la izquierda. Pero, ¿qué pasa si queremos que se mueva de arriba hacia abajo y cambie de dirección al alcanzar el borde creando un efecto de "rebote"?

**Ejemplo: movimiento vertical con control de bordes**

En este ejemplo, animaremos una imagen de un mapache para que suba y baje dentro de los límites de la pantalla. Cuando alcance el borde superior o inferior, cambiará de dirección automáticamente.

Agregaremos una variable `velocidad_y` para representar la dirección y velocidad vertical. Cuando el mapache llegue al borde superior o inferior, invertiremos el valor de `velocidad_y`, logrando que rebote.

```py
# Importa las librerías necesarias
import pgzrun
import os

# Centra la ventana del juego en la pantalla
os.environ['SDL_VIDEO_CENTERED'] = '1'

# Define el tamaño de la ventana del juego
WIDTH = 800
HEIGHT = 600

# Carga la imagen y calcula su tamaño
mapache_image = images.load('mapache_genial.png')
mapache_ancho = mapache_image.get_width()
mapache_alto = mapache_image.get_height()

# Define la posición inicial de la imagen
mapache_x = 0
mapache_y = 0
mapache_velocidad_y = 2  # Velocidad de movimiento vertical

def draw():
    screen.clear()  # Limpia la pantalla
    screen.blit('mapache_genial.png', (mapache_x, mapache_y))  # Dibuja la imagen 

def update():
    global mapache_y, mapache_velocidad_y

    # Mueve la imagen en el eje Y 
    mapache_y += mapache_velocidad_y

    # Si el mapache alcanza los límites superior o inferior, invierte su dirección
    if mapache_y <= 0 or mapache_y >= HEIGHT - mapache_alto:  # Ajuste según el tamaño de la imagen
        mapache_velocidad_y = -mapache_velocidad_y  # Cambia la dirección vertical

pgzrun.go()  # Iniciar el juego
```

* **Cargar la imagen:** la imagen del mapache se carga con `images.load('mapache_genial.png')`, y luego usamos `get_width()` y `get_height()` para obtener sus dimensiones (mapache_ancho y mapache_alto). Esto es fundamental para controlar los bordes: al restar el alto de la imagen del límite inferior (HEIGHT - mapache_alto), evitamos que el mapache se salga de la pantalla.

* **Posición inicial y velocidad:** *mapache_x* y *mapache_y* representan la posición inicial de la imagen. *mapache_velocidad_y* controla la velocidad y dirección del movimiento vertical. Un valor positivo hace que el mapache se mueva hacia abajo, mientras que un valor negativo lo hace subir.

* **Función `update()`:** Aquí es donde ocurre el movimiento:
    * **Movimiento vertical:** *mapache_y* se incrementa o decrementa según *mapache_velocidad_y*.
    * **Control de bordes:** comprobamos si *mapache_y* ha alcanzado el límite superior (mapache_y <= 0) o el límite inferior (mapache_y >= HEIGHT - mapache_alto). Si ha alcanzado uno de estos límites, invertimos *mapache_velocidad_y*, haciendo que el mapache rebote.


> **Ejercicio 4.** 
> * Modifica el código para que el mapache también se mueva hacia los lados, rebotando en los bordes izquierdo y derecho de la pantalla.
> * Añade un texto en pantalla que se mueva de derecha a izquierda. Cuando el texto alcance el borde izquierdo, haz que reaparezca en el borde derecho para crear un efecto de desplazamiento continuo.
> * Ajusta la velocidad del texto cambiando su velocidad y observa cómo afecta al movimiento.
> * Añade otro texto que se mueva de izquierda a derecha, pero que cambie de dirección al llegar a los bordes en lugar de reaparecer.

**IMPORTANTE:** Si quieres que la ventana de *Pygame Zero* se abra centrada en la pantalla y evitar así problemas de visualización, puedes añadir las siguientes líneas al inicio de tu código, antes de importar la biblioteca `pgzrun`:

```py
import os
os.environ['SDL_VIDEO_CENTERED'] = '1'
```

Esta configuración hace que la ventana del juego se coloque automáticamente en el centro de la pantalla cada vez que ejecutes tu programa, garantizando que todos los elementos dibujados sean visibles.