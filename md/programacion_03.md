# 

## 1. Tipos de datos básicos

* **Cadenas de texto (strings):** son secuencias de caracteres, como palabras o frases. Se definen usando comillas simples (' ') o dobles (" ").
    * Ejemplo: "Hola", 'Python es genial'

* **Números enteros (int):** son números sin decimales, como el 3 o el 2024.
    * Ejemplo: edad = 17

* **Números decimales (float):** son números con decimales. Se usan cuando necesitas más precisión, como en notas o cálculos científicos.
    * Ejemplo: altura = 1.75

* **Valores booleanos (bool):** son valores que solo pueden ser `True` o `False`. Son muy útiles cuando se trata de decisiones y condiciones.
    * Ejemplo: es_mayor = True

## 2. Funciones de conversión de tipos de datos

A veces, querrás convertir datos de un tipo a otro. Por ejemplo, convertir un número en texto o al revés. Aquí es donde entran funciones como `str()`, `int()` y `float()`:

* **str():** convierte un número (o cualquier cosa) en texto. Esto es útil cuando quieres combinar texto y números en un print():
  
```py
edad = 17
print("Tengo " + str(edad) + " años.")  # Convierte el número en texto para imprimirlo
```

* **int():** convierte texto o decimales en números enteros. Esto es especialmente útil cuando usas `input()`, porque lo que escriben los usuarios siempre es tratado como texto, aunque escriban números:

```py
edad = int(input("¿Cuántos años tienes? "))
print("El año que viene tendrás " + str(edad + 1) + " años.")
```

* **float():** convierte texto o enteros en números con decimales. Útil cuando trabajas con medidas o cálculos más precisos:

```py
altura = float(input("¿Cuál es tu altura en metros? "))
print("Tu altura es " + str(altura) + " metros.")
``` 




