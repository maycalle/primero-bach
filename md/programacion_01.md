# 1. Primeros pasos con Python

¡Bienvenidos al emocionante mundo de Python! Un lenguaje de programación que no solo es fácil de aprender, sino que también es súper versátil. ¿Listos para empezar a programar? 

## 1. ¿Qué es Python?

Imagina un idioma que puedes aprender rápidamente y te permite hacer casi de todo: eso es Python. Es uno de los lenguajes de programación más populares en la actualidad, y por una buena razón: es sencillo pero potente. ¡Vamos a ver algunas de las cosas que puedes hacer con él!

* **Desarrollo de Videojuegos:** ¿Te gustan los videojuegos? ¡Con Python puedes crear los tuyos! Bibliotecas como Pygame te permiten diseñar gráficos, mover personajes y programar toda la acción. 

* **Aplicaciones Web:** ¿Te gustaría construir tu propia página web o una app que todos usen? Frameworks como Django y Flask son herramientas basadas en Python que te ayudarán a crear aplicaciones web de manera rápida y eficiente. 

* **Ciencia de Datos y Análisis:** ¿Sabías que Python es la herramienta favorita de los científicos de datos? Con Pandas y Matplotlib puedes analizar montañas de datos, hacer gráficos impresionantes y descubrir patrones inesperados.

* **Inteligencia Artificial y Machine Learning:** Python también es el lenguaje estrella en el mundo de la inteligencia artificial. Usando bibliotecas como TensorFlow y Scikit-Learn, puedes construir modelos que aprenden y hacen predicciones. ¡Casi como darle vida a una máquina!

## 2. ¿Cómo instalarlo?

Ahora que ya sabemos para qué podemos usar Python, ¡vamos a instalarlo! Verás que es más fácil que instalar la última actualización de un videojuego.

**Instalación en los ordenadores de clase**

1. Enciende el ordenador y accede al sistema operativo Windows.
2. Inicia sesión con tu **identidad digital**.
3. Busca el icono de la **Botiga d'Aplicacions** en el escritorio. Si no lo encuentras, usa la barra de búsqueda.
4. En la *Botiga d'Aplicacions*, busca Python. ¡Lo encontrarás fácil!
5. Haz clic en **Instalar** y espera pacientemente (puedes tomarte un respiro, pero no te vayas muy lejos).
6. Cuando todo haya terminado, recibirás una notificación confirmando la instalación.

**Instalación en casa (para sistemas Windows)**

1. Ve a la [página oficial de Python](https://www.python.org/downloads/) y descarga la última versión.

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/instalacion_python.png" width="40%">
</div>

2. Haz clic en **Install now**, pero **OJO**: marca la casilla que dice **Add python.exe to PATH**. Esto es muy importante, porque así podrás usar Python desde cualquier parte del sistema.

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/instalacion_python2.png" width="40%">
</div>

3. Cuando la instalación termine, verás una pantalla de confirmación (¡y sentirás que ya eres casi un hacker!)
  
<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/instalacion_python3.png" width="40%">
</div>


## 3. ¿Cómo probarlo?

Ahora que ya tienes Python instalado, vamos a asegurarnos de que todo está funcionando como debe. Aquí te explico cómo verificar que Python esté bien instalado:

1. Haz clic en el botón de **Inicio** (es el logo de Windows, en la esquina inferior izquierda de la pantalla).
2. Escribe **cmd** o **Símbolo del sistema** en la barra de búsqueda. 
3. Haz clic en **Abrir** para lanzar el terminal o pulsa **Enter** (la pantalla negra da algo de respeto, pero es súper útil)

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/terminal_comandos_windows.png" width="50%">
</div>

4. Una vez dentro, escribe uno de estos comandos: 
      * python -V       
      * python --version


5. Si todo ha ido bien, verás un número en pantalla que indica la versión de Python que acabas de instalar. 

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/version_python_instalada.png" width="35%">
</div>

**¡Felicidades, ya tienes Python listo para usar!**

## 4. ¿Cómo programar en Python?

¡Ahora que ya tenemos Python instalado, es hora de empezar a escribir nuestras primeras líneas de código! Pero para hacerlo de forma cómoda y eficiente, necesitamos un **IDE (Entorno de Desarrollo Integrado)**, que es básicamente un programa que hace que programar sea mucho más fácil y organizado.

Para nuestro caso, vamos a usar **Visual Studio Code** (VSCode, para los amigos 😎), y lo elegimos porque es:

* Gratuito (¡y a quién no le gusta lo gratis!).
* Open Source (el código está abierto para que cualquiera lo vea y lo mejore).
* Superpersonalizable (puedes añadirle un montón de extensiones para adaptarlo a lo que necesites).

**Instalación en los ordenadores de clase**

1. Enciende el ordenador y accede al sistema operativo Windows.
2. Inicia sesión con tu **identidad digital**.
3. Busca el icono de la **Botiga d'Aplicacions** en el escritorio. Si no lo encuentras, ¡tranquilidad! Usa la barra de búsqueda.
4. Dentro de la *Botiga d'Aplicacions*, busca Visual Studio Code (no te confundas con otros, este es el bueno). 
5. Haz clic en **Instalar** y relájate un momento mientras se descarga.
6. Cuando todo haya terminado, recibirás una notificación de que ya está listo para usarse. 

**Instalación en casa (para sistemas Windows)** 

Si estás en casa, instalar **VSCode** también es muy sencillo. Solo sigue estos pasos:

1. Ve a la web oficial de [Visual Studio Code](https://code.visualstudio.com/) y descarga la última versión (¡que siempre es la mejor!).

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/instalacion_vscode.png" width="50%">
</div>

2. Abre el archivo descargado y sigue los pasos del instalador. En unos minutos tendrás todo listo para empezar a programar.

**Configurando Visual Studio Code para Python**

Aunque ya tengas Python y VSCode listos, ¡aún nos falta un detalle!. Para que programar sea más sencillo y cómodo, necesitamos instalar la **extensión de Python** en nuestro IDE. Con esta maravilla, podrás escribir, ejecutar y depurar tus programas sin sudar la gota gorda.

Para instalarla, sigue este [enlace](https://marketplace.visualstudio.com/items?itemName=ms-python.python) ¡Es tan fácil como hacer clic en **Install**!

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/instalacion_extension_python.png" width="50%">
</div>

Durante el proceso de instalación, VSCode te pedirá permiso para abrirse. Aparecerá una pestaña con toda la info sobre la extensión. Lo único que tienes que hacer es volver a pulsar **Install**, y la instalación comenzará automáticamente. 

¡Y listo! Ahora tu Visual Studio Code estará preparado para trabajar con Python como un campeón.

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/instalacion_extension_python2.png" width="50%">
</div>

**¿Y si quiero probar algo rápido sin instalar nada?**

No siempre tienes que instalar un programa completo para probar un par de líneas de código. Si solo quieres hacer una prueba rápida, ¡existen opciones online! 

Uno de los mejores editores en línea para Python es **[Programiz](https://www.programiz.com/python-programming/online-compiler/)**. Solo tienes que abrirlo, escribir tu código, y hacer clic en ejecutar. ¡Es como programar en cualquier parte, sin complicaciones!

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/inicio_programiz.png" width="60%">
</div>

## 5. Nuestro primer programa

¡Ha llegado el momento de la verdad! Ahora que ya tenemos todo configurado, es hora de ponernos manos a la obra y escribir nuestro primer programa en Python 🚀.

Lo primero que necesitas es **crear una carpeta** donde vas a guardar todos tus archivos Python. Este será tu espacio de trabajo, ¡el lugar donde ocurrirá toda la magia! ✨

Una vez que tengas esa carpeta lista, **abre VSCode** y sigue estos pasos súper sencillos:
1. Ve al menú **Archivo > Abrir carpeta** o, si tienes tu VSCode en inglés, **File > Open Folder**.
2. Selecciona la carpeta que acabas de crear.
3. ¡Y voilá! Ahora esa carpeta aparecerá en el panel izquierdo del explorador de archivos de VSCode. Desde allí, puedes empezar a crear todos los archivos y carpetas que necesites. ¡Es como tu cuaderno, pero lleno de código!
4. Crea un archivo Python llamado, por ejemplo, `holamundo.py`. 

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/crear_fichero_vscode.png" width="50%">
</div>

5. Escribe este código dentro del archivo recién creado: `print("Hola")` y guarda el archivo.

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/primer_programa_python.png" width="50%">
</div>
 
6. Ahora, ¡vamos a ejecutarlo y ver el resultado en acción!. Haz clic derecho sobre tu código y elige **Run Python > Run Python File in Terminal**. ¡Y listo! ¡Tu pantalla te saludará con un gran "Hola"! 🎉

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/ejecucion_hola_mundo.png" width="50%">
</div>

Si cometes un error, recibirás un mensaje de error indicándote lo qué salió mal !Pruébalo! Borra la última comilla `"` o el último paréntesis `)` (o ambos) y comprueba lo que pasa. Después vuelve a escribir la comilla o el paréntesis, y haz clic en **Run** para asegurarte de que el proyecto vuelve a funcionar correctamente.

## 6. Poner comentarios

Los **comentarios** son notas aclaratorias o explicativas que escribes en el código pero que Python ignora cuando ejecuta el programa. Son muy útiles porque te ayudan a organizar tu código, hacer anotaciones para ti mismo o explicar qué hace una parte del programa. Es como cuando en clase tomas notas en los márgenes de tus apuntes, ¡pero en código!

Para crear un comentario de una sola línea en Python, simplemente utiliza el símbolo `#`. Todo lo que escribas después de # será ignorado.

```py
# Este es un comentario, Python lo ignorará al ejecutar el programa
print("Hola")  # Esto imprimirá el saludo "Hola" en la pantalla
```

```py
# Puedes hacer operaciones matemáticas
print(10 + 5)  # Esto imprimirá 15
```

En estos ejemplos, los comentarios `# Este es un comentario` y `# Puedes hacer operaciones matemáticas` no afecta al funcionamiento del programa. Lo mismo ocurre con el comentario añadido al final de las líneas donde usamos `print()`.

## 7. Es tu turno

¡Es tu turno de modificar el código y experimentar con `print()`! Aquí tienes algunas ideas para empezar:

1. **Añadir más texto:** modifica el código para que imprima varias frases seguidas.
2. **Imprimir números:** Python también permite imprimir números. Sin embargo, hay una diferencia importante: los números no necesitan comillas. Prueba a añadir líneas que muestren algunos números o hagan operaciones matemáticas, como 10 + 5. Si pones comillas, Python tratará el número como texto, pero sin comillas lo verá como un valor numérico. ¡Haz la prueba y verás la diferencia!   
3. **Habla sobre ti:** escribe un programa que cuente algo sobre ti. Combina texto y números; por ejemplo, usa una operación matemática para calcular tu edad: 2024 - tu_año_nacimiento. ¡Python te ayudará a sacar las cuentas!