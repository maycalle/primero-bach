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

    Con `if-elif-else`, puedes manejar varias condiciones de manera más clara y eficiente que anidando múltiples estructuras.

Estas herramientas te permiten tomar decisiones en tu código y hacer que tu programa responda de manera diferente dependiendo de las condiciones establecidas. ¡Con esto, ya tienes la base para crear programas mucho más inteligentes y dinámicos!

## 4. Es tu turno

¡Ahora es tu momento de aplicar lo que has aprendido! Aquí tienes algunos ejercicios:

* 1. **Edad (adulto o no):** escribe un programa que le pida al usuario su edad y le diga si es adulto o no.
* 2. **Contraseña:** escribe un programa que le pida al usuario su contraseña y, si es 1111 o 4444, le diga "Bienvenido/a", y si no le diga "Acceso no permitido".
* 3. **Impuesto basado en edad y sueldo mensual:** para pagar un impuesto se deben tener al menos 16 años y cobrar al menos 1000 euros mensuales. Escribe un programa que le pida al usuario su edad y su sueldo mensual y le diga si tiene que pagar el impuesto o no.
* 4. **Calculadora de impuestos para futuros millonarios:** imagina que ya has conseguido tu primer gran sueldo anual (¡felicidades!). Ahora, tu misión es calcular cuánto te tocará pagar en impuestos. Escribe un programa que le pregunte al usuario cuál es su sueldo anual y le diga cuánto debe pagar en impuestos según los siguientes tramos:
    * Si ganas *menos de 10.000 euros*, pagarás un *5%* en impuestos.
    * Si tu sueldo está *entre 10.000 y 20.000 euros*, el impuesto será del *15%*.
    * Si tu sueldo está *entre 20.000 y 35.000 euros*, pagarás un *20%*.
    * Si ganas *35.000 euros o más*, tendrás que pagar un *30%* en impuestos.
    * El programa debe calcular y mostrar cuánto deberás pagar. ¡Vamos a ver cuánto te quedaría para gastar después de impuestos!
* 5. **Calculadora de becas:** imagina que trabajas en una oficina de becas y debes ayudar a decidir quiénes pueden recibir una beca. El sistema funciona así:
    * Para ser elegible, un estudiante debe tener una nota mínima de 5 y no superar los 18 años.
    * Si tiene una nota *mayor o igual a 9*, recibe una beca del *100%*.
    * Si tiene una nota *entre 7 y 9 (sin incluir el 9)*, recibe una beca del *50%*.
    * Si tiene una nota *entre 5 y 7 (sin incluir el 7)*, recibe una beca del *25%*.
    * Si el estudiante tiene *más de 18 años o una nota inferior a 5*, no recibe beca.
    * Escribe un programa que le pida al usuario su edad y su nota media, y le diga qué tipo de beca recibe o si no es elegible para ninguna beca.

Si has terminado todos los ejercicios, puedes continuar con más **retos** en la [**web kattis**](https://open.kattis.com/)





