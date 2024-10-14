# 8. Funciones en Python

Las funciones son uno de los pilares de la programación. Nos permiten escribir código más eficiente y organizado, dividiendo grandes problemas en partes más pequeñas y manejables. 

En este apartado aprenderemos cómo **definir funciones**, **pasarles parámetros** y hacer que **devuelvan valores** que podemos usar más adelante.

## 1. ¿Qué es una Función?

Una **función** es un bloque de código reutilizable que realiza una tarea específica. Permite organizar el código de manera más clara, evitando la repetición de instrucciones y facilitando su comprensión y mantenimiento.

**Ventajas de usar funciones**

* **Reutilización**: permiten usar el mismo código en varios lugares del programa.
* **Organización**: ayudan a dividir el código en secciones más manejables.
* **Mantenimiento**: si hay errores, es más fácil localizarlos y corregirlos.

## 2. Definición de una función

En Python, se define una función usando la palabra clave `def`. Su sintaxis es la siguiente:

```py
def nombre_funcion(parámetros):
    # Cuerpo de la función
    return valor_de_retorno
```

* **def:** palabra clave para definir la función.
* **nombre_funcion:** nombre que le damos a la función.
* **parámetros:** variables que la función puede recibir (opcional).
* **return:** devuelve un resultado (opcional, pero útil).

### 2.1 Ejemplo básico

```py
def saludar():
    print("¡Hola, bienvenido!")
```

Para llamar a la función, simplemente escribimos su nombre:

```py
saludar()  # Esto imprimirá "¡Hola, bienvenido!"
```

## 3. Funciones con parámetros

Las funciones pueden recibir parámetros que les permiten realizar tareas más complejas con diferentes datos.

```py
def sumar(a, b):
    resultado = a + b
    return resultado
```

Para llamar a esta función, escribimos su nombre y entre paréntesis indicamos el valor de dichos parámetros:

```py
print(sumar(3, 5))  # Esto imprimirá 8
```

En este caso, a y b son los **parámetros** de la función, y 3 y 5 son los **argumentos** que pasamos al llamarla.

> **Nota:** Es importante distinguir entre parámetros y argumentos. Los
> *parámetros* son las variables que se declaran en la definición de la
> función, mientras que los *argumentos* son los valores que se pasan a la
> función cuando es llamada.

### 3.1 Pasar un número indeterminado de argumentos

Es posible pasar un número variable de argumentos a una función, lo que es útil cuando no se sabe cuántos argumentos se recibirán.

Para hacer esto, se antepone un asterisco (*) al nombre del parámetro. Los argumentos se almacenan en una tupla.

```py
def menu(*platos):
    print('Hoy tenemos: ', end='')
    for plato in platos:
        print(plato, end=', ')
    return
```

Al llamar a la función con varios argumentos: 

```py
menu('pasta', 'pizza', 'ensalada') 
# Se imprimirá: "Hoy tenemos: pasta, pizza, ensalada" 
```

### 3.1 Parámetros por defecto

Puedes asignar valores por defecto a los parámetros. Si no se pasa un valor al llamarla, tomará el valor por defecto.

```py
def saludar(nombre="invitado"):
    print(f"¡Hola, {nombre}!")
```

Al llamar a la función:

```py
saludar()           # Imprime: ¡Hola, invitado!
saludar("Lucía")    # Imprime: ¡Hola, Lucía!
```

**Reto:** Define una función que reciba un número y lo multiplique por 5. Si no se pasa ningún argumento, que el número sea 10 por defecto.

### 4. Funciones que devuelven valores

Las funciones pueden devolver valores usando la palabra clave `return`. Esto es útil cuando necesitamos procesar el valor devuelto en otro punto del programa. Sin `return`, la función solo ejecuta su tarea y no podrías reutilizar el resultado que obtiene.

Por ejemplo, la siguiente función realiza la multiplicación de dos números:

```py
def multiplicar(a, b):
    return a * b
```

Al llamar a la función:

```py
resultado = multiplicar(4, 6)
print(resultado)  # Esto imprimirá 24
```

Puedes guardar el resultado en una variable y usarlo en cualquier otra parte del programa. 

**Contraejemplo: función que no devuelve valor**

```py
def multiplicar(a, b):
    print(a * b)  # Esto solo imprimirá el valor pero no lo devolverá

resultado = multiplicar(4, 6)  # El resultado no puede almacenarse ni usarse
print(resultado)  # Esto imprimirá "None", porque no se ha usado `return`
```

## 5. Ámbito de las variables

El ámbito (o *"scope"*) se refiere a desde dónde es accesible una variable. Hay dos tipos:

* **Local:** son las variables definidas dentro de una función, y solo existen dentro de esa función.
* **Global:** son las variables definidas fuera de las funciones, y son accesibles desde cualquier parte del código.

**Ejemplo de ámbito local:**

```py
def prueba():
    x = 10  # x es local
    print(x)

prueba()  # Imprime 10
# print(x)  # Esto daría un error, porque x no existe fuera de la función
```

**Ejemplo de ámbito global:**

```py
x = 10  # Variable global

def prueba():
    print(x)  # Puede acceder a la variable global

prueba()  # Imprime 10
```

## 6. Es tu turno

1. Escribir una función a la que se le pase una cadena <nombre> y muestre por pantalla el saludo ¡hola <nombre>!
   
2. Escribir una función que reciba una muestra de números en una lista y devuelva su media.

    ```py
    media([4, 5, 6, 7, 8])  # Esto devolverá 6.0
    ```
3. Escribir una función que reciba un número entero positivo y devuelva su factorial.

    Pista: El factorial de un número n se calcula multiplicando todos los números enteros desde 1 hasta n. Por ejemplo, el factorial de 5 es 5 * 4 * 3 * 2 * 1 = 120.

    ```py
    factorial(5)  # Esto devolverá 120
    ```
   
4. Crea una función que tome un número entero y retorne **True** si es par, y **False** si es impar.

    ```py
    es_par(4)  # Esto devolverá True
    es_par(7)  # Esto devolverá False
    ```

5. **Conversión entre decimal y binario**.
* Escribe una función que convierta un número decimal en su equivalente binario.
* Escribe otra función que convierta un número binario en su equivalente decimal.

    Pista: Para convertir un número decimal a binario, puedes dividir el número entre 2 repetidamente y registrar los restos. Para la conversión inversa (binario a decimal), cada dígito binario representa una potencia de 2 (de derecha a izquierda, el primer dígito es 2^0, el segundo es 2^1, y así sucesivamente).

    ```py
    decimal_a_binario(10)  # Esto devolverá '1010'
    binario_a_decimal('1010')  # Esto devolverá 10
    ```

