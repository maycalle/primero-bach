# 4. Sonido, temporización y estados de juego

En esta unidad, aprenderás a incorporar elementos avanzados que harán tu juego mucho más interesante. Estos elementos incluyen:

* Agregar un fondo visual para mejorar la ambientación del juego.
* Incluir sonidos que den feedback al jugador.
* Programar eventos que ocurran automáticamente después de un intervalo.
* Implementar diferentes estados del juego, como una pantalla de inicio, de juego y de fin, para mejorar la estructura general del juego.
 
Construiremos estos elementos sobre el ejemplo del dinosaurio que recoge brócoli, paso a paso. ¡Comencemos!

Puedes [descargar aquí las imágenes y sonidos](recursos/recursos_unidad3.zip) utilizados en los ejemplos.

## 4.1 Dibujar un fondo en el juego

Lo primero que haremos es añadir un fondo. Este elemento básico ayuda a crear un ambiente en el juego, haciendo que se vea más completo y atractivo.

Para dibujar un fondo en Pygame Zero:

1. Guarda la imagen del fondo en una carpeta llamada **images**, ubicada en el mismo directorio donde guardas el archivo de tu código.
2. Asegúrate de que la imagen sea compatible con el tamaño de tu ventana de juego (800x600 en este ejemplo).
3. Usa `screen.blit("nombre_de_imagen", (0, 0))` en la función `draw()` para colocar el fondo en la pantalla.

**Ejemplo: agregar el fondo al juego**

```py

# Carga la imagen de fondo
imagen_fondo = pygame.image.load("images/fondo_juego.png")  

def draw():
    screen.clear()    

    # Dibujar el fondo        
    screen.blit(imagen_fondo, (0, 0))
    
    # Dibujar el jugador
    screen.blit(imagen_jugador, (jugador_x, jugador_y))

    ... 

```

> **Ejercicio 1.** Cambia la imagen de fondo para experimentar con diferentes temas visuales y observa cómo afecta a la ambientación del juego.

## 4.2 Agregar sonido al juego

El sonido es fundamental en los videojuegos, ya que refuerza las interacciones y hace que el juego sea más dinámico. En este paso, añadiremos un efecto de sonido para que se reproduzca cada vez que el dinosaurio recoja un brócoli.

1. Guarda los archivos de sonido en formato **.wav** o **.ogg** en una **carpeta sounds** dentro del directorio de tu proyecto.
2. Usa `sounds.nombre_del_sonido.play()` para reproducir el sonido en el momento deseado. Por ejemplo, si tienes un fichero de audio llamado **comer.wav** tendrías que poner `sounds.comer.play()` donde quieras que se reproduzca. En nuestro caso, nos interesa ponerlo dentro de la función `update()` justo cuando se detecta la colisión con el brocoli.

**Ejemplo: agregar sonido al recoger el brocoli**

```py
def update():
    ... 
    # Detectar colisión
    if distancia <= (radio_jugador + radio_tesoro):
        puntuacion += 1  # Aumentar la puntuación
        sounds.comer.play()
        # Mover el tesoro a una nueva posición al azar
        tesoro_x = random.randint(0, WIDTH - ancho_tesoro)
        tesoro_y = random.randint(0, HEIGHT - alto_tesoro)

```

> **Ejercicio 2.** Cambia el sonido por uno diferente o añade otros para diferentes situaciones (por ejemplo, que alcanze el borde de la pantalla o cuando llegue a 10 puntos). Puedes visitar [Pixabay Sounds](https://pixabay.com/es/sound-effects/) para buscar más sonidos. Recuerda que el archivo de audio solo puede ser **.wav** o **.ogg**. Puedes utilizar Audacity para covertir .mp3 a .wav o buscar por Internet algún conversor de audio online.

## 4.3 Programar eventos temporales con clock.schedule_unique()

A veces queremos que ciertos elementos se activen solo durante unos segundos o que se muevan de forma automática después de un intervalo de tiempo. En Pygame Zero, podemos programar estos eventos con `clock.schedule_unique()`.

**Ejemplo: mostrar un mensaje temporal al recoger el brócoli**

Queremos que aparezca un mensaje diciendo *"¡Brócoli recogido!"* cada vez que el dinosaurio se coma un brócoli, y que este mensaje desaparezca después de 2 segundos.

```py

# Variable para mensaje temporal
mensaje = ""

def draw():
    screen.clear()

    # Dibujar el fondo
    screen.blit("imagen_fondo.png", (0, 0))

    # Dibujar el dinosaurio y el brócoli
    screen.blit("dino.png", (jugador_x, jugador_y))
    screen.blit("brocoli.png", (tesoro_x, tesoro_y))

    # Mostrar la puntuación
    screen.draw.text(f'Puntuación: {puntuacion}', (10, 10), color='black', fontsize=30)

    # Mostrar el mensaje temporal si existe
    if mensaje:
        screen.draw.text(mensaje, (WIDTH // 2 - 100, HEIGHT // 2), color="white", fontsize=40)

def mostrar_mensaje(texto):
    global mensaje
    mensaje = texto
    # Programar el borrado del mensaje después de 2 segundos
    clock.schedule_unique(borrar_mensaje, 2)

def borrar_mensaje():
    global mensaje
    mensaje = ""  # Limpia el mensaje después de 2 segundos

... 

```

La función `mostrar_mensaje()` debe ser llamada cada vez que el dinosaurio recoge un brócoli, para mostrar el mensaje temporal *"¡Brócoli recogido!"* y luego hacer que desaparezca después de unos segundos

```py
def update():
    global jugador_x, jugador_y, puntuacion, tesoro_x, tesoro_y, estado_juego

    if estado_juego == "jugando":
        # Movimiento del jugador
        if keyboard.left:
            jugador_x -= 5
        if keyboard.right:
            jugador_x += 5
        if keyboard.up:
            jugador_y -= 5
        if keyboard.down:
            jugador_y += 5

        # Detectar colisión entre el dinosaurio y el brócoli
        distancia = math.sqrt((jugador_x - tesoro_x) ** 2 + (jugador_y - tesoro_y) ** 2)
        if distancia < 50:
            puntuacion += 1
            sounds.recoger.play()  # Reproduce el sonido de recogida
            mostrar_mensaje("¡Brócoli recogido!")  # Llama a la función mostrar_mensaje() para mostrar el mensaje
            # Mover el tesoro a una nueva posición al azar
            brocoli_x = random.randint(0, WIDTH - ancho_brocoli)
            brocoli_y = random.randint(0, HEIGHT - alto_brocoli)
        
```

Para hacerlo más interesante, podemos hacer que el brocoli cambie de sitio cada 10 segundos. Crea una función llamada `mover_brocoli()` que calcule una nueva posición aleatoria transcurrido ese tiempo.

```py

def mover_brocoli():
    global brocoli_x, brocoli_y
    brocoli_x = random.randint(0, WIDTH - 50)
    brocoli_y = random.randint(0, HEIGHT - 50)
    clock.schedule_unique(mover_brocoli, 10)

```

> **Ejercicio 3.** Cambia los tiempos y observa la diferencia


## 4.4 Implementar estados de juego

Para mejorar la estructura del juego, implementaremos diferentes estados que controlan qué se muestra y cómo responde el juego en cada momento. Los estados incluyen:

* **Inicio:** una pantalla de bienvenida con instrucciones.
* **Juego:** la pantalla principal donde el dinosaurio recoge brócolis.
* **Fin:** una pantalla final que muestra la puntuación total y la opción de reiniciar.

**Ejemplo: agregar estados al juego**

Usaremos una variable `estado_juego` para almacenar el estado actual. Esto nos permitirá cambiar entre los diferentes estados y controlar qué se muestra en cada pantalla.

```py

# Estado del juego: "inicio", "jugando", "fin"
estado_juego = "inicio"

def draw():
    screen.clear()
    
    if estado_juego == "inicio":
        # Pantalla de inicio
        screen.blit(imagen_fondo, (0, 0))
        screen.draw.text("¡Bienvenido al Juego del Dinosaurio y el Brócoli!", (100, 150), color="white", fontsize=40)
        screen.draw.text("Presiona Enter para comenzar", (200, 300), color="yellow", fontsize=30)
    elif estado_juego == "jugando":
        # Pantalla del juego en progreso
        screen.blit(imagen_fondo, (0, 0))
        screen.blit(imagen_dino, (jugador_x, jugador_y))
        screen.blit(imagen_brocoli, (tesoro_x, tesoro_y))
        screen.draw.text(f'Puntuación: {puntuacion}', (10, 10), color='black', fontsize=30)
        if mensaje:
            screen.draw.text(mensaje, (WIDTH // 2 - 100, HEIGHT // 2), color="white", fontsize=40)
    elif estado_juego == "fin":
        # Pantalla de fin del juego
        screen.blit(imagen_fondo, (0, 0))
        screen.draw.text("¡Fin del Juego!", (300, 150), color="red", fontsize=50)
        screen.draw.text(f"Puntuación final: {puntuacion}", (300, 250), color="white", fontsize=40)
        screen.draw.text("Presiona R para reiniciar", (250, 400), color="yellow", fontsize=30)

def update():
    global jugador_x, jugador_y, puntuacion, tesoro_x, tesoro_y, estado_juego

    if estado_juego == "jugando":
		# Condición de fin del juego
        if puntuacion >= 10:
            estado_juego = "fin"
    
        # Controles del jugador con las flechas
        if keyboard.left:
            jugador_x -= 5
        if keyboard.right:
            jugador_x += 5
        if keyboard.up:
            jugador_y -= 5
        if keyboard.down:
            jugador_y += 5
    
		# Calcular la distancia entre el jugador y el tesoro
        distancia = math.sqrt((jugador_x - tesoro_x) ** 2 + (jugador_y - tesoro_y) ** 2)

		# Detectar colisión
        if distancia <= (radio_jugador + radio_tesoro):
            puntuacion += 1  # Aumentar la puntuación
            sounds.comer.play()
            # Mover el tesoro a una nueva posición al azar
            tesoro_x = random.randint(0, WIDTH - ancho_tesoro)
            tesoro_y = random.randint(0, HEIGHT - alto_tesoro)

```

Por último vamos a establecer una lógica para navegar entre los diferentes estados del juego:

* **Pulsar enter en la pantalla de inicio:** inicia el juego y configura las variables principales (posición del dinosaurio y puntuación) para un nuevo comienzo.
* **Pulsar R en la pantalla de fin:** lleva al jugador de vuelta a la pantalla de inicio, permitiéndole reiniciar el juego.

```py

def on_key_down(key):
    global estado_juego, jugador_x, jugador_y, puntuacion
    if estado_juego == "inicio" and key == keys.RETURN:
        estado_juego = "jugando"
        jugador_x, jugador_y = 100, 100
        puntuacion = 0
        mover_brocoli()
    elif estado_juego == "fin" and key == keys.R:
        estado_juego = "inicio"

``` 

> **Ejercicio 4. Aumenta la dificultad del juego** 
> * Cada vez que el jugador recoge un brócoli, aumenta la velocidad de movimiento del dinosaurio en 1 punto. 
> * Define una variable `velocidad` para el movimiento del dinosaurio y aumenta su valor en `update()` cuando el jugador recoge un brócoli.

> **Ejercicio 5. Haz que el brocoli caiga desde la parte superior de la pantalla.**
> En lugar de que el brócoli aparezca en una posición aleatoria fija, vamos a hacer que caiga continuamente desde la parte superior de la pantalla. Cada vez que llegue al suelo (parte inferior de la pantalla) o que el dinosaurio lo recoja, el brócoli volverá a caer desde una nueva posición aleatoria en la parte superior.
> * Define una velocidad vertical para el brócoli.
> * Haz que el brócoli se mueva hacia abajo en cada actualización de la función update().
> * Si el brócoli llega a la parte inferior de la pantalla sin ser recogido, vuelve a colocarlo en una posición aleatoria en la parte superior.
> * Si el dinosaurio recoge el brócoli, reposiciónalo en la parte superior también y aumenta la puntuación.

