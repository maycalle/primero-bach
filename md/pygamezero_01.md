# 1. Primeros pasos con Pygame Zero

¡Bienvenido/a al mundo de **Pygame Zero**! Un entorno que hace que desarrollar videojuegos 2D sea fácil y accesible, especialmente si ya sabes un poco de Python. ¡Con Pygame Zero, no solo aprenderás programación, sino que también podrás crear tus propios videojuegos de forma sencilla y divertida!

## 1. ¿Qué es Pygame Zero?

**Pygame Zero** es una versión simplificada de *Pygame*, diseñada para facilitar el desarrollo de videojuegos 2D de manera rápida y sencilla. No es necesario tener un conocimiento profundo sobre el funcionamiento interno de los videojuegos para comenzar a crear.

A diferencia de *Pygame*, **Pygame Zero** elimina la necesidad de configurar manualmente la ventana del juego y escribir el bucle principal. Esto significa que no tienes que preocuparte por manejar eventos o dibujar desde cero. En su lugar, *Pygame Zero* te permite centrarte en los aspectos más divertidos e importantes del desarrollo de un videojuego: **dibujar objetos** en pantalla, **mover personajes** y hacer que el **juego sea interactivo**.

**Ejemplos de juegos que puedes hacer con Pygame Zero:**
* **Juego de plataformas** tipo *"Super Mario"* donde un personaje salta, recoge monedas y evita enemigos.
* **Juego de disparos** donde una nave destruye enemigos mientras evita colisiones.
* **Juego de carreras** con coches moviéndose en una pista y cambiando de velocidad.
* **Puzzle** estilo *"Tetris"* o un juego de combinar piezas.
* **Aventuras gráficas** donde el jugador interactúa con personajes y objetos usando el ratón.

## 2. ¿Cómo instalarlo?

**Instalación para sistemas Windows**

1. Abre la consola (haz clic en el **menú de Inicio** y escribe **cmd**).
2. Escribe el siguiente comando para instalar Pygame Zero usando **`pip`**: 

```py
pip install pgzero
```

## 3. Estructura básica de un juego en Pygame Zero

¡Ha llegado el momento de ver cómo se crea un juego en Pygame Zero! Solo necesitas dos funciones básicas para empezar a crear un juego:

* `draw()`: esta función es obligatoria y se usa para dibujar todo lo que aparece en la pantalla (personajes, fondos, objetos, etc.). Se ejecuta cada vez que hay que volver a dibujar algo en la pantalla.
* `update()`: esta función se ejecuta constantemente y es donde controlamos la lógica del juego, como mover personajes o cambiar el estado del juego.

**Ejemplo básico: dibujar en la pantalla**

Vamos a crear un pequeño juego en el que simplemente dibujamos un círculo en la pantalla. Aquí tienes el código:

```py
# Importar la librería
import pgzrun

# Definir el tamaño de la ventana
WIDTH = 800
HEIGHT = 600

def draw():
    screen.clear()  # Limpiar la pantalla
    screen.draw.circle((400, 300), 30, 'white')  # Dibujar un círculo blanco

pgzrun.go()  # Iniciar el juego
```

* Lo primero que hay que hacer es **importar la librería de Pygame Zero**, de lo contrario no podremos usar sus funciones. 
* A continuación, de define el tamaño de la ventana del juego: **WIDTH** establece un ancho de 800 píxeles y **HEIGHT** establece la altura en 600 píxeles.
* Luego, se define la **función draw()**. Esta función es fundamental porque es la encargada de dibujar todo lo que aparece en la pantalla. Pygame Zero la llama cada vez que necesita actualizar lo que se muestra en el juego. Dentro de esta función, usamos las funciones de **screen** para dibujar los elementos gráficos.
* La primera línea dentro de la función es **screen.clear()**, que limpia la pantalla de cualquier dibujo anterior. Esto asegura que no queden "rastros" de lo que se dibujó previamente, dejando la pantalla lista para el siguiente dibujo.
* A continuación, se dibuja un círculo blanco en la pantalla. La función **screen.draw.circle()** toma como parámetros la posición del círculo, su tamaño y el color. En este caso, el círculo se dibuja en las coordenadas (400, 300), que están en el centro de la pantalla, con un radio de 30 píxeles, y el color es blanco.
* Finalmente, la función **pgzrun.go()** inicia el ciclo del juego. Esta función le dice a Pygame Zero que comience a ejecutar y mostrar el juego en la ventana. Sin esta línea, el juego no comenzaría, ya que es la que activa todo el proceso de dibujar y actualizar la pantalla.



