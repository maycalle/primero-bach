# Listas

Una lista es una estructura de datos que permite almacenar elementos de diferentes tipos y pueden modificarse fácilmente (añadiendo o quitando elementos).

## 1. Creación de listas

Puedes crear una lista de dos maneras:

* **Directamente con corchetes:**

    ```py 
    mi_lista = ['A', 'B', 'C']
    ```

* **Usando la función `list()`:**

    ```py 
    mi_lista = list()
    ```

Las listas pueden contener cualquier tipo de datos, incluso mezclados:

```py
mi_lista = ['Juan', 25, True]
```

## 2. Acceder a los elementos

Para obtener un elemento de una lista, usamos su **índice**, que empieza en 0. Por ejemplo, si tenemos la lista `mi_lista = ['A', 'B', 'C']`, el primer elemento será `mi_lista[0]`, y el segundo `mi_lista[1]`.

Podemos usar índices negativos para acceder a los elementos desde el final. En `mi_lista = ['A', 'B', 'C']`, `mi_lista[-1]` devolverá 'C'.

## 3. Modificar listas

* Para **añadir elementos al final**, usamos `append()`:
  
```py
mi_lista.append('D')
```

* Para **insertar un elemento en una posición específica**, usamos `insert()`:

```py 
mi_lista.insert(1, 'X')
```

* Para **eliminar un elemento por su posición**, usamos `del` o `pop()`:

```py 
del mi_lista[1] 
mi_lista.pop(1)
```

* Para **eliminar un elemento por su valor**, usamos `remove()`:

```py 
mi_lista.remove('A')
```



