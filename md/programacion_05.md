# Estructuras repetitivas (Bucles)

En programación, muchas veces necesitamos realizar una tarea de forma repetida sin tener que escribir manualmente el mismo código una y otra vez. Aquí es donde entran en juego las **estructuras repetitivas**, también conocidas como **bucles**. Los **bucles** nos permiten ejecutar un bloque de código varias veces de forma automática, lo que no solo ahorra tiempo y líneas de código, sino que también hace que nuestros programas sean más flexibles y eficientes.

Python ofrece dos tipos principales de bucles: **for** y **while**. Cada uno tiene sus propias ventajas y es adecuado para diferentes situaciones. 

## 1. Estructura for

En Python, la estructura básica de un bucle `for` es la siguiente:

```py
for i in range(n):
    # Código que se repetirá
``` 

En este caso, `n` es el número de veces que quieres repetir lo que va dentro del bucle. Por ejemplo, si quisiéramos mostrar la palabra "hola" 10 veces, el código sería:

```py
for i in range(10):
    print("hola")   # Imprime "hola" diez veces
```

Este enfoque es mucho más eficiente que copiar y pegar la misma línea 10 veces. Si luego decides que necesitas imprimir "hola" 100 veces, solo tendrías que cambiar el 10 por un 100, y listo.

La variable `i`, es la que controla el número de repeticiones; `i` comienza en 0 y aumenta de uno en uno con cada vuelta del bucle. Si quisiéramos ver cómo cambia el valor de `i` en lugar de imprimir "hola", podríamos hacer lo siguiente:

```py
for i in range(4):
    print(i)    # Imprime 0 1 2 3
```

Pero Python no solo puede contar de 1 en 1. Si necesitas más control, puedes decirle que empiece en un número específico, termine en otro, e incluso que aumente una cierta cantidad en cada vuelta o iteración. 

```py
for i in range(0, 9, 2):
    print(i)    # Imprime 0 2 4 6 8 
```

Este bucle empieza en 0, se detiene antes de llegar a 9, y avanza de 2 en 2.

## 2. Estructura while

Además del bucle `for`, Python ofrece otro tipo de bucle llamado `while`, que también permite repetir una sección de código varias veces, pero con una diferencia importante: en lugar de repetir un número fijo de veces, el bucle `while` se ejecuta mientras se cumple una determinada condición.

La estructura básica de un while es la siguiente:

```py
while condición:
    # Código que se repetirá mientras la condición sea verdadera
```

El bucle continuará ejecutándose mientras la condición sea verdadera. En el momento en que la condición es falsa, el bucle se detiene. Por ejemplo, supongamos que queremos imprimir "hola" mientras una variable llamada contador sea menor que 5:

```py
contador = 0
while contador < 5:
    print("hola")   # Imprime "hola"
    contador += 1   # Aumenta el contador en 1 en cada iteración
``` 

En este caso: 
* La variable `contador` empieza en 0.
* Mientras `contador` sea menor que 5, el bucle imprimirá "hola".
* En cada repetición, aumentamos el valor de `contador` en 1 con `contador += 1`.
* Cuando `contador` llega a 5, la condición `contador < 5` ya no se cumple, y el bucle se detiene.


## 3. Diferencias clave entre FOR y WHILE

* **FOR** se utiliza cuando sabes cuántas veces quieres que se repita el código.
* **WHILE** se usa cuando no sabes de antemano cuántas veces se repetirá el bucle, porque la repetición depende de una condición que puede cambiar mientras se ejecuta el programa.

Por ejemplo, imagina que quieres hacer un bucle que pida al usuario que adivine un número hasta que lo acierte. Usarías un while, porque no sabes cuántas veces el usuario necesitará intentarlo:

```py
numero_secreto = 7
adivina = int(input("Adivina el número: "))

while adivina != numero_secreto:
    print("¡Intenta de nuevo!")
    adivina = int(input("Adivina el número: "))

print("¡Felicidades, adivinaste el número!")
```

Este bucle seguirá pidiendo al usuario que adivine el número hasta que el valor introducido sea igual a `numero_secreto`.

Como ves, los bucles son una herramienta muy poderosa para hacer que tu código sea más eficiente y flexible. Python te da toda la libertad para controlar cómo y cuántas veces se repiten las cosas.

## 4. Es tu turno

