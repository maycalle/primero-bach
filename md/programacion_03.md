# 3. Tipos de Datos, Conversión y Formato

En esta sección vamos a conocer algunos de los **tipos de datos** que existen en Python, desde texto hasta números y valores lógicos. También aprenderemos a convertir entre estos tipos de datos cuando lo necesitemos. Al finalizar, serás capaz de escribir código más flexible y adaptado a distintas situaciones en el mundo real de la programación. ¡Vamos a ello!

## 1. Tipos de datos básicos

En Python, hay diferentes tipos de datos que puedes usar según lo que necesites almacenar. Los más comunes son:

* **Cadenas de texto (strings):** se usan para almacenar palabras o frases. Se definen con comillas simples (' ') o dobles (" ").
  
    * Ejemplo: "Hola", 'Python es genial'

* **Números enteros (int):** Son números sin decimales, como edades, cantidades o años.
  
    * Ejemplo: edad = 17

* **Números decimales (float):** se usan cuando necesitas precisión. Por ejemplo,  para representar medidas o valores que incluyen decimales.
  
    * Ejemplo: altura = 1.75

* **Valores booleanos (bool):** solo pueden ser `True` *(verdadero)* o `False` *(falso)*. Estos son muy útiles para hacer decisiones en los programas.
  
    * Ejemplo: es_mayor_de_edad = True

Cada tipo de dato tiene su función, y Python los maneja de manera distinta según lo que necesites hacer. Saber qué tipo de dato estás utilizando es importante para evitar errores y asegurarte de que tu programa funcione correctamente. 

## 2. Usando f-string

El nombre **"f-string"** viene de *"formatted string"* (cadena formateada), y su principal ventaja es que te permite combinar texto y variables de forma clara y legible.

Para **crear una f-string**, simplemente antepon una **f** al texto que quieras mostrar. Luego, inserta donde lo necesites (pero siempre dentro de la cadena de texto) cualquier variable o expresión que quieras que se incluya o evalúe dentro de unas llaves **{}**. Python reemplaza las llaves **{}** por el valor de las variables o expresiones que se encuentran dentro, generando un texto formateado de forma automática.

```py
nombre = "May"
edad = 45
print(f"Hola, {nombre}. Tienes {edad} años.")
```

Puedes **usar las f-strings para para formatear números**, como mostrar decimales con un número determinado de decimales.

```py
pi = 3.1415926535
print(f"El valor de pi es {pi:.2f}.")
```

Observa que **.2f** indica que quieres mostrar el valor de **pi** con 2 decimales.

## 3. Funciones de conversión de tipos de datos

A veces, necesitarás convertir un tipo de dato en otro para realizar ciertas operaciones o para que el programa funcione correctamente. Por ejemplo, convertir un número en texto o al revés. Python tiene funciones integradas que facilitan estas conversiones: 

* **str(): convertir a cadena de texto**
  
    La función `str()` convierte convierte cualquier dato (número, booleano, etc.) en una cadena de texto. Se suele utilizar para combinar texto con números en una operación de `print()`.

    *Ejemplo que da error*

    ```py
    edad = 17
    print("Tengo " + edad + " años.")   # Esto dará error, porque Python no sabe cómo unir un texto con un entero
    ```

    *Ejemplo correcto*

    ```py
    edad = 17
    print("Tengo " + str(edad) + " años.")  # OK, primero convierte el número en texto para imprimirlo
    ```

* **int(): convertir a número entero** 

    La función `int()` convierte texto o números decimales en números enteros. Pero cuidado, si intentas convertir algo que no es un número en un entero, Python dará un error. Por ejemplo, `int("Hola")` dará un error. 

    Se suele utilizar cuando pedimos información al usuario de tipo numérico (edad, año, cantidad, etc) porque todo lo que el usuario introdce con `input()` se almacena como texto, sin importar si introduce números. Si intentas hacer operaciones matemáticas con ese texto, Python no sabrá cómo interpretarlo y lanzará un error.

    *Ejemplo que da error*
    
    ```py
    edad = input("¿Cuántos años tienes? ")
    print("El año que viene tendrás " + (edad + 1) + " años.")      # Esto dará error, porque `edad` es texto.
    ```
    *Ejemplo correcto*

    ```py
    edad = int(input("¿Cuántos años tienes? "))
    print("El año que viene tendrás " + str(edad + 1) + " años.")   # OK
    ```
    
    En el ejemplo correcto, observa que: 
    * Primero se convierte el texto introducido por el usuario a un número entero con `int()`, lo que permite realizar operaciones matemáticas.
    * Luego se convierte el resultado de esa operación en texto con `str()` para poder combinarlo con otros fragmentos de texto en el mensaje final.

* **float(): convertir a número decimal** 

    La función `float()` convierte texto o enteros en números con decimales. Muy útil para trabajar con medidas o cálculos científicos.

    ```py
    altura = float(input("¿Cuál es tu altura en metros? "))
    print("Tu altura es " + str(altura) + " metros.")
    ``` 

    Con esta conversión, se realizan cálculos con decimales sin perder precisión.

## 4. Es tu turno

¡Ahora es tu momento de aplicar lo que has aprendido! Aquí tienes algunos ejercicios:

1. **El amplificador de mensajes**. Un streamer quiere un comando para su chat que repita un grito de ánimo varias veces. 

    - Pide al usuario que introduzca una palabra o grito (ej. "¡Gol! ") y el número de veces que quiere repetirlo. 
    - Convierte la cantidad al tipo de dato adecuado y muestra en pantalla la repetición usando el operador * y una f-string.

2. **Tu contador de días**. Crea un programa que calcule aproximadamente cuántos días lleva en el mundo una persona.

    - Pide al usuario su nombre y su edad actual en años cumplidos (número entero).
    - Calcula cuántos días ha vivido aproximadamente (asume 365 días por año).
    - Muestra un mensaje personalizado usando f-strings con el siguiente formato: Hola, [Nombre]. Has vivido aproximadamente [Días] días.

3. **Viaje a EEUU: el termómetro digital**. Aterrizas en Nueva York y los paneles de la calle muestran la temperatura en grados Fahrenheit, pero necesitas saber qué ropa ponerte. 

    - Pide la temperatura actual en grados Fahrenheit (debe admitir decimales con float()).
    - Conviértela a grados Celsius mediante la fórmula: Celsius = (Fahrenheit - 32) * 5/9
    - Muestra el resultado por pantalla con exactamente 1 cifra decimal usando el especificador de formato :.1f

4. **La cena con amigos**. Un grupo de 4 amigos va a cenar a una pizzería y deciden pagar la cuenta a partes iguales.

    - Pide por teclado el importe total de la cuenta en euros (número con decimales) y el porcentaje de propina que desean dejar (por ejemplo, 10 para un 10%).
    - Calcula el total a pagar sumando la propina y divídelo entre los 4 comensales.
    - Imprime cuánto debe poner cada persona, asegurándote de mostrar el resultado con 2 cifras decimales:.2f

5. **El relojero digital**. En programación de videojuegos es habitual recibir duraciones expresadas solo en segundos y tener que transformarlas a un formato comprensible para el jugador.

    - Pide al usuario una cantidad total de segundos (número entero, ej. 195).
    - Utiliza la división entera (//) para calcular cuántos minutos completos contiene ese tiempo.
    - Utiliza el operador módulo/resto (%) para calcular los segundos sobrantes.
    - Muestra el resultado formateado: `195 segundos equivalen a 3 minutos y 15 segundos.`

6. **El boletín de notas**. Un tutor necesita una pequeña herramienta para calcular la nota media exacta de un alumno en cuatro materias clave: Matemáticas, Lengua, Inglés y Tecnología.

    - Pide por teclado: el nombre y apellidos del alumno.
    - La calificación de cada una de las 4 asignaturas por separado (deben admitir decimales con float()).
    - El programa debe calcular la media aritmética de las cuatro notas.
    - Muestra por pantalla un informe claro y ordenado usando f-strings, mostrando cada nota individual y la nota media final calculada con 3 cifras decimales(.3f)

Por ejemplo, genera una salida como esta: 

```txt
    --- INFORME ACADÉMICO ---
    Alumno: Laura Navarro Martínez
    Matemáticas: 8.5
    Lengua: 7.25
    Inglés: 9.0
    Tecnología: 6.8
    ------------------------
    Nota media final: 7.888
    ------------------------
```