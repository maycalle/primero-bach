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

* **1. Edad (adulto o no):** escribe un programa que pida la edad de una persona y muestre si es mayor de edad (18 años o más) o menor de edad.
* **2. Validador de contraseña:** escribe un programa que pida una contraseña. Si la contraseña es 1111 o 4444, debe mostrar "Bienvenido/a". En cualquier otro caso, "Acceso no permitido". 
* **3. Impuesto básico (edad y sueldo):** para pagar un impuesto se deben cumplir dos condiciones a la vez: tener al menos 16 años y cobrar más de 1000 euros mensuales. Escribe un programa que le pida al usuario su edad y su sueldo mensual y le diga si tiene que pagar el impuesto o no.
* **4. Validador de usuario y contraseña:** escribe un programa que pida un nombre de usuario y una contraseña. Solo si el usuario es "alumno" y la contraseña es "1234", mostrará "Acceso permitido". En cualquier otro caso, "Usuario o contraseña incorrectos".
* **5. Juego de adivinanza simple**: el programa guarda un número secreto (elige uno, por ejemplo 7). El usuario introduce un número:
   - Si acierta → “¡Has ganado!”
   - Si es menor → “Demasiado bajo”
   - Si es mayor → “Demasiado alto”
* **6. Número positivo, negativo o cero:** escribe un programa que pida un número y diga si es positivo, negativo o cero.
* **7. Notas de examen:** escribe un programa que pida al usuario introducir una nota (entre 0 y 10) y muestre:
    - Menos de 5 → "Suspenso".
    - 5 o 6 → "Aprobado".
    - 7 u 8 → "Notable".
    - 9 o 10 → "Sobresaliente".

* **8. Comprobador de divisibilidad**: escribe un programa que pida un número entero y muestre:

    - "Divisible por 2 y 3" si lo es por ambos.
    - "Divisible por 2" si solo lo es por 2.
    - "Divisible por 3" si solo lo es por 3.
    - "No divisible por 2 ni por 3" en cualquier otro caso.

   *Pistas:* 

    - Usa el operador módulo %.
    - Ejemplo: numero % 2 == 0 significa “es divisible por 2”.
    - Combina con and y elif.

* **9. Calculadora de impuestos (por tramos):** escribe un programa que pida el sueldo anual y calcule el impuesto según los siguientes tramos:

    - Menos de 10.000 € → 5%.
    - Entre 10.000 y 19.999 € → 15%.
    - Entre 20.000 y 34.999 € → 20%.
    - 35.000 € o más → 30%.

    El programa debe mostrar:

    - El impuesto que se paga.
    - El dinero que queda después de pagar impuestos.
   
    *Pistas:*

    - Pide sueldo como float.
    - Usa elif para comprobar rangos.
    - Calcula el impuesto como: impuesto = sueldo * 0.15 y restante = sueldo - impuesto
   

* **10. Calculadora de becas:** escribe un programa que pida la edad y la nota media de un estudiante.

    El sistema funciona así:

    - Si la nota < 5 o la edad > 18 → el estudiante no tiene beca.
    - Si la nota ≥ 9 → el estudiante recibe una beca del 100%.
    - Si la nota ≥ 7 y < 9 → el estudiante recibe una beca del 50%.
    - Si la nota ≥ 5 y < 7 → el estudiante recibe una beca del 25%.

    El programa debe mostrar al final un mensaje que indique claramente el resultado, por ejemplo:

    - "No hay beca"
    - "Beca del 100%"
    - "Beca del 50%"
    - "Beca del 25%"

    *Pistas:*

    - Primero descarta a los que no cumplen (if nota < 5 or edad > 18).
    - Después usa elif para comprobar los tramos de nota.
    - Ordena las condiciones de mayor a menor para evitar errores.
    - Recuerda mostrar siempre un mensaje con print().


Si has terminado todos los ejercicios, puedes continuar con más **retos** en la [**web kattis**](https://open.kattis.com/)





