# Más sobre cadenas de texto 

## 1. Operaciones básicas

Ya hemos visto en apartados anteriores que Python permite manejar cadenas de texto utilizando indistintamente comillas simples o dobles. Podemos crearlas con un texto predefinido en el programa, o pedirlas al usuario a través de la instrucción input:

```py
texto = "Hola"
texto2 = 'Buenas' 
texto3 = input("Dime tu nombre: ")
```

Además, también hemos visto las siguientes operaciones básicas:

* **Concatenación:** unimos cadenas con el operador `+`

```py
nombre = "May"
texto = "Hola, " + nombre  # Hola, May
```

* **Conversión a cadena:** convertimos cualquier dato a cadena con `str()`

```py
edad = 17
texto = "Tengo " + str(edad) + " años"
```

* **Repetir cadenas:** repetimos una cadena usando `*`:

```py
texto = "Hola" * 3  # HolaHolaHola
```

A estas operaciones básicas ya conocidas, podemos añadir la siguiente: 

* **Índices y longitud:** podemos acceder a un carácter concreto con corchetes `[]` y conocer la longitud de la cadena con `len()`:

```py
texto = "Hola"
print(texto[0])  # H
print(len(texto))  # 4
```





