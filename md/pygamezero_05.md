# 5. Mecanicas de juego: saltos y enemigos

En esta unidad aprenderemos a implementar mecánicas básicas de juego relacionadas con saltos, plataformas, y enemigos. 

## 5.1 Mecánica de saltos

El salto es una de las mecánicas más comunes en los videojuegos. Para implementarlo necesitamos considerar:

* Un sistema de gravedad que tire del personaje hacia abajo.
* Una fuerza inicial que impulse al personaje hacia arriba.
* Condiciones que determinen cuándo el personaje puede aterrizar.

### 5.1.1 Crear un personaje que pueda saltar

En este apartado, haremos que un personaje salte y aterrice correctamente. El objetivo es que cuando el jugador presione la tecla de salto (la que queramos), una fuerza inicial lo impulse hacia arriba. A continuación, la gravedad simulará la fuerza que tira del personaje hacia abajo, haciéndolo regresar al suelo y detenerse cuando aterrice.

Para implementar esta mecánica, definiremos las siguientes variables:

* **GRAVEDAD:**
    * Representa la fuerza que tira del personaje hacia abajo.
    * Este valor se suma a la velocidad vertical (`velocidad_y`) del personaje en cada fotograma si está en el aire.
* **FUERZA_SALTO:**
    * Define la intensidad con la que el personaje es impulsado hacia arriba al saltar.
* **en_el_suelo:**
    * Variable booleana que indica si el personaje está en contacto con el suelo.
    * Si es `True`, el personaje está listo para saltar.

Y realizaremos los siguientes cambios en la lógica del juego en la `función update()`: 

* **Gravedad:**
    * Si el personaje no está en el suelo (`en_el_suelo == False`), se le aplica la gravedad aumentando su velocidad vertical (`velocidad_y`).
* **Movimiento vertical:**
    * El valor de `velocidad_y` se suma a la posición vertical del personaje (`jugador_y`), haciendo que suba o baje según corresponda.
 * **Colisión con el suelo:**
    * Si `jugador_y` alcanza el nivel del suelo (`HEIGHT - 80`), el personaje se detiene y su posición se ajusta para alinearse con el suelo.
* **Reinicio de variables:**
    * Al aterrizar, se establece `en_el_suelo = True` para indicar que el personaje puede volver a saltar.
    * La velocidad vertical (`velocidad_y`) se reinicia a 0.

A continuación, se indica el código que implementa el salto:

```py
import pgzrun

# Configuración inicial
WIDTH = 800
HEIGHT = 600
GRAVEDAD = 1
FUERZA_SALTO = 15

# Posición y velocidad inicial del jugador
jugador_x = 400
jugador_y = 500
velocidad_y = 0

# Estado del salto
en_el_suelo = True

def draw():
    screen.clear()
    screen.fill('lightblue')
    # El suelo es un rectángulo que ocupa todo el ancho de la pantalla y está ubicado 50 píxeles por encima del borde inferior.
    screen.draw.filled_rect(Rect((0, HEIGHT - 50), (WIDTH, 50)), 'green')  # Suelo
    screen.draw.circle((jugador_x, jugador_y), 30, 'blue')  # Personaje

def update():
    global jugador_y, velocidad_y, en_el_suelo

    # Aplicar gravedad si el personaje no está en el suelo
    if not en_el_suelo:
        velocidad_y += GRAVEDAD

    # Actualizar la posición vertical del jugador
    jugador_y += velocidad_y

    # Verificar colisión con el suelo
    if jugador_y >= HEIGHT - 80:
        jugador_y = HEIGHT - 80
        en_el_suelo = True
        velocidad_y = 0

def on_key_down(key):
    global velocidad_y, en_el_suelo
    if key == keys.SPACE and en_el_suelo:  # Salta con espacio
        velocidad_y = -FUERZA_SALTO
        en_el_suelo = False

pgzrun.go()
```

> **Ejercicio 1.** Modifica el código para que el personaje salte más alto al presionar la tecla Shift (`keys.LSHIFT`) en lugar de la barra espaciadora.

### 5.1.2 Controlar la altura del salto con la duración del botón presionado

Para controlar la altura del salto, podemos ajustar la lógica para que la fuerza inicial del salto dependa de cuánto tiempo el jugador mantenga presionada la tecla.

```py
import pgzrun

# Configuración inicial
WIDTH = 800
HEIGHT = 600
GRAVEDAD = 1
FUERZA_SALTO_MAX = 15

# Posición y velocidad inicial del jugador
jugador_x = 400
jugador_y = 500
velocidad_y = 0

# Estado del salto
en_el_suelo = True
salto_duracion = 0

def draw():
    screen.clear()
    screen.fill('lightblue')
    screen.draw.filled_rect(Rect((0, HEIGHT - 50), (WIDTH, 50)), 'green')  # Suelo
    screen.draw.circle((jugador_x, jugador_y), 30, 'blue')  # Personaje

def update():
    global jugador_y, velocidad_y, en_el_suelo, salto_duracion

    # Aplicar gravedad si el personaje no está en el suelo
    if not en_el_suelo:
        velocidad_y += GRAVEDAD

    # Actualizar la posición vertical del jugador
    jugador_y += velocidad_y

    # Verificar colisión con el suelo
    if jugador_y >= HEIGHT - 80:
        jugador_y = HEIGHT - 80
        en_el_suelo = True
        velocidad_y = 0
        salto_duracion = 0  # Reiniciar duración del salto al aterrizar

def on_key_down(key):
    global velocidad_y, en_el_suelo, salto_duracion
    if key == keys.SPACE and en_el_suelo:  # Comienza a saltar
        velocidad_y = -FUERZA_SALTO_MAX
        en_el_suelo = False

def on_key_up(key):
    global velocidad_y
    if key == keys.SPACE and velocidad_y < 0:  # Reduce la altura si se suelta pronto
        velocidad_y = 0

pgzrun.go()
```

### 5.1.3 Implementar un límite de plataformas

Añadiremos plataformas al juego y haremos que el personaje solo pueda aterrizar en ellas. Esto requiere detectar colisiones con múltiples plataformas.

```py
import pgzrun

# Configuración inicial
WIDTH = 800
HEIGHT = 600
GRAVEDAD = 1
FUERZA_SALTO = 15

# Posición y velocidad inicial del jugador
jugador_x = 400
jugador_y = 500
velocidad_y = 0

# Estado del salto
en_el_suelo = False

# Plataformas
plataformas = [
    Rect((200, 400), (200, 20)),
    Rect((500, 300), (150, 20)),
    Rect((300, 200), (100, 20))
]

def draw():
    screen.clear()
    screen.fill('lightblue')
    screen.draw.filled_rect(Rect((0, HEIGHT - 50), (WIDTH, 50)), 'green')  # Suelo
    screen.draw.circle((jugador_x, jugador_y), 30, 'blue')  # Personaje
    for plataforma in plataformas:
        screen.draw.filled_rect(plataforma, 'brown')  # Dibujar plataformas

def update():
    global jugador_y, velocidad_y, en_el_suelo

    # Aplicar gravedad si el personaje no está en el suelo
    if not en_el_suelo:
        velocidad_y += GRAVEDAD

    # Actualizar la posición vertical del jugador
    jugador_y += velocidad_y
    en_el_suelo = False  # Asumir que el jugador está en el aire

    # Verificar colisión con el suelo
    if jugador_y >= HEIGHT - 80:
        jugador_y = HEIGHT - 80
        en_el_suelo = True
        velocidad_y = 0

    # Verificar colisión con plataformas
    for plataforma in plataformas:
        if plataforma.collidepoint(jugador_x, jugador_y + 30) and velocidad_y > 0:
            jugador_y = plataforma.top - 30
            en_el_suelo = True
            velocidad_y = 0

def on_key_down(key):
    global velocidad_y, en_el_suelo
    if key == keys.SPACE and en_el_suelo:  # Salta con espacio
        velocidad_y = -FUERZA_SALTO
        en_el_suelo = False

pgzrun.go()
```

## 5.2 Introducción al comportamiento de enemigos

### 5.2.1 Movimiento básico de enemigos en línea recta

Haremos que un enemigo se mueva horizontalmente en línea recta.

```py
enemigo_x = 100
enemigo_y = 500
enemigo_velocidad = 3

def draw():
    screen.clear()
    screen.fill('lightblue')
    screen.draw.filled_circle((enemigo_x, enemigo_y), 20, 'red')

def update():
    global enemigo_x
    enemigo_x += enemigo_velocidad

    # Cambiar dirección al llegar a los bordes
    if enemigo_x > WIDTH or enemigo_x < 0:
        enemigo_velocidad *= -1

```

