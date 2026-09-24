# 4. Otros operadores y estructuras selectivas

Con las **estructuras de control** podrás tomar decisiones dentro del código, permitiendo que tus programas sigan diferentes caminos dependiendo de las condiciones que se cumplan. En esta unidad, aprenderás cómo usar **operadores relacionales y lógicos** para comparar valores, y exploraremos las **estructuras selectivas if, if-else, y if-elif-else** para crear programas que reaccionen de manera inteligente a diferentes situaciones.

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
print( 2 > 10) # False

x = 4
y = 7
print(x < y) # True (4 es menor que 7)
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
print(not (3 > 2))  # False, porque 3 > 2 es True y not invierte el resultado
```

## 3. Estructuras selectivas if, if..else, if..elif..else

Con la ayuda de los operadores relacionales y lógicos puedes tomar decisiones dentro de tu código con las estructuras selectivas. Estas permiten ejecutar bloques de código dependiendo de si las condiciones son verdaderas o falsas.

* **Estructura básica: if**

    La estructura `if` evalúa una condición, y si esta es verdadera, ejecuta el bloque de código que le sigue. Si la condición es falsa, simplemente salta ese bloque. Es **muy importante tabular las instrucciones** dentro del bloque `if` (usualmente con 4 espacios o una tabulación), ya que Python usa la indentación para identificar qué código pertenece a la estructura. Además, siempre debes terminar la línea de la condición con dos puntos (:).

    Por ejemplo:

    ```py
    numero = int(input("Escribe un número positivo:"))
    if numero > 0:
        numero = numero + 1
        print ("El siguiente número es", numero)
    print ("Fin del programa")
    ```

    Aquí, si `numero > 0` es verdadero, el número se incrementará y se imprimirá el mensaje. Si no se cumple, el programa simplemente continuará con el resto del código.
    - Si escribes 5, se mostrará: "El siguiente número es 6".
    - Si escribes -3, no pasará nada dentro del if, y solo aparecerá "Fin del programa".

* **Distinguiendo entre dos caminos: if .. else**

    Cuando quieres manejar dos posibles resultados, puedes usar la estructura `if-else`. Esta te permite ejecutar un bloque de código si la condición es verdadera, y otro bloque si la condición es falsa. Al igual que con el `if`, el bloque asociado al `else` también debe estar tabulado correctamente, y no olvides los dos puntos (:) en ambas líneas.

    ```py
    numero = int(input("Escribe un número positivo:"))
    if numero > 0:
        numero = numero + 1
        print ("El siguiente número es", numero)
    else:
        print ("El número no es positivo")
    print ("Fin del programa")
    ```

    Si `numero > 0` es verdadero, se ejecutará el código dentro del `if`. Si no, se ejecutará el bloque dentro del `else`.
    - Con 5: "El siguiente número es 6".
    - Con -2: "El número no es positivo".

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

- Con 5: "El siguiente número es 6".
- Con -20: "El número es demasiado bajo".
- Con -3: "El número no es positivo".

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

    Con `if-elif-else`, puedes manejar varias condiciones de manera más clara y eficiente que anidando múltiples estructuras.

Estas herramientas te permiten tomar decisiones en tu código y hacer que tu programa responda de manera diferente dependiendo de las condiciones establecidas. ¡Con esto, ya tienes la base para crear programas mucho más inteligentes y dinámicos!

## 4. Es tu turno

¡Ahora es tu momento de aplicar lo que has aprendido! Aquí tienes algunos ejercicios:

**Ejercicio 1. Mayoría de edad:** pide la edad de una persona. Si tiene 18 años o más, muestra "Mayor de edad"; en caso contrario, muestra "Menor de edad".

**Ejercicio 2. Número positivo, negativo o cero:** pide un número entero e indica si es positivo, negativo o cero.

**Ejercicio 3. Validador de contraseña:** Pide un código o contraseña. Si la contraseña es `1111` o `4444`, debe mostrar *"Bienvenido/a"*. En cualquier otro caso, *"Acceso no permitido"*.

**Ejercicio 4. Control de acceso de doble factor:**  Pide un nombre de usuario y una contraseña. Solo si el usuario es `alumno` y la contraseña es `1234`, muestra *"Acceso permitido"*. En cualquier otro caso, muestra *"Usuario o contraseña incorrectos".*

**Ejercicio 5. Juego de adivinanza simple**: el programa guarda un número secreto (elige uno, por ejemplo 7). El usuario introduce un número:
   - Si acierta → “¡Has ganado!”
   - Si es menor → “Demasiado bajo”
   - Si es mayor → “Demasiado alto”

**Ejercicio 6. Calificaciones académicas:** pide una nota con decimales (float) entre 0 y 10 e imprime su tramo. 
  - Menor que 5 → *"Suspenso"*.
  - De 5 a menos de 7 → *"Aprobado"*.
  - De 7 a menos de 9 → *"Notable"*.
  - De 9 a 10 → *"Sobresaliente"*.

> (Pista: ordena las condiciones con `elif` aprovechando que las anteriores ya han descartado los valores más bajos o más altos).

**Ejercicio 7. Comprobador de divisibilidad:** pide un número entero. El programa debe indicar:
  - *"Divisible por 2 y por 3"* (si cumple ambas condiciones simultáneamente).
  - *"Divisible solo por 2"*
  - *"Divisible solo por 3"*
  - *"No divisible ni por 2 ni por 3"*

>Pista: para saber si un número es divisible por otro usamos el operador `%`. Ejemplo: si `numero % 2 == 0` significa *“ número es divisible por 2”* ).

**Ejercicio 8. Calculadora IRPF por tramos:** pide el sueldo anual (como `float`) y calcula la retención aplicable:

  - Menos de 10.000 € → 5%
  - De 10.000 € a menos de 20.000 € → 15%
  - De 20.000 € a menos de 35.000 € → 20%
  - 35.000 € o más → 30%

El programa debe imprimir:
  - El importe exacto del impuesto (*impuesto = sueldo * porcentaje*).
  - El sueldo neto restante (*sueldo - impuesto*).

**Ejercicio 9. Concesión de becas:** pide la edad (`entero`) y la nota media de un estudiante (`float`).

El sistema funciona así:
  - Si la edad es mayor de 18 o la nota es menor que 5: "No hay beca".

Si cumple los requisitos de entrada, evalúa la cuantía según su nota:
  - Nota de 9 o más: "Beca del 100%"
  - Nota entre 7 y menos de 9: "Beca del 50%"
  - Nota entre 5 y menos de 7: "Beca del 25%"

El programa debe mostrar al final un mensaje que indique claramente el resultado, por ejemplo:
  - "No hay beca"
  - "Beca del 100%"
  - "Beca del 50%"
  - "Beca del 25%"

*Pistas:*
  - Primero descarta a los que no cumplen el requisito de entrada.
  - Después usa elif para comprobar los tramos de nota.
  - Ordena las condiciones de mayor a menor para evitar errores.
  - Recuerda mostrar siempre un mensaje con print().


Si has terminado todos los ejercicios, puedes continuar con más **retos** en la [**web kattis**](https://open.kattis.com/)

- [**Quadrant selection**](https://open.kattis.com/contests/hzsr8d/problems/quadrant)






