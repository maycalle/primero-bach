# 2. Eventos y controles

En esta unidad, aprenderás a dar control al jugador sobre lo que sucede en el juego. Esto es fundamental para que el jugador pueda interactuar con el juego, como mover un personaje o hacer que reaccione al pulsar teclas específicas o al hacer clic con el ratón. Los eventos de teclado y ratón son esenciales en casi cualquier tipo de juego.

## 1. Introducción a los eventos

En Pygame Zero, los **eventos** son acciones que realiza el jugador, como pulsar una tecla o hacer clic con el ratón. Podemos detectar estos eventos y programar acciones que respondan a ellos, lo que hace que el juego sea interactivo.

Existen principalmente dos tipos de eventos en Pygame Zero:
* **Eventos de teclado:** permiten que el jugador controle el juego usando teclas específicas.
* **Eventos de ratón:** permiten realizar acciones al hacer clic en ciertas partes de la pantalla.

## 2. Controlando objetos con el teclado

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

## 3. Controlando objetos con el ratón

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

