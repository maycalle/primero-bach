# 7. Más sobre cadenas de texto 

## 1. Operaciones básicas

Ya hemos visto en apartados anteriores que Python permite manejar cadenas de texto utilizando indistintamente comillas simples o dobles. Podemos crearlas con un texto predefinido en el programa, o pedirlas al usuario a través de la instrucción input:

```py
texto = "Hola"
texto2 = 'Buenas' 
texto3 = input("Dime tu nombre: ")
```

Además, también hemos visto las siguientes operaciones básicas:

* **Concatenación:** unimos cadenas con el operador `+`

```py
nombre = "May"
texto = "Hola, " + nombre  # Hola, May
```

* **Conversión a cadena:** convertimos cualquier dato a cadena con `str()`

```py
edad = 17
texto = "Tengo " + str(edad) + " años"
```

* **Repetir cadenas:** repetimos una cadena usando `*`:

```py
texto = "Hola" * 3  # HolaHolaHola
```

A estas operaciones básicas ya conocidas, podemos añadir la siguiente: 

* **Índices y longitud:** podemos acceder a un carácter concreto con corchetes `[]` y conocer la longitud de la cadena con `len()`:

```py
texto = "Hola"
print(texto[0])  # H
print(len(texto))  # 4
```

## 2. Operaciones avanzadas

* **Dividir cadenas:** usamos `split()` para separar una cadena en una lista de palabras, usando un delimitador:

```py
texto = "Uno,Dos,Tres"
partes = texto.split(",")  # ["Uno", "Dos", "Tres"]
```

* **Unir listas en cadenas:** Con `join()`, podemos unir elementos de una lista en una cadena, separándolos con un delimitador:

```py
partes = ["Uno", "Dos", "Tres"]
texto = ','.join(partes)  # Uno,Dos,Tres
```

* **Reemplazar texto:** replace() sustituye una parte de la cadena por otro texto:

```py
texto = "Java es el mejor lenguaje"
texto2 = texto.replace("Java", "Python")  # Python es el mejor lenguaje
```

* **Convertir mayúsculas/minúsculas:** Usamos `lower()` y `upper()` para convertir texto a minúsculas o mayúsculas:

```py
texto = "Hola, buenas"
texto_mayus = texto.upper()  # HOLA, BUENAS
```

* **Buscar en cadenas:** Con `find()`, encontramos la posición de una subcadena, y con `in` verificamos si una palabra está presente:

```py
texto = "Hola, buenas"
posicion = texto.find("buenas")  # 6
if "buenas" in texto:
    print("El texto contiene 'buenas'")
```

* **Subcadenas:** Para extraer una parte de la cadena, usamos el formato cadena[inicio:fin]:

```py
texto = "Hola, buenas tardes"
subcadena = texto[6:12]  # buenas
subcadena2 = texto[6:]   # buenas tardes
```

* **Comparar cadenas:** Usamos operadores de comparación (<, >, ==) para comparar alfabéticamente:

```py
texto1 = "Hola"
texto2 = "buenas"
if texto1 < texto2:
    print('"Hola" es menor que "buenas"')
```

* **Eliminar espacios:** `strip()` elimina espacios al inicio y al final de una cadena. También están `lstrip()` y `rstrip()` para limpiar solo a la izquierda o derecha:

```py
texto = "\tHola   "
texto_limpio = texto.strip()  # "Hola"
```

## 3. Es tu turno

* 1. Escribe un programa llamado **caracteres.py** que:
      * Pida al usuario que introduzca una palabra.
      * Muestre el primer y el último carácter de la palabra.
      * Muestre también la longitud de la palabra.

* 2. Escribe un programa llamado **dividir_cadena.py** que:
      * Pida al usuario que introduzca una frase con varias palabras separadas por comas.
      * Divida la frase en una lista de palabras y muestre la lista por pantalla.

    ```py
    Introduce una frase separada por comas: manzana,pera,plátano
    ['manzana', 'pera', 'plátano']
    ``` 

* 3. Escribe un programa llamado **unir_palabras.py** que:
      * Tenga una lista predefinida con 5 palabras.
      * Una las palabras de la lista en una cadena, separadas por guiones, y muestre la cadena resultante.

    ```py
    Lista de palabras: ['gato', 'perro', 'pájaro', 'ratón', 'pez']
    Cadena resultante: gato-perro-pájaro-ratón-pez
    ```
* 4. Escribe un programa llamado **reemplazar.py** que:
     * Pida al usuario una frase con las palabras "bueno" y "malo"
     * Reemplace todas las ocurrencias de la palabra "malo" por "bueno" y muestre el resultado.

* 5. Escribe un programa llamado **mayus_minus.py** que:
      * Pida al usuario una frase.
      * Muestre la frase convertida completamente en mayúsculas y en minúsculas.

* 6. Escribe un programa llamado **buscar_palabra.py** que:
     * Pida al usuario una frase.
     * Pida al usuario una palabra para buscar en la frase.
     * Muestra si la palabra está presente en la frase, y si es así, la posición donde comienza.

    ```py
    Introduce una frase: Me gusta programar en Python
    Introduce una palabra para buscar: Python
    La palabra 'Python' está en la frase en la posición 23
    ```
* 7. Escribe un programa llamado **extraer_subcadena.py** que:
     * Pida al usuario que introduzca una frase.
     * Pida dos posiciones (inicio y fin) para extraer una subcadena.
     * Muestra la subcadena resultante.

    ```py
    Introduce una frase: Estoy aprendiendo Python
    Introduce la posición inicial: 6
    Introduce la posición final: 16
    La subcadena es: aprendiendo
    ```
* 8. Escribe un programa llamado **comparar_cadenas.py** que:
     * Pida al usuario que introduzca dos palabras.
     * Compare las palabras alfabéticamente y diga cuál es mayor, menor o si son iguales.

* 9. Escribe un programa llamado **palindromo.py** que pida al usuario una palabra y muestre por pantalla si es un palíndromo. Un **palíndromo** es una palabra que se lee igual de izquierda a derecha que de derecha a izquierda. Es decir, si la palabra se invierte, sigue siendo la misma. Por ejemplo: radar, oso, etc

Si has terminado todos los ejercicios, puedes continuar con más **retos** en la [**web kattis**](https://open.kattis.com/)