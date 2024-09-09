# Tipos de datos y conversión

En esta sección vamos a conocer algunos de los **tipos de datos** que existen en Python, desde texto hasta números y valores lógicos. Además, aprenderemos cómo convertir estos datos de un tipo a otro según lo necesitemos. Al finalizar, serás capaz de escribir código más flexible y adaptado a distintas situaciones en el mundo real de la programación. ¡Vamos a ello!

## 1. Tipos de datos básicos

En Python, hay diferentes tipos de datos que puedes usar según lo que quieras almacenar. Vamos a ver los más comunes:

* **Cadenas de texto (strings):** se usan para almacenar palabras o frases. Se definen con comillas simples (' ') o dobles (" ").
    * Ejemplo: "Hola", 'Python es genial'

* **Números enteros (int):** Son números sin decimales, como edades, cantidades o años.
    * Ejemplo: edad = 17

* **Números decimales (float):** se usan cuando necesitas precisión. Por ejemplo,  para representar medidas o valores que incluyen decimales.
    * Ejemplo: altura = 1.75

* **Valores booleanos (bool):** solo pueden ser `True` *(verdadero)* o `False` *(falso)*. Estos son muy útiles para hacer decisiones en los programas.
    * Ejemplo: es_mayor_de_edad = True

## 2. Funciones de conversión de tipos de datos

A veces, necesitarás convertir un tipo de dato en otro para realizar ciertas operaciones o para que el programa funcione correctamente. Por ejemplo, convertir un número en texto o al revés. Python tiene funciones integradas que facilitan estas conversiones: 

* **str():** convierte un número (o cualquier cosa) en texto. Esto es útil cuando quieres combinar texto y números en un print():
  
```py
edad = 17
print("Tengo " + str(edad) + " años.")  # Convierte el número en texto para imprimirlo
```

* **int():** convierte texto o números decimales en números enteros. Útil cuando quieres tratar un valor como un número entero. Esto es especialmente útil cuando usas `input()`, porque lo que escriben los usuarios siempre es tratado como texto, aunque escriban números:

```py
edad = int(input("¿Cuántos años tienes? "))
print("El año que viene tendrás " + str(edad + 1) + " años.")
```

OJO: si intentas convertir algo que no es un número en un entero, Python dará un error. Por ejemplo, int("Hola") dará un error.

* **float():** convierte texto o enteros en números con decimales. Muy útil para trabajar con medidas o cálculos científicos.

```py
altura = float(input("¿Cuál es tu altura en metros? "))
print("Tu altura es " + str(altura) + " metros.")
``` 





