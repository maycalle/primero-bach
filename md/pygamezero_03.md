# 3. Colisiones básicas

En los videojuegos, la detección de colisiones es fundamental para la interacción entre los elementos del juego, como cuando un personaje recoge un objeto, choca con un obstáculo o dispara a un enemigo. En esta sección, aprenderemos los principios básicos para detectar colisiones entre objetos en pantalla.

## 3.1 Colisiones circulares usando distancias

Para detectar colisiones entre dos objetos de forma circular (como un personaje y una moneda), podemos calcular la distancia entre sus centros y compararla con el radio de los objetos. Si la distancia es menor o igual a la suma de los radios, decimos que los objetos están colisionando.

**Ejemplo 1: Colisión entre el jugador y un tesoro**

Veamos un ejemplo donde un dinosaurio recoge un brocoli al acercarse a él e incrementa su puntuación.

```py
# Importar librerías necesarias
import pgzrun
import math
import random
import pygame

# Dimensiones de la pantalla
ANCHO = 800
ALTO = 600

# Posiciones iniciales del jugador y el tesoro
jugador_x = 100
jugador_y = 100
tesoro_x = 400
tesoro_y = 300

# Puntuación del jugador
puntuacion = 0

# Cargar las imágenes y calcular sus radios una sola vez
imagen_jugador = pygame.image.load("images/dinosaurio.png")  # Ruta de la imagen del jugador
ancho_jugador = imagen_jugador.get_width()
alto_jugador = imagen_jugador.get_height()
radio_jugador = min(ancho_jugador, alto_jugador) // 2  # Calcular el radio del jugador

imagen_tesoro = pygame.image.load("images/brocoli.png")  # Ruta de la imagen del tesoro
ancho_tesoro = imagen_tesoro.get_width()
alto_tesoro = imagen_tesoro.get_height()
radio_tesoro = min(ancho_tesoro, alto_tesoro) // 2  # Calcular el radio del tesoro

def draw():
    screen.clear()
    screen.fill('lightblue')
    
    # Dibujar el jugador
    screen.blit(imagen_jugador, (jugador_x, jugador_y))
        
    # Dibujar el tesoro
    screen.blit(imagen_tesoro, (tesoro_x, tesoro_y))
    
    # Mostrar la puntuación
    screen.draw.text(f'Puntuación: {puntuacion}', (10, 10), color='black', fontsize=30)

def update():
    global jugador_x, jugador_y, puntuacion, tesoro_x, tesoro_y

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
        # Mover el tesoro a una nueva posición al azar
        tesoro_x = random.randint(0, ANCHO - ancho_tesoro)
        tesoro_y = random.randint(0, ALTO - alto_tesoro)

pgzrun.go()
```

**Cambiar el tamaño de una imagen en Pygame Zero**

En Pygame Zero, no hay una función directa para cambiar el tamaño de una imagen, ya que está diseñado para simplificar el proceso de desarrollo de juegos y no incluye toda la funcionalidad de Pygame completa. Sin embargo, puedes cambiar el tamaño de una imagen utilizando la **biblioteca pygame** junto con `pygame.transform.scale()` y luego usar Pygame Zero para mostrar la imagen escalada.

```py
# Importar librerías necesarias
import pygame

# Carga la imagen y la escala
imagen_original = pygame.image.load("images/dinosaurio.png")  
# Cambia el tamaño de la imagen a 100x100 píxeles
imagen_escalada = pygame.transform.scale(imagen_original, (100, 100))  
```

> **Ejercicio 1.** Haz que el brócoli caiga desde la parte superior de la pantalla. Puedes ajustar la posición `y` del brócoli en cada actualización. Así, cada vez que se llama a `update()`, el brócoli se desplazará hacia abajo. Cuando llegue al final de la pantalla, puedes hacer que reaparezca en la parte superior o en una posición aleatoria en el eje x.
