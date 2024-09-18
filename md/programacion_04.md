# Más tipos de operadores

Hasta ahora, hemos visto cómo Python nos permite hacer operaciones matemáticas básicas con sus operadores aritméticos, pero este lenguaje tiene más operadores bajo la manga, y algunos son realmente útiles. ¡Vamos a conocerlos!

## 1. Operadores relacionales

Imagina que quieres comparar dos elementos, como ver si un número es mayor que otro, o si dos valores son iguales. Para eso, Python nos da los operadores relacionales. Estos siempre devolverán un resultado de tipo booleano, es decir, o `True` (verdadero) o `False` (falso), dependiendo de si la comparación que estás haciendo se cumple o no.

Aquí tienes los operadores relacionales más comunes:

* **==**: igual a.
* **!=**:  distinto de.
* **<**: menor que.
* **<=**: menor o igual que.
* **>**: mayor que.
* **>=**: mayor o igual que.

```py
5 == 5  # True
10 != 5  # True
3 < 7  # True
8 >= 8  # True
```

## 2. Operadores lógicos

Los operadores lógicos permiten combinar varias comparaciones para crear expresiones más complejas. En Python, los operadores lógicos son:

* **and** *(Y lógica)*: devuelve `True` solo si ambas condiciones son verdaderas. 
* **or** *(O lógica)*: devuelve `True` si al menos una de las condiciones es verdadera. 
* **not** *(Negación lógica)*: invierte el valor de la condición, es decir, `True` se convierte en `False` y viceversa. 

```py
3 > 2 and 5 > 1  # True, ambas condiciones son verdaderas
3 > 2 and 5 < 1  # False, solo una condición es verdadera
3 > 2 or 5 < 1  # True, al menos una de las condiciones es verdadera
not 3 > 2  # False, porque 3 > 2 es True y not invierte el resultado
```

