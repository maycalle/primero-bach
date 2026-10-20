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

### 1.1 Creación de listas numéricas consecutivas con range()

Escribir a mano una lista de muchos números (por ejemplo, del 1 al 100) resulta tedioso y propenso a errores. Para automatizarlo, podemos combina la función `range()` con la función `list()`.

La función `range(inicio, fin, salto)` genera una secuencia de números enteros, donde:

- **inicio:** el primer número de la secuencia (incluido). Si se omite, empieza en 0 por defecto.
- **fin:** el límite superior ( no incluido, se detiene uno antes).
- **salto (opcional):** la distancia entre números consecutivos. Por defecto vale 1.

Para transformar esa secuencia en una lista real modificable, la envolvemos dentro de list()

```py
# Lista de números del 1 al 10 (el 11 se excluye)
numeros = list(range(1, 11))
print(numeros)  # Salida: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# Lista del 0 al 4 (omitiendo el inicio)
cero_a_cuatro = list(range(5))
print(cero_a_cuatro)  # Salida: [0, 1, 2, 3, 4]

# Lista de números pares del 2 al 10 (con salto de 2)
pares = list(range(2, 11, 2))
print(pares)  # Salida: [2, 4, 6, 8, 10]

# Secuencia descendente del 10 al 1 (con salto negativo)
cuenta_atras = list(range(10, 0, -1))
print(cuenta_atras)  # Salida: [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
```

>**Nota:** `range()` no crea la lista por sí solo; genera una secuencia bajo demanda. Por eso es obligatorio envolverlo con `list(...)` si queremos almacenar los valores como una lista en memoria.

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

* Podemos **buscar la posición de un elemento** dentro de una lista con el método `.index()`. Le pasamos el valor que queremos buscar y nos devuelve el primer índice donde aparece. Si el elemento aparece repetido varias veces, `.index()` devolverá únicamente la posición de la primera aparición.

    ```py
    colores = ['rojo', 'verde', 'azul', 'verde']

    posicion = colores.index('azul')
    print(posicion)  # Salida: 2 (el primer elemento es 0)
    ```

Si buscas un elemento que no existe en la lista, Python lanzará un error (`ValueError`) y el programa se detendrá. Para evitar que el programa falle, comprueba siempre antes con el operador `in` que el elemento existe previamente en la lista: 

    ```py
    colores = ['rojo', 'verde', 'azul', 'verde']

    # Color que queremos buscar
    color_buscado = 'azul'

    # Comprobamos previamente si el elemento existe en la lista
    if color_buscado in colores:
        # Obtenemos su posición con .index() de forma segura
        posicion = colores.index(color_buscado)
        print(f"El color '{color_buscado}' se encuentra en la posición {posicion}.")
    else:
        print(f"El color '{color_buscado}' no existe en la lista.")
    ```

### 2.1 Recorrer una lista 

La forma más sencilla de recorrer una lista es usar un bucle `for..in`. Este bucle permite iterar por cada elemento de la lista y realizar acciones con ellos.

```py
mi_lista = [10, 20, 30, 40, 50]
for elemento in mi_lista:
    print(elemento) # Salida: 10 20 30 40 50 (cada número en una línea diferente)
```

### 2.2 Sublistas (slicing)

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

**¡Cuidado al usar remove()!**

Si intentas eliminar un valor que no está en la lista, Python lanzará un error (`ValueError`) y el programa se detendrá.

Para evitar que el programa falle, es una buena práctica comprobar primero si el elemento existe usando el operador `in`:

```py
mi_lista = ['B', 'C', 'D']

# Comprobamos si el elemento existe antes de borrarlo
if 'A' in mi_lista:
    mi_lista.remove('A')
    print("Elemento eliminado correctamente.")
else:
    print("El elemento no se encuentra en la lista.")
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

## 5. Métodos y funciones integradas útiles

* El método `sort()` ordena los elementos de la lista de menor a mayor. Si quieres que sea en orden inverso, puedes usar el argumento `reverse=True`.

    ```py
    mi_lista = [3, 1, 2]
    mi_lista.sort()
    print(mi_lista)  # Salida: [1, 2, 3]

    mi_lista.sort(reverse=True)
    print(mi_lista)  # Salida: [3, 2, 1]
    ```

* El método `reverse()` invierte los elementos de la lista, modificando directamente la lista sin crear una nueva. A diferencia de `sort(reverse=True)`, `reverse()` no ordena los elementos, solo cambia su orden.

```py
mi_lista = [1, 2, 3, 4]
mi_lista.reverse()
print(mi_lista)  # Salida: [4, 3, 2, 1]
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

* La función `len()` devuelve la cantidad de elementos en la lista.

    ```py
    mi_lista = [1, 2, 3, 4]
    print(len(mi_lista))  # Salida: 4
    ```

## 6. Es tu turno

**Ejercicio 1.** Escribe un programa llamado `sentido_inverso.py` que almacene en una lista los números del 1 al 10 y los muestre por pantalla en orden inverso, en una sola línea y separados por comas.

> Pista: Puedes invertir el orden de la lista antes con el método `.reverse()` y luego recorrerla con un bucle `for`, o recorrer los índices hacia atrás. Para que los números salgan en la misma línea separados por comas, recuerda el uso del parámetro `end=","` en la función `print()`.

- **Reto:** Con `print(..., end=", ")`, el último número dejará una coma suelta al final (10, 9, ..., 1, ). Haz que no aparezca esa última coma (puedes usar la condición `if i != len(...) - 1` o `", ".join(...)`).

**Ejercicio 2.** Escribe un programa llamado `loteria.py` que solicite al usuario los 6 números de una apuesta de la **Lotería Primitiva** (valores entre 1 y 49).
   - El programa debe pedir los números uno a uno.
   - Si el usuario introduce un número fuera del rango (1-49) o un número que ya ha introducido antes, el programa debe mostrar un mensaje de aviso y volver a pedir ese mismo número sin avanzar el contador.
   - Al finalizar, muestra la combinación ordenada de menor a mayor (`.sort()`).

**Ejercicio 3.** Un observatorio meteorológico toma 8 registros de temperatura a lo largo del día. Escribe un programa llamado `radar_temperaturas.py` que:

- Pida al usuario las 8 temperaturas (números reales) y las guarde en una lista.
- Calcule y muestre:
   - La **temperatura mínima** y cuándo se tomó (número de medición de 1 a 8).
   - La **temperatura máxima**.
   - La **media del día** con 2 decimales.
   - El número de registros que estuvieron por **encima de la media**.


**Ejercicio 4.** Queremos eliminar las letras que ocupan posiciones múltiplos de 3 (la 3ª letra 'c', la 6ª letra 'f', la 9ª 'i', etc.).

- Crea una lista con todas las letras del abecedario

```py
abecedario = [
    'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm',
    'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z'
]
```
- **Método seguro (lista nueva):** crea una nueva lista vacía `resultado = []`. Recorre abecedario con un bucle y añade a resultado únicamente aquellas letras cuya posición humana no sea múltiplo de 3 (pista: usa el índice del bucle o un contador).
- **El reto del borrado inverso:** ahora intenta resolverlo sobre la lista original, eliminando elementos con `del` o `.pop()`.
- **Pregunta de reflexión:** Si intentas borrar recorriendo de izquierda a derecha (0 a 25), ¿por qué falla o se salta letras?
- **Solución ingeniosa:** ¿Qué ocurre si recorres los índices hacia atrás (desde el final hacia el principio)? Pruébalo usando `range(inicio, fin, paso)` con un paso negativo.

**Ejercicio 5.** Escribe un programa llamado `frecuencia_vocales.py` que pida al usuario una frase. 
   - Conviértela a minúsculas con `.lower()`
   - Utiliza dos listas sincronizadas: 
      - una para las vocales ['a', 'e', 'i', 'o', 'u'] 
      - otra para contar apariciones inicializada a ceros [0, 0, 0, 0, 0].
   - Recorre la frase y actualiza el contador correspondiente a cada vocal.
   - Muestra un informe final con un pequeño histograma de texto (ejemplo: si hay 4 'a', dibuja a: **** (4)).
   - Indica cuál fue la vocal más frecuente utilizando `max()` sobre la lista de frecuencias.

**Ejercicio 6**. Crea un programa llamado `gestion_calificaciones.py` para gestionar las asignaturas y calificaciones de un alumno usando dos listas sincronizadas: asignaturas y notas. 

- El programa arrancará con una **lista predefinida** (ej. ['Matemáticas', 'Física', 'Lengua', 'Historia']) y pedirá al inicio la nota de cada una. Luego mostrará un menú interactivo con un bucle while:
- **Ver boletín:** Muestra cada asignatura junto a su nota y la nota media global del curso.
- **Modificar nota:** Pide el nombre de la asignatura. Si existe, pide la nueva nota y la actualiza; si no existe, avisa con un mensaje de error.
- **Añadir asignatura:** Pide el nombre de la nueva materia, la posición donde se desea colocar y su calificación (insertando en ambas listas con .insert()).
- **Eliminar asignatura:** Solicita el nombre de la materia a dar de baja. Debe buscar su índice, eliminarla de asignaturas y retirar también su calificación correspondiente en notas.
- **Salir**.

Si has terminado todos los ejercicios, puedes continuar con más **retos** en la [**web kattis**](https://open.kattis.com/)


