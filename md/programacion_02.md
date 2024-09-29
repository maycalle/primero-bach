# 2. Imprime, calcula y pregunta

En esta sesión vamos a aprender más detalles sobre el comando `print()`, exploraremos el arte ASCII, trabajaremos con operadores matemáticos y, lo más importante, ¡aprenderemos a interactuar con el usuario con `input()`! 

## 1. Más sobre print()

Ya sabes lo básico de `print()`, pero ahora vamos a ver algunos detalles importantes que te serán útiles en situaciones más complejas, como incluir apóstrofes, comillas y combinar diferentes mensajes en una sola línea.

### 1.1 Comillas simples vs comillas dobles

Python te permite usar tanto comillas simples (' ') como comillas dobles (" "), y aunque funcionan de forma similar, hay algunos detalles importantes que debes conocer.

* **Apóstrofes en el texto:** si el texto contiene un apóstrofe ('), y estás usando comillas simples, Python podría confundirse. En ese caso, usa comillas dobles:

    ```py
    print('I'm learning Python')    # ¡Error! Python se confunde con el apóstrofe
    print("I'm learning Python")    # OK, las comillas dobles nos salvan
    ```

* **Comillas dobles dentro del texto:** si quieres incluir comillas dobles en el texto, usa comillas simples para delimitarlo:

    ```py
    print('May dice que "Python es genial"')    # OK
    print("May dice que "Python es genial"")    # Error
    ```

* **Caracteres de escape:** si necesitas usar el mismo tipo de comillas tanto dentro como fuera del texto (por ejemplo, comillas dobles dentro de un texto delimitado por comillas dobles), puedes usar el carácter de escape (`\`) para decirle a Python que ignore la comilla y la trate como parte del texto:

    ```py
    print("May dice que \"Python es genial\"")  # Comillas dobles dentro del texto y delimitando la cadena, sin dramas
    ```

### 1.2 Combinando mensajes en `print()`

Cuando quieras mostrar más de un elemento en un solo ``print()`, tienes dos formas de hacerlo: usando comas o el operador `+`. Vamos a ver cómo funciona cada una.

1. **Usando comas**: es la forma más sencilla de combinar varios elementos en un `print()`. Cuando lo haces así, Python automáticamente añade un espacio entre cada elemento. Puedes combinar textos (cadenas de caracteres), números y variables sin ningún problema.

    ```py
    nombre = "May"
    edad = 45
    print("Hola,", nombre, ". Tienes", edad, "años.")
    ```

    Observa que Python ha puesto espacios entre los elementos automáticamente, sin que tengas que preocuparte por eso.

2. **Usando el operador `+`**: es otra manera de combinar textos en `print()`. Aquí es importante destacar que solo funciona con cadenas de texto, es decir, todos los elementos que quieras combinar deben ser texto (cadenas). Si estás trabajando con números o variables de otro tipo, deberás convertirlos a texto con la función `str()` (pero no te preocupes, esa parte la veremos más adelante).

    ```py
    nombre = "May"
    print("Hola, " + nombre + ". ¡Qué alegría verte!")
    ```

    Con el operador `+`, no se añaden espacios automáticamente, por lo que debes asegurarte de incluirlos en los lugares correctos dentro de las cadenas.

## 2. Arte ASCII

Vamos a ponernos creativos. El arte ASCII es una forma de hacer dibujos usando solo caracteres. No es exactamente como dibujar con un lápiz, pero te sorprendería lo que se puede lograr. 

Vamos a empezar con algo básico: un perro.

```py
print("o----'")
print(" ||||")
```

Ojo, si usas comillas simples en la primera línea, Python podría confundirse con el apóstrofe. Recuerda las reglas que acabamos de aprender.

**Multilínea con comillas triples**

Si quieres hacer algo más grande (¡o más artístico!), puedes usar comillas triples (''' o """) para escribir varias líneas en un solo `print()`.

```py
print('''
 /\_/\
(o . o)
 > ^ <
''')
```

**¡Felicidades, acabas de crear un gato con Python! 🐱**

## 3. Operaciones matemáticas

Python no solo sirve para hacer arte ASCII o mostrar mensajes; también es una calculadora superpoderosa. Vamos a repasar algunas operaciones matemáticas básicas:

* **Operaciones básicas:**
    * **Suma:** +
    * **Resta:** -
    * **Multiplicación:** *
    * **División:** / (división real) y // (división entera)
    * **Exponentes:** ** (por ejemplo, 2 ** 3 es 2 al cubo, o 8)
    * **Módulo (resto de una división):** % (ideal para saber si un número es par o impar)

Prueba esto:

```py
print(2 + 3 * 4)  # Resultado: 14, porque multiplica antes de sumar
```

**Precedencia de operadores**

Python sigue reglas de precedencia para las operaciones, lo que significa que algunas operaciones se hacen antes que otras. 

La regla general es seguir este orden: 
* **Paréntesis:** todo lo que esté dentro de paréntesis se evalúa primero.
* **Exponentes:** luego vienen los exponentes (por ejemplo, 2 ** 3).
* **Multiplicación, División, y Módulo:** se resuelven de izquierda a derecha.
* **Suma y Resta:** se evalúan de izquierda a derecha.

Si quieres cambiar el orden de las operaciones, usa paréntesis.

```py
print(2 + 3 * 4)  # Resultado: 14 (primero se multiplica 3 * 4, luego se suma 2)
print((2 + 3) * 4)  # Resultado: 20 (los paréntesis cambian el orden de evaluación)
```

¡Experimenta con tus propios cálculos y verás cómo cambia el resultado dependiendo del orden!

**Desafío: calcular con texto**

Ahora que dominas las operaciones matemáticas, te lanzo un reto un poco diferente. ¡¿Sabías que Python también puede hacer "cálculos" con texto?! Puedes usar el operador `+` para concatenar cadenas (juntar textos), y el operador `*` para repetir cadenas.

Pruena el siguiente ejemplo: 

```py
print('ja ' * 4)
print('ba' + 'na' * 2)
print('¡ * 5' + 'Hola' + '!*5')
```

¿Eres capaz de inventarte palabras? ¡Puedes incluso crear tus propios patrones!

```py
print('/\ ' * 10)
print('  \/' * 10)
```

## 4. Uso de variables

En Python, una variable es como una "caja" donde puedes guardar un valor, y luego usar ese valor cuando lo necesites.

* **Declarar una variable:** para crear una variable, simplemente le das un nombre y le asignas un valor con el signo igual (=). Por ejemplo:

    ```py
    nombre = "May"
    edad = 45
    ```

* **Usar de una variable:** después de asignar un valor a una variable, puedes usarla en cualquier parte de tu programa. Prueba el siguiente código y observa el resultado obtenido:

    ```py
    nombre = "May"
    print("Hola, " + nombre) 
    ```

* **Cambiar el valor de una variable:** las variables pueden cambiar de valor en cualquier momento. Puedes hacer algo como esto:

    ```py
    edad = 45
    edad = edad + 1       # Actualiza la variable edad sumándole 1.    
    ```

* **Sobre los nombres de las variables**: a la hora de asignar un nombre a una variable, hay que seguir estas reglas:

    * **Caracteres permitidos:**
        * Letras (mayúsculas y minúsculas)
        * Dígitos
        * Subrayado 
        * No pueden empezar por un dígito

    * **Nombres compuestos:** puedes separar las palabras usando:
        * Subrayado → estilo más común en Python.
        * camelCase → primera palabra en minúsculas y las siguientes con mayúscula.
  
    * **Diferencia entre mayúsculas y minúsculas:** Python distingue entre mayúsculas y minúsculas. Por ejemplo, las variables `apellido`, `Apellido` y `APELLIDO` se consideran diferentes entre sí.

    ```py
    # Ejemplos de nombres válidos
    numero = 12
    numero_cuenta_bancaria = 'ES1100001111222233334444'
    loginUsuario = 'may'
    numero2 = 22
    
    # Ejemplos de nombres incorrectos
    2numero = 12 
    numero-cuenta = 'ES1100001111222233334444' 
    login usuario = 'may'  
    print = 3
    ```

## 6. Interacción con el usuario: input()

Hasta ahora, tú eras quien le daba las órdenes a Python, pero ¿qué tal si hacemos que el programa pregunte algo al usuario? Aquí entra en juego `input()`. 

Básicamente, lo que hace es esperar pacientemente a que el usuario escriba algo y presione **Enter**. Una vez que lo hace, el contenido que ha escrito se captura como texto (¡siempre como texto!).

* **Uso básico de input():**
  
    ```py
    nombre = input("¿Cómo te llamas? ")
    print("¡Hola, " + nombre + "!")
    ```

¡Ahora tu programa puede saludar a cualquiera que lo use! 😄

## 7. Es tu turno 

Ahora que ya sabes más sobre `print()`, arte ASCII, operaciones matemáticas e interacción con el usuario, ¡es tu momento de crear! Aquí tienes algunas ideas para que experimentes:

* **Crea tu propio arte ASCII:** diseña una figura usando caracteres ASCII. ¿Podrías hacer un coche, un cohete o un animal? ¡Imaginación al poder!
* **Un programa sobre ti:** haz que tu programa le pregunte al usuario algunos datos personales, como su nombre, dirección y número de teléfono, y luego muestre toda esa información en pantalla.
* **Dime tu animal favorito:** escribe un programa que le pregunte al usuario cuál es su animal favorito. Luego, responde con un mensaje personalizado. 
  Por ejemplo, si el usuario te ha contestado que su animal favorito son los *gatos*, puedes mostrar un mensaje similar a este: "Me gustan los *gatos*, pero mi animal favorito es el perro" 




