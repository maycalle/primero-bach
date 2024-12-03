# 2. Eventos y controles

En esta unidad, aprenderás a dar control al jugador sobre lo que sucede en el juego. Esto es fundamental para que el jugador pueda interactuar con el juego, como mover un personaje o hacer que reaccione al pulsar teclas específicas o al hacer clic con el ratón. Los eventos de teclado y ratón son esenciales en casi cualquier tipo de juego.

## 2.1. Introducción a los eventos

En Pygame Zero, los **eventos** son acciones que realiza el jugador, como pulsar una tecla o hacer clic con el ratón. Podemos detectar estos eventos y programar acciones que respondan a ellos, lo que hace que el juego sea interactivo.

Existen principalmente dos tipos de eventos en Pygame Zero:
* **Eventos de teclado:** permiten que el jugador controle el juego usando teclas específicas.
* **Eventos de ratón:** permiten realizar acciones al hacer clic en ciertas partes de la pantalla.

## 2.2 Controlando objetos con el teclado

Para detectar eventos de teclado, usamos el **módulo keyboard** de Pygame Zero. Este módulo permite comprobar si el jugador ha presionado una tecla específica y programar respuestas a esas acciones. 

**Ejemplo 1. Mover un objeto en pantalla usando las teclas de flecha**

```py
# Importar librerías necesarias
import pgzrun
import os

# Centrar la ventana en el monitor
os.environ['SDL_VIDEO_CENTERED'] = '1'

# Dimensiones de la pantalla
ANCHO = 800
ALTO = 600

# Posición inicial del personaje
jugador_x = 400
jugador_y = 300

def draw():
    screen.clear()
    screen.fill('lightblue')  # Fondo color azul claro
    screen.draw.circle((jugador_x, jugador_y), 30, 'blue')  # Dibuja un círculo que representa al personaje

def update():
    global jugador_x, jugador_y
    
    # Controles de movimiento usando las teclas de flecha
    if keyboard.left:
        jugador_x -= 5
    if keyboard.right:
        jugador_x += 5
    if keyboard.up:
        jugador_y -= 5
    if keyboard.down:
        jugador_y += 5

pgzrun.go() # Inicia el juego
```

> **Ejercicio 1.** 
> * Crea una figura o imagen y haz que se mueva por la pantalla usando las teclas de flecha. 
> * Modifica el valor de desplazamiento (+= 5 o -= 5) para que se mueva más rápido o más lento.
> * Prueba a mover la figura usando otras teclas, como W, A, S, D.

## 2.3 Controlando objetos con el ratón

Los **eventos de ratón** permiten al jugador interactuar con objetos haciendo clic en ellos o moviendo el ratón en la pantalla. Esto es útil para juegos en los que el jugador necesita seleccionar objetos o moverlos de acuerdo con la posición del ratón.

Pygame Zero usa la función especial `on_mouse_down(pos)` para detectar un clic. La variable `pos` nos da la posición exacta donde ocurrió el clic.

**Ejemplo 2. Cambiar la posición del personaje a otra con el ratón**

En el siguiente ejemplo se muestra cómo hacer que el personaje se traslade a la posición donde el jugador hace clic.

```py
# Importar librerías necesarias
import pgzrun
import os

# Centrar la ventana en el monitor
os.environ['SDL_VIDEO_CENTERED'] = '1'

# Dimensiones de la pantalla
ANCHO = 800
ALTO = 600

# Posición inicial del personaje
jugador_x = 400
jugador_y = 300

def draw():
    screen.clear()
    screen.fill('lightblue')  # Fondo color azul claro
    screen.draw.circle((jugador_x, jugador_y), 30, 'blue')

def on_mouse_down(pos):
    global jugador_x, jugador_y
    jugador_x, jugador_y = pos  # Mueve el personaje a la posición del clic

pgzrun.go() # Inicia el juego
```

> **Ejercicio 2.**  
> * Modifica el código del ejemplo para que el personaje cambie entre dos colores cada vez que hagas clic en la pantalla. Puedes seguir los siguientes pasos:
>       * Define una variable `color` al inicio del código (por ejemplo, color = 'green').
>       * En la función `on_mouse_down(pos)`, cambia el valor de `color` (por ejemplo, de 'green' a 'red' y viceversa).
>       * Usa la variable `color` en `draw()` para que el círculo se dibuje con el color actual.
> 
> **Ejercicio 3.** 
> * Modifica el código del ejemplo para que el tamaño del personaje aumente cada vez que el jugador hace clic en la pantalla. Puedes establecer un tamaño máximo para que no crezca indefinidamente (*if tamaño > 60: tamaño = 30*)

**Ejemplo 3. Desplazarse hacia un punto con movimiento gradual**

Vamos a ver cómo hacer que el personaje se desplace hacia el punto donde el jugador hace clic, pero de forma gradual, como si estuviera *"caminando"* o *"dirigiéndose"* hacia allí. 

Para lograrlo:
1. Calcula la dirección hacia el punto objetivo, hallando la diferencia en x (*dx*) y en y (*dy*) entre el personaje y el punto de destino.
2. Usa el **teorema de Pitágoras** para calcular la distancia entre el personaje y el destino. Según el teorema de Pitágoras, la distancia (*d*) entre los puntos se calcula con la fórmula:

<div align="center">
    <img src="/primero-bach/img/pitagoras.png" width="20%">
</div>   

   Esta distancia nos ayuda a ajustar el movimiento en cada eje (*x* e *y*) de forma proporcional, logrando que el personaje se desplace en línea recta y a una velocidad constante.

   En Python, podemos calcular la raíz cuadrada utilizando la función `sqrt()` de la librería **math**. Para acceder a `math.sqrt()` y otros métodos matemáticos, debemos importar **math** al inicio del programa.

3. Avanza en esa dirección en pequeños pasos, de forma que el personaje se desplace suavemente hacia el destino.

En el ejemplo siguiente se muestra este efecto: 

```py
# Importar librerías necesarias
import pgzrun
import os
import math

# Centrar la ventana en el monitor
os.environ['SDL_VIDEO_CENTERED'] = '1'

# Dimensiones de la pantalla
ANCHO = 800
ALTO = 600

# Posición inicial del personaje
jugador_x = 400
jugador_y = 300

# Variables de destino
destino_x = jugador_x
destino_y = jugador_y

# Velocidad de movimiento del personaje
velocidad = 3

def draw():
    screen.clear()
    screen.fill('lightblue')  # Fondo color azul claro
    screen.draw.circle((jugador_x, jugador_y), 30, 'blue')  # Dibuja el personaje

def update():
    global jugador_x, jugador_y
    
    # Calcula la distancia hacia el punto objetivo
    dx = destino_x - jugador_x
    dy = destino_y - jugador_y
    distancia = math.sqrt(dx**2 + dy**2)

    # Si el personaje no está en el destino, se mueve en esa dirección
    if distancia > velocidad:  # Para que no se pase del destino
        jugador_x += velocidad * (dx / distancia)
        jugador_y += velocidad * (dy / distancia)

def on_mouse_down(pos):
    global destino_x, destino_y
    destino_x, destino_y = pos  # Actualiza el destino a la posición del clic

pgzrun.go() # Inicia el juego
```

¡Nuestro objeto se dirige a su destino a paso firme y constante! Te explico algunos detalles: 

* **Variables de posición inicial y destino:**
    * `jugador_x` y `jugador_y` definen la posición inicial del personaje.
    * `destino_x` y `destino_y` son las coordenadas del destino al que el personaje se dirigirá cuando el jugador haga clic.
* **Evento de ratón:**
    * Cada vez que el jugador hace clic, `on_mouse_down(pos)` actualiza `destino_x` y `destino_y` a la posición del clic. Esto establece el destino y activa el movimiento del personaje hacia ese punto.
* **Cálculo de la distancia y dirección usando el teorema de Pitágoras**
    * Para que el personaje se desplace correctamente, necesitamos calcular la distancia y dirección hacia el destino aplicando el teorema de Pitágoras.
* **Desplazamiento gradual hacia el destino:**
    * Si la distancia entre el personaje y el destino es mayor que su velocidad, significa que el personaje aún no ha llegado y debe seguir avanzando hacia ese punto.
    * Para moverlo correctamente en cada eje (x e y):
        * Dividimos *dx* y *dy* (las diferencias en x e y) por la distancia total. Esto nos indica la dirección exacta en la que debe moverse el personaje.
        * Multiplicamos esta dirección por la velocidad, lo que permite que el personaje avance en pequeños pasos hacia el destino.  

> **Ejercicio 4.** 
> * Cambia la velocidad del personaje para ver cómo afecta al movimiento. Prueba diferentes valores de speed y observa los cambios.
> * Agrega un segundo personaje que también se mueva hacia donde el jugador hace clic, pero de manera más lenta. 


## 4. Control avanzado: combinando teclado y ratón

Podemos combinar los controles de teclado y ratón para hacer el juego aún más dinámico. Por ejemplo, el jugador podría moverse usando el teclado, pero disparar con el ratón en un juego de disparos.

**Ejemplo 4. Mover personaje con las teclas y disparar en una única dirección con el ratón**

Para gestionar los disparos en el juego, utilizamos una **lista** llamada `disparos`. Cada vez que el jugador hace clic, se añade un nuevo disparo a esta lista. Cada disparo tiene sus propias coordenadas en *x* e *y*, lo que permite que se muevan independientemente unos de otros.

* **Añadir disparos:** cada vez que el jugador hace clic, se crea un nuevo disparo en la posición del personaje y se añade a la lista.
* **Mover disparos:** en cada actualización (*update*), todos los disparos se mueven hacia arriba en la pantalla, simulando un disparo.
* **Eliminar disparos:** si un disparo llega a la parte superior de la pantalla, se elimina de la lista para liberar memoria y mantener el juego ordenado.

```py
# Importar librerías necesarias
import pgzrun
import os
import math

# Centrar la ventana en el monitor
os.environ['SDL_VIDEO_CENTERED'] = '1'

# Dimensiones de la pantalla
ANCHO = 800
ALTO = 600

# Posición inicial del personaje
jugador_x = 400
jugador_y = 300

# Lista para almacenar los disparos
disparos = []

def draw():
    screen.clear()
    screen.fill('lightblue')  # Fondo color azul claro
    # Dibujar el personaje como un círculo azul
    screen.draw.circle((jugador_x, jugador_y), 30, 'blue')
    # Dibujar cada disparo como un círculo rojo pequeño
    for disparo in disparos:
        screen.draw.circle(disparo, 5, 'red')

def update():
    global jugador_x, jugador_y
    # Mover el personaje con las flechas del teclado
    if keyboard.left:
        jugador_x -= 5
    if keyboard.right:
        jugador_x += 5
    if keyboard.up:
        jugador_y -= 5
    if keyboard.down:
        jugador_y += 5

    # Mover los disparos hacia arriba
    for disparo in disparos:
        disparo[1] -= 10

    # Eliminar los disparos que salen de la pantalla
    for disparo in disparos:
        if disparo[1] <= 0:
            disparos.remove(disparo)

def on_mouse_down(pos):
    # Añadir un nuevo disparo en la posición del personaje
    disparos.append([jugador_x, jugador_y])

pgzrun.go() # Inicia el juego
```

**Ejemplo 5. Mover personaje con las teclas y disparar en una varias direcciones con el ratón**

En este ejemplo, el personaje se mueve con las teclas de flecha y dispara en la dirección del ratón cuando el jugador hace clic. Este tipo de control es común en juegos de disparos, donde el jugador puede moverse en una dirección y disparar en otra.

Para gestionar los disparos, utilizamos listas para almacenar las propiedades de cada disparo, como su posición y dirección. Esto nos permite tener múltiples disparos en pantalla, cada uno avanzando en línea recta hacia donde el jugador hizo clic.

```py
# Importar librerías necesarias
import pgzrun
import math
import os

# Centrar la ventana en el monitor
os.environ['SDL_VIDEO_CENTERED'] = '1'

# Dimensiones de la pantalla
ANCHO = 800
ALTO = 600

# Posición inicial del personaje
jugador_x = 400
jugador_y = 300

# Listas para almacenar las propiedades de cada disparo
disparos_x = []  # Posiciones x de los disparos
disparos_y = []  # Posiciones y de los disparos
disparos_dx = []  # Dirección x de los disparos
disparos_dy = []  # Dirección y de los disparos
disparos_velocidad = 5  # Velocidad constante para todos los disparos

def draw():
    screen.clear()
    screen.fill('lightblue')  # Fondo color azul claro
    # Dibujar el personaje como un círculo azul
    screen.draw.circle((jugador_x, jugador_y), 30, 'blue')
    # Dibujar cada disparo como un círculo rojo pequeño
    for i in range(len(disparos_x)):
        screen.draw.circle((disparos_x[i], disparos_y[i]), 5, 'red')

def update():
    global jugador_x, jugador_y, disparos_x, disparos_y, disparos_dx, disparos_dy

    # Mover el personaje con las flechas del teclado
    if keyboard.left:
        jugador_x -= 5
    if keyboard.right:
        jugador_x += 5
    if keyboard.up:
        jugador_y -= 5
    if keyboard.down:
        jugador_y += 5

    # Mover cada disparo en su dirección
    for i in range(len(disparos_x)):
        disparos_x[i] += disparos_dx[i] * disparos_velocidad
        disparos_y[i] += disparos_dy[i] * disparos_velocidad

    # Crear listas temporales para almacenar solo los disparos dentro de la pantalla
    nuevos_disparos_x = []
    nuevos_disparos_y = []
    nuevos_disparos_dx = []
    nuevos_disparos_dy = []

    for i in range(len(disparos_x)):
        if 0 <= disparos_x[i] <= ANCHO and 0 <= disparos_y[i] <= ALTO:
            # Añadir solo los disparos dentro de la pantalla a las listas temporales
            nuevos_disparos_x.append(disparos_x[i])
            nuevos_disparos_y.append(disparos_y[i])
            nuevos_disparos_dx.append(disparos_dx[i])
            nuevos_disparos_dy.append(disparos_dy[i])

    # Actualizar las listas de disparos
    disparos_x = nuevos_disparos_x
    disparos_y = nuevos_disparos_y
    disparos_dx = nuevos_disparos_dx
    disparos_dy = nuevos_disparos_dy

def on_mouse_down(pos):
    # Calcular la dirección del disparo hacia el punto donde se hizo clic
    dx = pos[0] - jugador_x
    dy = pos[1] - jugador_y
    distancia = math.sqrt(dx**2 + dy**2)
    
    # Ajustar la dirección para que el disparo siga una línea recta hacia el clic
    dx = dx / distancia
    dy = dy / distancia

    # Añadir el nuevo disparo a cada lista
    disparos_x.append(jugador_x)
    disparos_y.append(jugador_y)
    disparos_dx.append(dx)
    disparos_dy.append(dy)

pgzrun.go()  # Inicia el juego
```

> **Ejercicio 5.** Modifica el código para que el color de cada disparo cambie en función de la dirección del clic. 
>   * Si el clic está a la derecha del personaje, el disparo debe ser azul.
>   * Si el clic está a la izquierda del personaje, el disparo debe ser rojo.
> 
> **PISTAS:**
>   * Añade una lista `disparos_color` para almacenar el color de cada disparo.
>   * En la función `on_mouse_down`, determina el color del disparo según la posición del clic en relación con la posición del personaje.
>   * Usa `screen.draw.circle` en la función draw para dibujar cada disparo con su color correspondiente.
> 
> **Ejercicio 6.** Haz que solo pueda haber un máximo de 5 disparos en pantalla a la vez. Si ya hay 5 disparos, el personaje no podrá disparar hasta que uno de ellos desaparezca de la pantalla.