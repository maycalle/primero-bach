# Estructuras de control

Con las estructuras de control podrás tomar decisiones dentro del código, permitiendo que tus programas sigan diferentes caminos dependiendo de las condiciones que se cumplan. Veremos cómo usar operadores relacionales y lógicos para comparar valores, y exploraremos las estructuras selectivas if, if-else, y if-elif-else para crear programas que reaccionen de manera inteligente a diferentes situaciones.

## 1. Operadores relacionales

A veces, necesitarás comparar dos elementos, por ejemplo, para saber si un número es mayor que otro o si dos valores son iguales. Para estas situaciones, Python nos ofrece los **operadores relacionales**, que siempre te devolverán un resultado booleano (`True` o `False`), dependiendo de si la comparación se cumple.

Aquí tienes los operadores relacionales más comunes:

* **==**: igual a.
* **!=**:  distinto de.
* **<**: menor que.
* **<=**: menor o igual que.
* **>**: mayor que.
* **>=**: mayor o igual que.

```py
print(5 == 5)  # True
print(10 != 5)  # True
print(3 < 7)  # True
print(8 >= 8)  # True
print()
```

## 2. Operadores lógicos

Los operadores lógicos son muy útiles cuando necesitas comprobar varias condiciones a la vez. En Python, los principales operadores lógicos son:

* **and** *(Y lógica)*: devuelve `True` solo si **todas** las condiciones son verdaderas. 
* **or** *(O lógica)*: devuelve `True` si al menos **una** de las condiciones es verdadera. 
* **not** *(Negación lógica)*: invierte el valor de la condición (si es `True`, se convierte en `False` y viceversa). 

```py
print(3 > 2 and 5 > 1)  # True, ambas condiciones se cumplen
print(3 > 2 and 5 < 1)  # False, solo una condición es verdadera
print(3 > 2 or 5 < 1)  # True, al menos una de las condiciones es verdadera
print(not 3 > 2)  # False, porque 3 > 2 es True y not invierte el resultado
```

## 3. Estructuras selectivas if, if..else, if..elif..else

Python te permite decidir qué hacer en función de las condiciones que establezcas usando las estructuras de control selectivas. Vamos a ver las más importantes.

* **Estructura básica: if**

    La estructura `if` evalúa una condición, y si esta es verdadera, ejecuta el bloque de código que le sigue. Si la condición es falsa, simplemente salta ese bloque. Es importante que las instrucciones dentro de este bloque estén tabuladas (usualmente con 4 espacios o una tabulación), ya que Python usa la indentación para identificar qué código pertenece a la estructura `if`. Además, siempre debes terminar la línea de la condición con dos puntos (:).

    Por ejemplo:

    ```py
    numero = int(input("Escribe un número positivo:"))
    if numero > 0:
        numero = numero + 1
        print ("El siguiente número es", numero)
    print ("Fin del programa")
    ```

    En este ejemplo, el mensaje *"¡Es un número positivo!"* solo se imprimirá si la condición `numero > 0` es verdadera. La tabulación indica que esa línea pertenece al bloque del `if`. Si no tabulamos, el código lanzará un error, ya que Python no sabrá qué parte del código debe ejecutarse según la condición.

* **Distinguiendo entre dos caminos: if .. else**

    La estructura `if-else` te permite decidir entre dos bloques de código: uno que se ejecuta cuando la condición es verdadera y otro que se ejecuta cuando es falsa. Al igual que con el `if`, es fundamental tabular correctamente el bloque de código correspondiente tanto al `if` como al `else`, y no olvides añadir los dos puntos (:) después de cada uno.

    ```py
    numero = int(input("Escribe un número positivo:"))
    if numero > 0:
        numero = numero + 1
        print ("El siguiente número es", numero)
    else:
        print ("El número no es positivo")
    print ("Fin del programa")
    ```

    En este ejemplo, si la condición `numero > 0` es verdadera, se ejecutará el bloque de código dentro del `if`. Si no se cumple, se ejecutará el bloque dentro del `else`.

* **Varias condiciones a evaluar: if .. elif ..else**

    Si necesitamos tener más de dos caminos diferentes, podemos anidar estructuras `if..else` unas dentro de otras. En este caso, si la primera condición no se cumple, el programa revisará la siguiente condición dentro del bloque `else`. Python ejecutará el bloque de código correspondiente a la primera condición que sea verdadera.

    ```py
    numero = int(input("Escribe un número positivo:"))
    if numero > 0:
        numero = numero + 1
        print ("El siguiente número es", numero)
    else:
        if numero < -10:
            print ("El número es demasiado bajo")
        else:
            print ("El número no es positivo")
    print ("Fin del programa")
    ```

    … pero, en lugar de anidar estas estructuras, también podemos utilizar la cláusula `if..elif` para especificar más de un bloque de condiciones. Podemos enlazar tantas clásulas `elif` como necesitemos, y también concluir con una cláusula `else` si queremos, para el último camino a distinguir:

    ```py
    numero = int(input("Escribe un número positivo:"))
    if numero > 0:
        numero = numero + 1
        print ("El siguiente número es", numero)
    elif numero < -10:
        print ("El número es demasiado bajo")
    else:
        print ("El número no es positivo")
    print ("Fin del programa")
    ```
    
Con los operadores relacionales y lógicos, combinados con las estructuras de control selectivas, puedes crear programas mucho más flexibles y adaptables. Ya no estarás limitado a que tu código se ejecute siempre de la misma manera; ahora puedes tomar decisiones y hacer que el programa reaccione de manera diferente según la entrada del usuario o los valores en juego.

