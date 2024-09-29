# 6. Listas

Una lista es una estructura de datos que permite almacenar elementos de diferentes tipos y pueden modificarse fácilmente (añadiendo o quitando elementos).

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

## 3. Modificar listas

* Para **añadir elementos al final**, usamos `append()`:
  
    ```py
    # Agregamos un nuevo elemento al final de la lista
    mi_lista = ['A', 'B', 'C']
    mi_lista.append('D')
    print(mi_lista)  # Salida: ['A', 'B', 'C', 'D']
    ```

* Para **insertar un elemento en una posición específica**, usamos `insert()`:

    ```py
    # Insertamos el elemento 'X' en la posición 1
    mi_lista = ['A', 'B', 'C']
    mi_lista.insert(1, 'X')  
    print(mi_lista)  # Salida: ['A', 'X', 'B', 'C']    
    ```

* Para **eliminar un elemento por su posición**, usamos `del` o `pop()`:

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



