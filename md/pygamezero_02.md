# 2. Eventos y controles

En esta unidad, aprenderás a dar control al jugador sobre lo que sucede en el juego. Esto es fundamental para que el jugador pueda interactuar con el juego, como mover un personaje o hacer que reaccione al pulsar teclas específicas o al hacer clic con el ratón. Los eventos de teclado y ratón son esenciales en casi cualquier tipo de juego.

## 2.1. Introducción a los eventos

En Pygame Zero, los **eventos** son acciones que realiza el jugador, como pulsar una tecla o hacer clic con el ratón. Podemos detectar estos eventos y programar acciones que respondan a ellos, lo que hace que el juego sea interactivo.

Existen principalmente dos tipos de eventos en Pygame Zero:
* **Eventos de teclado:** permiten que el jugador controle el juego usando teclas específicas.
* **Eventos de ratón:** permiten realizar acciones al hacer clic en ciertas partes de la pantalla.

## 2.2 Controlando objetos con el teclado

Para detectar eventos de teclado, usamos el **módulo keyboard** de Pygame Zero. Este módulo permite comprobar si el jugador ha presionado una tecla específica y programar respuestas a esas acciones. 

En el siguiente ejemplo se muestra cómo mover un objeto en pantalla usando las teclas de flecha:

```py
import pgzrun

# Dimensiones de la ventana del juego
WIDTH = 800
HEIGHT = 600

# Posición inicial del personaje
player_x = 400
player_y = 300

def draw():
    screen.clear()
    screen.fill('lightblue')  # Fondo color azul claro
    screen.draw.circle((player_x, player_y), 30, 'blue')  # Dibuja un círculo que representa al personaje

def update():
    global player_x, player_y
    
    # Controles de movimiento usando las teclas de flecha
    if keyboard.left:
        player_x -= 5
    if keyboard.right:
        player_x += 5
    if keyboard.up:
        player_y -= 5
    if keyboard.down:
        player_y += 5

pgzrun.go() # Inicia el juego
```

> **Ejercicio 1.** 
> * Dibuja una figura y haz que se mueva por la pantalla usando las teclas de flecha. 
> * Modifica el valor de desplazamiento (+= 5 o -= 5) para que se mueva más rápido o más lento.
> * Prueba a mover la figura usando otras teclas, como W, A, S, D.

## 2.3 Controlando objetos con el ratón

Los **eventos de ratón** permiten al jugador interactuar con objetos haciendo clic en ellos o moviendo el ratón en la pantalla. Esto es útil para juegos en los que el jugador necesita seleccionar objetos o moverlos de acuerdo con la posición del ratón.

Pygame Zero usa la función especial `on_mouse_down(pos)` para detectar un clic. La variable `pos` nos da la posición exacta donde ocurrió el clic.

**Ejemplo 1. Cambiar la posición del personaje con el ratón**

En el siguiente ejemplo se muestra cómo hacer que el personaje se traslade a la posición donde el jugador hace clic.

```py
import pgzrun

WIDTH = 800
HEIGHT = 600

player_x = 400
player_y = 300

def draw():
    screen.clear()
    screen.fill('lightblue')  # Fondo color azul claro
    screen.draw.circle((player_x, player_y), 30, 'green')

def on_mouse_down(pos):
    global player_x, player_y
    player_x, player_y = pos  # Mueve el personaje a la posición del clic

pgzrun.go() # Inicia el juego
```

> **Ejercicio 2.** 
> Usa el ratón para controlar un objeto en pantalla.
> Haz que el objeto cambie de color cuando el jugador hace clic.
> Agrega un segundo personaje que se mueva hacia donde el jugador hace clic, pero de manera más lenta.

**Ejemplo 2. Desplazarse hacia un punto con movimiento gradual**

Vamos a ver cómo hacer que el personaje se desplace hacia el punto donde el jugador hace clic, pero de forma gradual, como si estuviera *"caminando"* o *"dirigiéndose"* hacia allí. 

Para lograrlo:
1. Calcula la dirección hacia el punto objetivo, hallando la diferencia en x (*dx*) y en y (*dy*) entre el personaje y el punto de destino.
2. Usa el **teorema de Pitágoras** para calcular la distancia entre el personaje y el destino. Según el teorema de Pitágoras, la distancia (*d*) entre los puntos se calcula con la fórmula:
    $$
    d = \sqrt{(dx)^2 + (dy)^2}
    $$

   Esta distancia nos ayuda a ajustar el movimiento en cada eje (*x* e *y*) de forma proporcional, logrando que el personaje se desplace en línea recta y a una velocidad constante.

   En Python, podemos calcular la raíz cuadrada utilizando la función `sqrt()` de la librería **math**. Para acceder a `math.sqrt()` y otros métodos matemáticos, debemos importar **math** al inicio del programa.

3. Avanza en esa dirección en pequeños pasos, de forma que el personaje se desplace suavemente hacia el destino.

En el ejemplo siguiente se muestra este efecto: 

```py
import pgzrun
import math

WIDTH = 800
HEIGHT = 600

# Posición inicial del personaje
player_x = 400
player_y = 300

# Variables de destino
target_x = player_x
target_y = player_y

# Velocidad de movimiento del personaje
speed = 3

def draw():
    screen.clear()
    screen.fill('lightblue')  # Fondo color azul claro
    screen.draw.circle((player_x, player_y), 30, 'blue')  # Dibuja el personaje

def update():
    global player_x, player_y
    
    # Calcula la distancia hacia el punto objetivo
    dx = target_x - player_x
    dy = target_y - player_y
    distance = math.sqrt(dx**2 + dy**2)

    # Si el personaje no está en el destino, se mueve en esa dirección
    if distance > speed:  # Para que no se pase del destino
        player_x += speed * (dx / distance)
        player_y += speed * (dy / distance)

def on_mouse_down(pos):
    global target_x, target_y
    target_x, target_y = pos  # Actualiza el destino a la posición del clic

pgzrun.go() # Inicia el juego
```

¡Nuestro objeto se dirige a su destino a paso firme y constante! Te explico algunos detalles: 

* **Variables de posición inicial y destino:**
    * `player_x` y `player_y` definen la posición inicial del personaje.
    * `target_x` y `target_y` son las coordenadas del destino al que el personaje se dirigirá cuando el jugador haga clic.
* **Evento de ratón:**
    * Cada vez que el jugador hace clic, `on_mouse_down(pos)` actualiza `target_x` y `target_y` a la posición del clic. Esto establece el destino y activa el movimiento del personaje hacia ese punto.
* **Cálculo de la distancia y dirección usando el teorema de Pitágoras**
    * Para que el personaje se desplace correctamente, necesitamos calcular la distancia y dirección hacia el destino aplicando el teorema de Pitágoras.
* **Desplazamiento gradual hacia el destino:**
    * Si la distancia entre el personaje y el destino es mayor que su velocidad (*speed*), significa que el personaje aún no ha llegado y debe seguir avanzando hacia ese punto.
    * Para moverlo correctamente en cada eje (x e y):
        * Dividimos *dx* y *dy* (las diferencias en x e y) por la distancia total. Esto nos indica la dirección exacta en la que debe moverse el personaje.
        * Multiplicamos esta dirección por la velocidad (*speed*), lo que permite que el personaje avance en pequeños pasos hacia el destino.  

> **Ejercicio 3.** 
> * Cambia la velocidad del personaje para ver cómo afecta al movimiento. Prueba diferentes valores de speed y observa los cambios.
> * Agrega una condición para que el personaje cambie de color o muestre una animación mientras se mueve hacia el destino.
> * Añade un segundo objetivo en pantalla y haz que el personaje cambie automáticamente de dirección al llegar a un objetivo.

## 4. Control avanzado: combinando teclado y ratón

Podemos combinar los controles de teclado y ratón para hacer el juego aún más dinámico. Por ejemplo, el jugador podría moverse usando el teclado, pero disparar con el ratón en un juego de disparos.

**Ejemplo básico: personaje que se mueve con las teclas y dispara en una única dirección con el ratón**

Para gestionar los disparos en el juego, utilizamos una **lista** llamada `disparos`. Cada vez que el jugador hace clic, se añade un nuevo disparo a esta lista. Cada disparo tiene sus propias coordenadas en *x* e *y*, lo que permite que se muevan independientemente unos de otros.

* **Añadir disparos:** cada vez que el jugador hace clic, se crea un nuevo disparo en la posición del personaje y se añade a la lista.
* **Mover disparos:** en cada actualización (*update*), todos los disparos se mueven hacia arriba en la pantalla, simulando un disparo.
* **Eliminar disparos:** si un disparo llega a la parte superior de la pantalla, se elimina de la lista para liberar memoria y mantener el juego ordenado.

```py
import pgzrun

WIDTH = 800
HEIGHT = 600

# Posición inicial del personaje
player_x = 400
player_y = 300

# Lista para almacenar los disparos
disparos = []

def draw():
    screen.clear()
    screen.fill('lightblue')  # Fondo color azul claro
    # Dibujar el personaje como un círculo azul
    screen.draw.circle((player_x, player_y), 30, 'blue')
    # Dibujar cada disparo como un círculo rojo pequeño
    for disparo in disparos:
        screen.draw.circle(disparo, 5, 'red')

def update():
    global player_x, player_y
    # Mover el personaje con las flechas del teclado
    if keyboard.left:
        player_x -= 5
    if keyboard.right:
        player_x += 5
    if keyboard.up:
        player_y -= 5
    if keyboard.down:
        player_y += 5

    # Mover los disparos hacia arriba
    for disparo in disparos:
        disparo[1] -= 10

    # Eliminar los disparos que salen de la pantalla
    for disparo in disparos:
        if disparo[1] <= 0:
            disparos.remove(disparo)

def on_mouse_down(pos):
    # Añadir un nuevo disparo en la posición del personaje
    disparos.append([player_x, player_y])

pgzrun.go() # Inicia el juego
```

**Ejemplo avanzado: personaje que se mueve con las teclas y dispara en una varias direcciones con el ratón**

En este ejemplo, el personaje se mueve con las teclas de flecha y dispara en la dirección del ratón cuando el jugador hace clic. Este tipo de control es común en juegos de disparos, donde el jugador puede moverse en una dirección y disparar en otra.

Para gestionar los disparos, utilizamos listas para almacenar las propiedades de cada disparo, como su posición y dirección. Esto nos permite tener múltiples disparos en pantalla, cada uno avanzando en línea recta hacia donde el jugador hizo clic.

```py
import pgzrun
import math

WIDTH = 800
HEIGHT = 600

# Posición inicial del personaje
player_x = 400
player_y = 300

# Listas para almacenar las propiedades de cada disparo
disparos_x = []  # Posiciones x de los disparos
disparos_y = []  # Posiciones y de los disparos
disparos_dx = []  # Dirección x de los disparos
disparos_dy = []  # Dirección y de los disparos
disparos_speed = 5  # Velocidad constante para todos los disparos

def draw():
    screen.clear()
    screen.fill('lightblue')  # Fondo color azul claro
    # Dibujar el personaje como un círculo azul
    screen.draw.circle((player_x, player_y), 30, 'blue')
    # Dibujar cada disparo como un círculo rojo pequeño
    for i in range(len(disparos_x)):
        screen.draw.circle((disparos_x[i], disparos_y[i]), 5, 'red')

def update():
    global player_x, player_y
    # Mover el personaje con las flechas del teclado
    if keyboard.left:
        player_x -= 5
    if keyboard.right:
        player_x += 5
    if keyboard.up:
        player_y -= 5
    if keyboard.down:
        player_y += 5

    # Mover cada disparo en su dirección
    for i in range(len(disparos_x)):
        disparos_x[i] += disparos_dx[i] * disparos_speed
        disparos_y[i] += disparos_dy[i] * disparos_speed

    # Eliminar los disparos que salen de la pantalla
    for i in range(len(disparos_x)):
        if disparos_x[i] < 0 or disparos_x[i] > WIDTH or disparos_y[i] < 0 or disparos_y[i] > HEIGHT:
            # Eliminar disparo fuera de pantalla de todas las listas usando remove()
            disparos_x.remove(disparos_x[i])
            disparos_y.remove(disparos_y[i])
            disparos_dx.remove(disparos_dx[i])
            disparos_dy.remove(disparos_dy[i])

def on_mouse_down(pos):
    # Calcular la dirección del disparo hacia el punto donde se hizo clic
    dx = pos[0] - player_x
    dy = pos[1] - player_y
    distance = math.sqrt(dx**2 + dy**2)
    # Ajustar la dirección para que el disparo siga una línea recta hacia el clic
    dx = dx/distance
    dy = dy/distance

    # Añadir el nuevo disparo a cada lista
    disparos_x.append(player_x)
    disparos_y.append(player_y)
    disparos_dx.append(dx)
    disparos_dy.append(dy)

pgzrun.go()  # Inicia el juego
```

> **Ejercicio 4.**
> * Haz que el color de cada disparo cambie en función de la dirección del clic. Por ejemplo, si el clic está a la derecha del personaje, el disparo es azul, si está a la izquierda es rojo, y si está arriba o abajo es verde.
> * Modifica el código para que solo haya un máximo de 5 disparos en pantalla a la vez. Si ya hay 5 disparos, el personaje no podrá disparar hasta que uno de ellos desaparezca de la pantalla.