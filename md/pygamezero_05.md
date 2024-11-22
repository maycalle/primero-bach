# 5. Mecanicas de juego: saltos y enemigos

## 5.1 Mecánica de saltos

### 5.1.1 Crear un personaje que pueda saltar

En este apartado, haremos que un personaje pueda saltar usando la tecla de salto. La mecánica básica requiere tres componentes principales:

* Un sistema de gravedad que tire del personaje hacia abajo.
* Una fuerza inicial que haga que el personaje salte hacia arriba.
* Condiciones para aterrizar en plataformas.

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

