# 

Más uso del print comillas
### 5.1 Sobre el uso de comillas

En Python, puedes usar comillas simples (' ') o comillas dobles (" ") para escribir texto, y funcionan igual. Entonces, ¿por qué tener las dos opciones? La respuesta es simple: te ahorran problemas cuando tienes apóstrofes o comillas dentro del texto.

* Si escribes algo como *I'm learning Python*, las comillas simples causarían problemas porque Python pensaría que el apóstrofe cierra la cadena. La solución: usa comillas dobles y el apóstrofe no dará problemas.

```py
print('I'm learning Python')    # Error
print("I'm learning Python")    # OK
```
* Si necesitas usar comillas dentro de la cadena, como en El profesor dijo: "Python es genial", usa comillas simples alrededor de todo:

Usa comillas dobles cuando haya apóstrofes, y comillas simples cuando haya comillas dobles en el texto. ¡Así te ahorras errores



ARTE ASCII
El arte ASCII es una forma de crear imágenes utilizando únicamente caracteres del conjunto ASCII, que es un estándar de codificación de caracteres. A través de la disposición inteligente de los caracteres, se forman patrones y figuras que crean una ilusión visual de imágenes. Añade un poco de arte a tu programa, ¡la imagen de un perro!

```py
print("o----'")
print(" ||||")
```

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
Operaciones matemáticas, precedencia de operadores
