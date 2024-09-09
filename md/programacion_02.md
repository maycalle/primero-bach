# Imprime, calcula y pregunta

En esta sesión vamos a aprender más detalles sobre el comando `print()`, exploraremos el arte ASCII (sí, ¡dibujos con caracteres!), trabajaremos con operadores matemáticos y, lo más importante, ¡aprender a interactuar con el usuario con `input()`! 

## 1. Más sobre print()

Ya sabes cómo usar `print()` para mostrar mensajes en pantalla, pero ahora vamos a aprender cómo manejar situaciones un poco más complejas, como incluir apóstrofes o comillas dentro del texto. 

Python te permite usar tanto comillas simples (' ') como comillas dobles (" "), y aunque funcionan de forma similar, hay algunos detalles importantes que debes conocer.

* **Comillas simples vs. comillas dobles:** Puedes usar cualquiera de las dos para mostrar texto, pero si dentro de tu texto tienes un apóstrofe, ¡atención! Python podría confundirse si usas comillas simples:

```py
print('I'm learning Python')    # ¡Error! Python se confunde con el apóstrofe
```

```py
print("I'm learning Python")    # OK, las comillas dobles nos salvan
```

Como ves, cuando hay un apóstrofe, es mejor usar comillas dobles para que Python no se líe.

* **Comillas dobles dentro del texto:** si tu texto incluye comillas dobles, la solución es usar comillas simples alrededor del texto:

```py
print('May dice que "Python es genial"')    # OK
```

* **Caracteres de escape:** pero, ¿qué pasa si necesitas usar el mismo tipo de comillas dentro y fuera del texto? No te preocupes, puedes usar el carácter de escape (\) para decirle a Python que ignore la comilla y la trate como parte del texto:

```py
print("May dice que \"Python es genial\"")  # Comillas dentro del texto, sin dramas
```

De esta forma, puedes usar el tipo de comillas que quieras sin generar errores.

En conclusión, usa comillas dobles si tu texto contiene apóstrofes, y comillas simples si contiene comillas dobles. Y si necesitas el mismo tipo de comillas dentro y fuera, el carácter de escape te sacará de apuros. ¡Así te ahorrarás dolores de cabeza!

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

