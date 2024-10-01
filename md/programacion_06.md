# 6. Listas

Una **lista** es una estructura de datos que permite almacenar elementos de diferentes tipos y pueden modificarse fácilmente (añadiendo o quitando elementos).

En este apartado, aprenderemos cómo crear listas, acceder a sus elementos y realizar operaciones comunes, como añadir, modificar y eliminar valores.

## 1. Creación de listas

Puedes crear una lista de dos maneras:

* **Directamente con corchetes:**

    ```py
    # Creamos una lista con tres elementos
    mi_lista = ['A', 'B', 'C']
    print(mi_lista)  # Salida: ['A', 'B', 'C']    
    ```

* **Usando la función `list()`:**

    ```py
    # Creamos una lista vacía usando la función list()
    mi_lista = list()
    print(mi_lista)  # Salida: []
    ```

* Las listas pueden contener cualquier tipo de datos, incluso mezclados:

    ```py
    # Ejemplo de lista con elementos de diferentes tipos
    mi_lista = ['Juan', 25, True]  
    print(mi_lista)  # Salida: ['Juan', 25, True]
    ```

## 2. Acceder a los elementos

* Para obtener un elemento de una lista, usamos su **índice**, que empieza en 0. Por ejemplo, si tenemos la lista `mi_lista = ['A', 'B', 'C']`, el primer elemento será `mi_lista[0]`, y el segundo `mi_lista[1]`.

    ```py
    mi_lista = ['A', 'B', 'C']
    print(mi_lista[0])  # Salida: 'A' (primer elemento)
    print(mi_lista[1])  # Salida: 'B' (segundo elemento)
    ```

* Podemos usar índices negativos para acceder a los elementos desde el final. En `mi_lista = ['A', 'B', 'C']`, `mi_lista[-1]` devolverá 'C'.

    ```py
    mi_lista = ['A', 'B', 'C']
    print(mi_lista[-1])  # Salida: 'C' (último elemento)
    print(mi_lista[-2])  # Salida: 'B' (penúltimo elemento)
    ```

### 2.1 Recorrer una lista 

La forma más sencilla de recorrer una lista es usar un bucle `for..in`. Este bucle permite iterar por cada elemento de la lista y realizar acciones con ellos.

```py
mi_lista = [10, 20, 30, 40, 50]
for elemento in mi_lista:
    print(elemento) # Salida: 10 20 30 40 50 (cada número en una línea diferente)
```

### 2.2 Sublistas

Podemos obtener una sublista de una lista dada de la siguiente forma:

`sublista = mi_lista[inicio:fin:salto]`

Donde: 
* **inicio:** es el índice desde donde se empieza a extraer (incluido).
* **fin:** es el índice hasta donde se extrae (no incluido).
* **salto:** indica el salto entre los elementos. El valor por defecto es 1.

**Ejemplos**

* **Sublista básica:** extraer los elementos desde el índice 1 al 4

    ```py
    lista = [10, 20, 30, 40, 50, 60]
    sublista = lista[1:4]  # Extrae desde el índice 1 hasta el 3
    print(sublista)  # Salida: [20, 30, 40]
    ```

* **Sublista con saltos:** extraer elementos en saltos de 2

    ```py
    lista = [1, 2, 3, 4, 5, 6]
    sublista = lista[0:6:2]  # Extrae desde el índice 0 hasta el 5, saltando de 2 en 2
    print(sublista)  # Salida: [1, 3, 5]
    ```

## 3. Modificar listas

* Para **añadir elementos al final**, usamos `append()`:
  
    ```py
    # Agregamos un nuevo elemento al final de la lista
    mi_lista = ['A', 'B', 'C']
    mi_lista.append('D')
    print(mi_lista)  # Salida: ['A', 'B', 'C', 'D']
    ```

* Para **insertar un elemento en una posición específica**, usamos `insert()`. Se debe indicar el índice donde se desea insertar el elemento y luego el valor.

    ```py
    # Insertamos el elemento 'X' en la posición 1
    mi_lista = ['A', 'B', 'C']
    mi_lista.insert(1, 'X')  
    print(mi_lista)  # Salida: ['A', 'X', 'B', 'C']    
    ```

* Para **eliminar un elemento por su posición**, usamos `del` o `pop()`. Por defecto, `pop()` elimina el último elemento si no se especifica índice:

    ```py
    # Eliminamos el elemento en la posición 1 ('B')
    mi_lista = ['A', 'B', 'C', 'D']
    del mi_lista[1]
    print(mi_lista)  # Salida: ['A', 'C', 'D']

    # Eliminamos el elemento en la posición 2 ('D') y lo almacenamos
    elemento_eliminado = mi_lista.pop(2)
    print(mi_lista)  # Salida: ['A', 'C']
    print(elemento_eliminado)  # Salida: 'D'
    ```

* Para **eliminar un elemento por su valor**, usamos `remove()`:

    ```py
    # Eliminamos el primer elemento que tenga el valor 'A'
    mi_lista = ['A', 'B', 'C']
    mi_lista.remove('A')
    print(mi_lista)  # Salida: ['B', 'C']
    ```

## 4. Copiar listas

Existen dos formas de copiar listas:

* **Copia por referencia (lista1 = lista2):** se asocia a `lista1` la misma lista que `lista2`. Ambas variables apuntan a la misma dirección de memoria, por lo que cualquier cambio en una afectará a la otra. 
  
    ```py
    lista1 = [1, 2, 3]
    lista2 = lista1  # Copia por referencia
    lista2.append(4)
    print(lista1)  # Salida: [1, 2, 3, 4]
    print(lista2)  # Salida: [1, 2, 3, 4]
    ```

Tanto lista1 como lista2 apuntan a la misma lista, por lo que los cambios en lista2 también se reflejan en lista1.

* **Copia por valor (lista1 = list(lista2)):** esto crea una nueva lista independiente con el mismo contenido que `lista2`, pero en una dirección de memoria diferente. Las dos listas son independientes, por lo que los cambios en una no afectan a la otra.

    ```py
    lista1 = [1, 2, 3]
    lista2 = list(lista1)  # Copia por valor
    lista2.append(4)
    print(lista1)  # Salida: [1, 2, 3]
    print(lista2)  # Salida: [1, 2, 3, 4]
    ```

Aquí, lista1 y lista2 son listas separadas, por lo que los cambios en lista2 no modifican a lista1.

## 5. Otras funciones interesantes sobre listas

* El método `sort()` ordena los elementos de la lista de menor a mayor. Si quieres que sea en orden inverso, puedes usar el argumento `reverse=True`.

    ```py
    mi_lista = [3, 1, 2]
    mi_lista.sort()
    print(mi_lista)  # Salida: [1, 2, 3]

    mi_lista.sort(reverse=True)
    print(mi_lista)  # Salida: [3, 2, 1]
    ```

* La función `len()` devuelve la cantidad de elementos en la lista.

    ```py
    mi_lista = [1, 2, 3, 4]
    print(len(mi_lista))  # Salida: 4
    ```

* El método `count()` cuenta cuántas veces aparece un valor en la lista.

    ```py
    mi_lista = [1, 2, 2, 3, 2]
    print(mi_lista.count(2))  # Salida: 3
    ```

* Los métodos `min()`, `max()`, y `sum()` son útiles para trabajar con listas numéricas:
    * **min(lista):** devuelve el valor mínimo de la lista.
    * **max(lista):** devuelve el valor máximo de la lista.
    * **sum(lista):** Suma todos los elementos de la lista.

    ```py
    lista = [3, 1, 4, 2]
    print(min(lista))  # Salida: 1
    print(max(lista))  # Salida: 4
    print(sum(lista))  # Salida: 10
    ```

* El método `reverse()` invierte los elementos de la lista, modificando directamente la lista sin crear una nueva. A diferencia de `sort(reverse=True)`, `reverse()` no ordena los elementos, solo cambia su orden.

```py
mi_lista = [1, 2, 3, 4]
mi_lista.reverse()
print(mi_lista)  # Salida: [4, 3, 2, 1]
```

## 6. Es tu turno

* 1. Escribe un programa llamado **loterias.py** que pregunte al usuario los números ganadores de la lotería primitiva, los almacene en una lista y los muestre por pantalla ordenados de menor a mayor.

* 2. Escribe un programa llamado **sentido_inverso.py** que almacene en una lista los números del 1 al 10 y los muestre por pantalla en orden inverso separados por comas.

* 3. Escribe un programa llamado **precios.py** que almacene en una lista 10 precios diferentes y muestre por pantalla el menor y el mayor de los precios.

* 3. Escribe un programa llamado **abecedario.py** que almacene el abecedario en una lista, elimine de la lista las letras que ocupen posiciones múltiplos de 3, y muestre por pantalla la lista resultante.

* 4. Escribe un programa llamado **vocales.py** que pida al usuario una palabra y muestre por pantalla el número de veces que contiene cada vocal.

* 5. Escribe un programa llamado **asignaturas.py** que realice las siguientes acciones:
    * **Crea una lista** que contenga las asignaturas de un curso (por ejemplo: Física, Química, Matemáticas, Historia y Lengua). Puedes ordenarla de acuerdo a tu nivel de interés (de más a menos interesante para ti). A continuación, muestra la lista por pantalla.
    * **Añadir una asignatura:** el programa debe pedir al usuario que introduzca el nombre de una nueva asignatura y la posición en la que quiere insertarla dentro de la lista. Una vez insertada, el programa debe mostrar la lista actualizada con la nueva asignatura en la posición elegida.
    * **Eliminar una asignatura:** El programa debe pedir al usuario que elimine una asignatura de la lista por su nombre. Después de eliminarla, muestra la lista actualizada sin esa asignatura.

    **Ejemplo de funcionamiento:** 

    ```
    Asignaturas ordenadas de más a menos interesantes:
    ['Física', 'Química', 'Matemáticas', 'Historia', 'Lengua']

    Introduce una nueva asignatura: Programación
    ¿En qué posición quieres añadirla (1-5)? 1
    Lista de asignaturas actualizada:
    ['Programación', 'Física', 'Química', 'Matemáticas', 'Historia', 'Lengua']

    ¿Qué asignatura deseas eliminar?: Historia
    Lista de asignaturas tras la eliminación:
    ['Programación', 'Física', 'Química', 'Matemáticas', 'Lengua']
    ```

* 6. Escribe un programa llamado **notas_asignaturas.py** que realice las siguientes acciones:
    * **Crear una lista de asignaturas:** crea una lista con varias asignaturas (como en el ejercicio anterior). Muestra esta lista de asignaturas por pantalla.
    * **Solicitar las notas:** pide al usuario que introduzca una nota para cada asignatura en el mismo orden en el que aparecen en la lista de asignaturas. Las notas deben guardarse en una nueva lista de notas, asegurando que las posiciones de las notas coincidan con las asignaturas correspondientes.
    * **Calcular el promedio:** calcula el promedio de todas las notas introducidas y muéstralo con 2 cifras decimales por pantalla.
    * **Mostrar asignaturas y notas:** finalmente, muestra la lista de asignaturas con sus respectivas notas, utilizando el siguiente formato: `Asignatura: Nota`

    **Ejemplo de funcionamiento:**
           
    ```
    Asignaturas: ['Física', 'Química', 'Matemáticas', 'Historia', 'Lengua']

    Introduce la nota para Física: 8
    Introduce la nota para Química: 7.5
    Introduce la nota para Matemáticas: 9
    Introduce la nota para Historia: 6
    Introduce la nota para Lengua: 7

    Asignaturas y notas:
    Física: 8.0
    Química: 7.5
    Matemáticas: 9.0
    Historia: 6.0
    Lengua: 7.0

    El promedio de las notas es: 7.50
    ```

Si has terminado todos los ejercicios, puedes continuar con más **retos** en la [**web kattis**](https://open.kattis.com/)


