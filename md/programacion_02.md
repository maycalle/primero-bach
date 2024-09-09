# Imprime, calcula y pregunta

En esta sesión vamos a aprender más detalles sobre el comando `print()`, exploraremos el arte ASCII (sí, ¡dibujos con caracteres!), trabajaremos con operadores matemáticos y, lo más importante, ¡aprender a interactuar con el usuario con `input()`! 

## 1. Más sobre print()

Ya sabemos cómo usar `print()` para mostrar mensajes en pantalla. Ahora vamos a ver cómo lidiar con situaciones más complejas, como incluir apóstrofes o comillas dentro del texto, mediante el uso de comillas simples (' ') y dobles (" ").
¡Spoiler! Son casi iguales, pero hay detalles importantes.

* **Comillas simples vs. comillas dobles:** puedes usar tanto comillas simples (' ') como comillas dobles (" ") para mostrar texto. Pero, ¿qué pasa si quieres usar un apóstrofe dentro del texto? Aquí es donde la cosa se pone interesante. Mira:

```py
print('I'm learning Python')    # ¡Error! Python se confunde con el apóstrofe
```

```py
print("I'm learning Python")    # OK, las comillas dobles nos salvan
```

Como ves, cuando hay un apóstrofe, es mejor usar comillas dobles para que Python no se líe.

* **Comillas dobles dentro del texto:** ¿Y si quieres poner comillas dobles dentro del texto? Pues entonces usa comillas simples:

```py
print('May dice que "Python es genial"')    # OK
```

Fácil, ¿no? ¡Un truco sencillo para evitar errores tontos!

* **Caracteres de escape:** si necesitas usar el mismo tipo de comillas dentro y fuera de la cadena, no hay problema. Puedes usar un carácter de escape (\) para decirle a Python que ignore la comilla que va dentro del texto:

```py
print("May dice que \"Python es genial\"")  # Comillas dentro del texto, sin dramas
```

En conclusión, usa comillas dobles cuando haya apóstrofes, y comillas simples cuando haya comillas dobles en el texto. ¡Así te ahorrarás dolores de cabeza!

## 2. Arte ASCII

El arte ASCII es una forma de crear imágenes utilizando únicamente caracteres del conjunto ASCII, que es un estándar de codificación de caracteres. 

A través de la disposición inteligente de los caracteres, se forman patrones y figuras que crean una ilusión visual de imágenes. 

Vamos a crear... ¡la imagen de un perro!

```py
print("o----'")
print(" ||||")
```

Observa que si en este caso usamos comillas simples en la primera instrucción, nos dará un error. ¿Por qué?

Si lo prefieres, puedes usar tres comillas `'''`en lugar de una, permitiéndote imprimir múltiples líneas de texto con una sentencia `print()`:

```py
print('''
o----'
 ||||
''')
```

```py
print('''
 /\_/\
(o . o)
 > ^ <
''')
```

## 3. Operaciones matemáticas

Operaciones matemáticas, precedencia de operadores


## 4. Interacción con el usuario con input()


## Es tu turno 

