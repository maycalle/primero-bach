# Primeros pasos con Python

¡Bienvenidos al emocionante mundo de Python! Un lenguaje de programación que no solo es fácil de aprender, sino que también es increíblemente versátil. ¿Listos para empezar a programar? 

## 1. ¿Qué es Python?

Imagina un idioma que puedes aprender rápidamente y te permite hacer casi de todo: eso es Python. Es uno de los lenguajes de programación más populares en la actualidad, y por una buena razón: es sencillo pero potente. ¡Vamos a ver algunas de las cosas que puedes hacer con él!

* **Desarrollo de Videojuegos:** ¿Te gustan los videojuegos? ¡Con Python puedes crear los tuyos! Bibliotecas como Pygame te permiten diseñar gráficos, mover personajes y programar toda la acción. 

* **Aplicaciones Web:** ¿Te gustaría construir tu propia página web o una app que todos usen? Frameworks como Django y Flask son herramientas basadas en Python que te ayudarán a crear aplicaciones web de manera rápida y eficiente. 

* **Ciencia de Datos y Análisis:** ¿Sabías que Python es la herramienta favorita de los científicos de datos? Con Pandas y Matplotlib puedes analizar montañas de datos, hacer gráficos impresionantes y descubrir patrones inesperados.

* **Inteligencia Artificial y Machine Learning:** Python también es el lenguaje estrella en el mundo de la inteligencia artificial. Usando bibliotecas como TensorFlow y Scikit-Learn, puedes construir modelos que aprenden y hacen predicciones. ¡Casi como darle vida a una máquina!

## 2. ¿Cómo instalarlo?

Ahora que ya sabemos para qué podemos usar Python, ¡vamos a instalarlo! Te aseguro que es más fácil que instalar la última actualización de un videojuego.

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
6. Cuando todo haya terminado, recibirás una notificación de que ya está listo para usarse. ¡Vamoooos!

**Instalación en casa (para sistemas Windows)** 

Si estás en casa, instalar **VSCode** también es muy sencillo. Solo sigue estos pasos:

1. Ve a la web oficial de [Visual Studio Code](https://code.visualstudio.com/) y descarga la última versión (¡que siempre es la mejor!).

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/instalacion_vscode.png" width="50%">
</div>

2. Abre el archivo descargado y sigue los pasos del instalador. En unos minutos tendrás todo listo para empezar a programar.

**Configurando Visual Studio Code para Python**

Ya tenemos Visual Studio Code instalado, ¡genial! Pero todavía nos falta un pequeño detalle: preparar el entorno para trabajar con Python. Esto es como configurar tu espacio de trabajo para que todo esté ordenado y funcione sin problemas.

1. **Instala la extensión de Python**: aunque ya tienes Python y VSCode, instalar la extensión de Python hará que todo sea aún más fácil. Con esta extensión, podrás escribir, ejecutar y depurar programas de una manera más sencilla. Para instalarla, simplemente sigue este [enlace](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

<div style="margin-bottom: 10px" align="center">
    <img style="border: 1px solid black" src="/primero-bach/img/instalacion_extension_python.png" width="50%">
</div>

2. **En VSCode, debes abrir la carpeta donde quieras trabajar**. Ve al menú **Archivo > Abrir carpeta**, elige la carpeta donde vas a crear tus archivos Python y ¡listo! Puedes empezar a trabajar desde el panel izquierdo del explorador, donde puedes crear todos los archivos y carpetas que necesites.
      


**¿Y si quiero probar algo rápido sin instalar nada?**

No siempre tienes que instalar un programa completo para probar un par de líneas de código. Si solo quieres hacer una prueba rápida, ¡existen opciones online! 

Uno de los mejores editores en línea para Python es **[Programiz]**(https://www.programiz.com/python-programming/online-compiler/). Solo tienes que abrirlo, escribir tu código, y hacer clic en ejecutar. ¡Es como programar en cualquier parte, sin complicaciones!

## 5. Nuestro primer programa

## 6. Es tu turno







