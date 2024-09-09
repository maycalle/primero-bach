# Tipos de datos y conversión

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

Cada tipo de dato tiene su función, y Python los maneja de manera distinta según lo que necesites hacer. Conocer qué tipo de dato estás utilizando es importante para evitar errores y asegurarte de que tu programa funcione correctamente. 

## 2. Funciones de conversión de tipos de datos

A veces, necesitarás convertir un tipo de dato en otro para realizar ciertas operaciones o para que el programa funcione correctamente. Por ejemplo, convertir un número en texto o al revés. Python tiene funciones integradas que facilitan estas conversiones: 

* **str(): convertir a cadena de texto**
La función `str()` convierte convierte cualquier dato (número, booleano, etc.) en una cadena de texto. Se suele utilizar para combinar texto con números en una operación de `print()`.

Ejemplo que da error
```py
edad = 17
print("Tengo " + edad + " años.")   # Esto dará error, porque Python no sabe cómo unir un texto con un entero
```
Ejemplo correcto
```py
edad = 17
print("Tengo " + str(edad) + " años.")  # OK, primero convierte el número en texto para imprimirlo
```

* **int(): convertir a número entero** 
La función `int()` convierte texto o números decimales en números enteros. Pero cuidado, si intentas convertir algo que no es un número en un entero, Python dará un error. Por ejemplo, int("Hola") dará un error.

Se suele utilizar cuando pedimos información al usuario de tipo numérico (edad, año, cantidad, etc) porque todo lo que el usuario introdce con `input()` se almacena como texto, sin importar si introduce números. Si intentas hacer operaciones matemáticas con ese texto, Python no sabrá cómo interpretarlo y lanzará un error.

Ejemplo que da error
```py
edad = input("¿Cuántos años tienes? ")
print("El año que viene tendrás " + (edad + 1) + " años.")      # Esto dará error, porque `edad` es texto.
```
Ejemplo correcto
```py
edad = int(input("¿Cuántos años tienes? "))
print("El año que viene tendrás " + str(edad + 1) + " años.")   # OK
```
En el ejemplo correcto, observa que: 
* Primero se convierte el texto introducido por el usuario a un número entero con `int()`, lo que permite realizar operaciones matemáticas.
* Luego se convierte el resultado de esa operación en texto con `str()` para poder combinarlo con otros fragmentos de texto en el mensaje final.

* **float(): convertir a número decimal** 
La función float() convierte texto o enteros en números con decimales. Muy útil para trabajar con medidas o cálculos científicos.

```py
altura = float(input("¿Cuál es tu altura en metros? "))
print("Tu altura es " + str(altura) + " metros.")
``` 

Con esta conversión, puedes se realizan cálculos con decimales sin perder precisión.

## Es tu turno

¡Ahora es tu momento de aplicar lo que has aprendido! Aquí tienes algunos ejercicios:

* 1. **Calculadora personalizada:** crea un programa que pida al usuario dos números y realice varias operaciones matemáticas con ellos (suma, resta, multiplicación y división).
* 
  


