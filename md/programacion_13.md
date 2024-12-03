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

¡Vamos a mejorar la mecánica del salto! Añadiremos una mecánica que permita controlar la altura del salto según el tiempo que se mantenga presionada la tecla. Este ajuste hará que el salto sea más dinámico y realista.

* **Salto bajo:** si el jugador presiona brevemente la tecla de salto.
* **Salto alto:** si el jugador la mantiene presionada más tiempo, hasta una altura máxima.

Para lograrlo, necesitamos introducir los siguientes cambios:

* **Nueva variable `salto_duracion`**:
    * Acumula el tiempo durante el cual el botón de salto está presionado.
    * Se reinicia a 0 cuando el personaje aterriza.
* **Fuerza de salto variable:**
    * Se modifica `FUERZA_SALTO` a `FUERZA_SALTO_MAX` para definir una fuerza máxima.
    * La fuerza inicial depende de la duración del botón presionado.
* **Ajustes en on_key_down y on_key_up**:
    * Cuando el jugador presiona la tecla de salto (*on_key_down*), el personaje inicia el salto con la fuerza máxima.
    * Cuando el jugador suelta la tecla (*on_key_up*), la velocidad hacia arriba se detiene, reduciendo la altura del salto.
* **Lógica de gravedad sin cambios**:
    * La gravedad continúa actuando sobre el personaje si no está en el suelo, simulando una caída natural.

A continuación, se muestra el código actualizado:

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

> **Ejercicio 2.** Modifica el código en *on_key_down* para que el jugador pueda realizar diferentes tipos de salto dependiendo de la tecla que presione. Por ejemplo:
> * **Salto bajo:** Si presiona la tecla W.
> * **Salto alto:** Si presiona la tecla SPACE.
> 
> **Pista:** puedes añadir una nueva fuerza de salto, llamada FUERZA_SALTO_BAJO, con un valor más pequeño que FUERZA_SALTO_MAX, y usar una condición `if` en `on_key_down` para verificar qué tecla se presiona.

### 5.1.3 Implementar un límite de plataformas

¡Es hora de subir el nivel! Vamos a añadir plataformas al juego y haremos que nuestro personaje pueda aterrizar en ellas. Esto significa que el personaje tendrá que "atinar" bien sus saltos para caer sobre estas superficies, ¡como en los clásicos juegos de plataformas!

Lo que haremos:
* Crear plataformas que actúen como puntos de apoyo.
* Detectar colisiones entre el personaje y las plataformas.
* Ajustar la posición del personaje para que pueda aterrizar de forma precisa sobre ellas.

#### 5.1.3.1 Crear las plataformas

Las plataformas son rectángulos (Rect) que definimos con una posición y un tamaño. Estas estructuras incluyen propiedades útiles, como `.top`, que nos ayudarán acceder fácilmente a distintas partes del rectángulo sin necesidad de cálculos adicionales.

En el código, las plataformas están organizadas en una lista para trabajar con ellas de manera sencilla:

```py
plataformas = [
    Rect((200, 500), (200, 20)),  # Plataforma baja
    Rect((400, 400), (150, 20)),  # Plataforma media
    Rect((600, 300), (100, 20))   # Plataforma alta
]
```

Para dibujarlas en la pantalla, usamos un bucle dentro de la función **draw()**:

```py
for plataforma in plataformas:
    screen.draw.filled_rect(plataforma, 'brown')  # Dibujar plataformas
```

Ahora que ya tenemos las plataformas listas, el siguiente paso es detectar si el personaje aterriza correctamente sobre ellas.

#### 5.1.3.2 Detectar colisiones

Para que el personaje pueda aterrizar en una plataforma, necesitamos comprobar si su borde inferior (el círculo azul) está tocando el borde superior de alguna de las plataformas. Esto lo logramos en la función `update()` con este fragmento:

```py
for plataforma in plataformas:
    if plataforma.collidepoint(jugador_x, jugador_y + 30) and velocidad_y > 0:
        jugador_y = plataforma.top - 30  # Ajustar para que se apoye en la parte superior
        en_el_suelo = True
        velocidad_y = 0
```

**¿Qué hace este código?**

* **Recorre las plataformas:** 
    * El bucle permite analizar las colisiones con cada plataforma de forma independiente y comprobar si el jugador colisiona con alguna de ellas durante la caída del salto. 
* **Detecta las colisiones:** 
    * Se usa `collidepoint(jugador_x, jugador_y + 30)` para comprobar si el borde inferior del personaje `(jugador_x, jugador_y + 30)` está dentro del área de la plataforma actual. El cálculo `jugador_y + 30` representa el borde inferior de nuestro personaje (recuerda que nuestro personaje es un círculo de 30 pixeles de radio).
    * La condición `velocidad_y > 0` comprueba si el personaje está cayendo. Sin esta condición, el personaje podría detectar una colisión cuando está saltando hacia arriba, lo cual no tendría sentido.
* **Ajusta la posición:**
    * Si hay una colisión, la posición vertical del personaje (`jugador_y`) se ajusta para que coincida con la parte superior de la plataforma (`plataforma.top`). La operación `plataforma.top - 30` asegura que el borde inferior del círculo del personaje quede justo en la parte superior de la plataforma.
* **Detiene la caída:**
    * Indicamos que el personaje está sobre una superficie (`en_el_suelo = True`), lo que le permitirá saltar de nuevo, y cambiamos la velocidad vertical en 0 (`velocidad_y=0`), para detener el movimiento hacia abajo del personaje tras aterrizar.

#### 5.1.3.3 Mantener la lógica del salto

El salto sigue funcionando igual que antes, pero ahora incluye las plataformas como posibles puntos de apoyo. Si el personaje está "en el suelo" (ahora, incluyendo las plataformas), podrá saltar al presionar la tecla ESPACIO.

```py
if key == keys.SPACE and en_el_suelo:
    velocidad_y = -FUERZA_SALTO
    en_el_suelo = False
```

La gravedad continúa funcionando para simular una caída natural cuando el personaje no está tocando ninguna superficie:

```py
if not en_el_suelo:
    velocidad_y += GRAVEDAD
```
#### 5.1.3.4 Código  completo

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
    Rect((200, 500), (200, 20)),  # Plataforma baja
    Rect((400, 400), (150, 20)),  # Plataforma media
    Rect((600, 300), (100, 20))   # Plataforma alta
]

def draw():
    screen.clear()
    screen.fill('lightblue')
    screen.draw.filled_rect(Rect((0, HEIGHT - 50), (WIDTH, 50)), 'green')  # Suelo
    screen.draw.circle((jugador_x, jugador_y), 30, 'blue')  # Personaje
    for plataforma in plataformas:
        screen.draw.filled_rect(plataforma, 'brown')  # Dibujar plataformas

def update():
    global jugador_x, jugador_y, velocidad_y, en_el_suelo

    # Movimiento horizontal
    if keyboard.left:
        jugador_x -= 5
    if keyboard.right:
        jugador_x += 5

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

> **Ejercicio 3:** Modifica el código para añadir al menos dos plataformas nuevas. Usa diferentes posiciones y tamaños. Prueba a crea alguna plataforma en una posición elevada (por ejemplo, y = 100), que sea difícil de alcanzar en un salto normal, y ajusta la posición inicial del jugador (jugador_x, jugador_y) para que pueda intentar alcanzarla. 
>
> **Ejercicio 4 (opcional):** Modifica el código para que durante el salto, si el jugador presiona las flechas izquierda o derecha, el personaje también se mueva horizontalmente. Puedes hacerlo sumando o restando un valor fijo a jugador_x mientras el personaje está en el aire.
> 

## 5.2 Introducción al comportamiento de enemigos

En esta sección, aprenderemos a añadir enemigos al juego y a programar su movimiento. Los enemigos añadirán un elemento de desafío, ya que el jugador tendrá que evitarlos mientras avanza por el nivel. 

### 5.2.1 Movimiento básico de enemigos en línea recta

El primer paso es programar un enemigo que se mueva horizontalmente en línea recta, cambiando de dirección al llegar a los bordes de la pantalla.

```py

# Posición y velocidad del enemigo
enemigo_x = 100
enemigo_y = 500
enemigo_velocidad = 3

def draw():
    screen.clear()
    screen.fill('lightblue')
    # Dibujar el enemigo
    screen.draw.filled_circle((enemigo_x, enemigo_y), 20, 'red')

def update():
    global enemigo_x

    # Movimiento horizontal
    enemigo_x += enemigo_velocidad

    # Cambiar dirección al llegar a los bordes
    if enemigo_x > WIDTH or enemigo_x < 0:
        enemigo_velocidad *= -1
```

> **Ejercicio 5:** Modifica el código para añadir varios enemigos al juego. Personaliza la velocidad y dirección inicial de cada enemigo.
> 
> **Ejercicio 6 (opcional):** Modifica el código para detectar la colisión del personaje con el enemigo. Para hacerlo usa la fórmula de ladistancia entre dos puntos para verificar si el círculo del enemigo y el círculo del personaje se tocan. Por último, añade una variable vidas, que vaya dosminuyendo su valor con cada colisión. Al perder todas las vidas, muestra un mensaje de "Game Over".




