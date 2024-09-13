# Más tipos de operadores

## 1. Operadores relacionales

Cuando queremos comparar dos elementos, Python nos ofrece los operadores relacionales. Estos operadores devuelven un valor de tipo booleano (`True` o `False`) dependiendo de si la condición que se está evaluando es cierta o falsa.

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

Los operadores lógicos te permiten combinar varias comparaciones o condiciones para crear expresiones más complejas. En Python, los operadores lógicos son:

* **and** *(Y lógica)*: devuelve `True` solo si ambas condiciones son verdaderas. 
* **or** *(O lógica)*: devuelve `True` si al menos una de las condiciones es verdadera. 
* **not** *(Negación lógica)*: invierte el valor de la condición, es decir, `True` se convierte en `False` y viceversa. 

```py
3 > 2 and 5 > 1  # True, ambas condiciones son verdaderas
3 > 2 and 5 < 1  # False, solo una condición es verdadera
3 > 2 or 5 < 1  # True, al menos una de las condiciones es verdadera
not 3 > 2  # False, porque 3 > 2 es True y not invierte el resultado
```

