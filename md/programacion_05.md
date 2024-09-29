# 5. Estructuras repetitivas (Bucles)

En programación, muchas veces necesitamos realizar una tarea de forma repetida sin tener que escribir manualmente el mismo código una y otra vez. Aquí es donde entran en juego las **estructuras repetitivas**, también conocidas como **bucles**. Los **bucles** nos permiten ejecutar un bloque de código varias veces de forma automática, lo que no solo ahorra tiempo y líneas de código, sino que también hace que nuestros programas sean más flexibles y eficientes.

Python ofrece dos tipos principales de bucles: **for** y **while**. Cada uno tiene sus propias ventajas y es adecuado para diferentes situaciones. 

## 1. Estructura for

El bucle `for` se utiliza para repetir un bloque de código un número determinado de veces. Su estructura básica es la siguiente:

```py
for i in range(n):
    # Código que se repetirá
``` 

En este caso:
* `i` es una variable que se actualiza automáticamente en cada repetición (o iteración) del bucle.
* `range(n)` genera una secuencia de números que comienza en 0 y llega hasta n-1, lo que significa que el bloque de código se ejecutará n veces.

Por ejemplo, si quisiéramos mostrar la palabra "hola" 10 veces, el código sería:

```py
for i in range(10):
    print("hola")   # Imprime "hola" diez veces
```

Este enfoque es mucho más eficiente que copiar y pegar la misma línea 10 veces. Si luego quisieras imprimir "hola" 100 veces, solo tendrías que cambiar 10 por 100 en `range(100)`, y listo.

Si quisiéramos ver cómo cambia el valor de `i` en lugar de imprimir **"hola"**, podríamos hacer lo siguiente:

```py
for i in range(4):
    print(i)    # Imprime 0 1 2 3
```

### 1.1 La función range()

La función `range()` es fundamental en los bucles `for` porque genera la secuencia de números que controla cuántas veces se ejecuta el bucle. Dependiendo de cómo la uses, `range()` puede generar diferentes tipos de secuencias:

* **range(n):** genera una secuencia que va desde 0 hasta n - 1.
* **range(inicio, fin):** genera una secuencia que empieza en inicio y llega hasta fin - 1.
* **range(inicio, fin, salto):** genera una secuencia que empieza en inicio, termina en fin - 1, y avanza de acuerdo con el valor de salto (que puede ser positivo o negativo).


Por ejemplo, si queremos generar una secuencia de números desde 3 hasta 7, el código sería: 

```py
for i in range(3, 8):
    print(i)  # Imprime 3, 4, 5, 6, 7
```

En este caso, `i` empieza en 3 y termina en 7, porque el bucle se detiene antes de llegar a 8.

Si queremos imprimir todos los números pares comprendidos entre 0 y 8, podemos hacer lo siguiente:

```py
for i in range(0, 9, 2):
    print(i)    # Imprime 0 2 4 6 8 
```

Aquí, el bucle empieza en 0, se detiene antes de llegar a 9, y avanza de 2 en 2.

Si quisiéramos contar hacia atrás desde 10 hasta 1, usaríamos un paso negativo:

```py
for i in range(10, 0, -1):
    print(i)  # Imprime 10, 9, 8, ..., 1
```

En este caso, `i` comienza en 10 y va disminuyendo en 1 hasta llegar a 1 (sin incluir el 0).


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

1. Escribe un programa llamado **impares.py** que pida al usuario un número entero positivo y muestre por pantalla todos los números impares desde 1 hasta ese número separados por comas.

    Para separar los números con comas, puedes usar el parámetro `end` del comando `print`, que define qué carácter colocar al final de lo que se imprime (por defecto es un salto de línea `\n`). Utilízalo así: `print("hola", end=",")`

    **Pista:** un número es impar si el resto de su división entre 2 es distinto de 0 (es decir, `n % 2 != 0`).

2. Escribir un programa llamado **primos.py** que pida al usuario un número entero y muestre por pantalla si es un número primo o no. Recuerda que un número es primo si es mayor que 1 y solo es divisible por 1 y él mismo.  

    **Pista:** un número *a* es divisible por otro número *b* si el resto de dividir *a* entre *b* es igual a 0 (es decir, `a % b == 0`).

3. Crea un programa llamado **notas.py** que le pida al usuario 3 notas, y calcule la nota final según estas reglas:
      * Si ninguna nota es mayor que 4, la nota final es 0
      * Si algunas notas son mayores que 4 (pero no todas), la nota final es 2
      * Si todas las notas son mayores que 4, la nota final será el 30% de la primera más el 20% de la segunda más el 50% de la tercera

4. Crea un programa llamado **factura.py** que le pida al usuario precios para una factura, hasta que escriba 0. Entonces, el programa debe mostrar el total de la factura con 2 dígitos decimales.

5. Escribe un programa llamado **dibuja_triangulo.py** que pida al usuario un número entero y muestre por pantalla un triángulo rectángulo como el de más abajo, de altura el número introducido.

    ```py
    *
    **
    ***
    ****
    *****
    ``` 

6. Crea un programa llamado **mayor_menor.py** que le pida al usuario que introduzca una secuencia de N números positivos (primero el usuario deberá indicar cuántos números va a introducir). Al final del proceso, el programa deberá mostrar por pantalla el valor del número mayor y el menor introducidos por el usuario. Por ejemplo:

    ```py
    Dime cuántos números vas a introducir:
    3
    Escribe 3 números:
    3
    7
    2
    El mayor es 7
    El menor es 2
    ```

    **Pista:** puedes usar variables acumulativas para almacenar el número mayor y el número menor conforme se van introduciendo los números. Comienza asignando a ambas variables el valor del primer número, y luego actualízalas si encuentras un número mayor o menor.

    
Si has terminado todos los ejercicios, puedes continuar con más **retos** en la [**web kattis**](https://open.kattis.com/)