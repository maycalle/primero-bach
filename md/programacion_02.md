# Imprime, calcula y pregunta

En esta sesión vamos a aprender más detalles sobre el comando `print()`, exploraremos el arte ASCII (sí, ¡dibujos con caracteres!), trabajaremos con operadores matemáticos y, lo más importante, ¡aprender a interactuar con el usuario con `input()`! 

## 1. Más sobre print()

Ya sabes cómo usar `print()` para mostrar mensajes en pantalla, pero ahora vamos a aprender cómo manejar situaciones un poco más complejas, como incluir apóstrofes o comillas dentro del texto. 

Python te permite usar tanto comillas simples (' ') como comillas dobles (" "), y aunque funcionan de forma similar, hay algunos detalles importantes que debes conocer.

* **Comillas simples vs. comillas dobles:** Puedes usar cualquiera de las dos para mostrar texto, pero si dentro de tu texto tienes un apóstrofe, ¡atención! Python podría confundirse si usas comillas simples:

```py
print('I'm learning Python')    # ¡Error! Python se confunde con el apóstrofe
```

```py
print("I'm learning Python")    # OK, las comillas dobles nos salvan
```

Como ves, cuando hay un apóstrofe, es mejor usar comillas dobles para que Python no se líe.

* **Comillas dobles dentro del texto:** si tu texto incluye comillas dobles, la solución es usar comillas simples alrededor del texto:

```py
print('May dice que "Python es genial"')    # OK
```

* **Caracteres de escape:** pero, ¿qué pasa si necesitas usar el mismo tipo de comillas dentro y fuera del texto? No te preocupes, puedes usar el carácter de escape (`\`) para decirle a Python que ignore la comilla y la trate como parte del texto:

```py
print("May dice que \"Python es genial\"")  # Comillas dentro del texto, sin dramas
```

De esta forma, puedes usar el tipo de comillas que quieras sin generar errores.

En conclusión, usa comillas dobles si tu texto contiene apóstrofes, y comillas simples si contiene comillas dobles. Y si necesitas el mismo tipo de comillas dentro y fuera, el carácter de escape te sacará de apuros. ¡Así te ahorrarás dolores de cabeza!

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
    * **División:** /
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
```

```py
print((2 + 3) * 4)  # Resultado: 20 (los paréntesis cambian el orden de evaluación)
```

¡Experimenta con tus propios cálculos y verás cómo cambia el resultado dependiendo del orden!

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
print("El año que viene tendré " + edad + " años.")
```

## 6. Interacción con el usuario: input()

Hasta ahora, tú eras quien le daba las órdenes a Python, pero ¿qué tal si hacemos que el programa pregunte algo al usuario? Aquí entra en juego `input()`. Este comando permite que el programa espere a que el usuario escriba algo y luego lo usemos en el código.

* **Uso básico de input():**
  
```py
nombre = input("¿Cómo te llamas? ")
print("Hola, " + nombre + "!")
```

¡Ahora tu programa puede saludar a cualquiera que lo use! 😄

## 7. Es tu turno 

Ahora que ya sabes más sobre `print()`, arte ASCII, operaciones matemáticas e interacción con el usuario, ¡es tu momento de crear! Aquí tienes algunas ideas para que experimentes:

* **Crea tu propio arte ASCII:** diseña una figura usando caracteres ASCII. ¿Podrías hacer un coche, un cohete o un animal? ¡Imaginación al poder!
* 
* **Un programa sobre ti:** haz que el programa pida el nombre, tu dirección y tu teléfono, y saque todos los datos por pantalla.



