# Cuaderno de trabajo de bucles en Python

## Ejercicio 1. ¿Qué aparecerá por pantalla?

Sin ejecutar los programas, indica exactamente qué mostrarán.

- **Programa 1**

```py
for i in range(5):
    print(i)
```

Salida: 

<br><br><br><br><br>

- **Programa 2**

```py
for i in range(2, 7):
    print(i)
```

Salida: 

<br><br><br><br><br>

- **Programa 3:**

```py
for i in range(10, 0, -2):
    print(i)
```

Salida: 

<br><br><br><br><br>

- **Programa 4:**

```py
for i in range(4):
    print("Python")
    print(i)
```

Salida: 

<br><br><br><br><br>


## Ejercicio 2. Sigue la evolución de las variables

Completa las tablas indicando el valor de las variables en cada repetición.

- **Programa 1**

```py
contador = 0

for i in range(5):
    contador = contador + 2
    print(contador)
```

<table width="40%">
    <tr>
        <th>Iteración</th>
        <th>i</th>
        <th>contador</th>
    </tr>
    <tr>
        <td>1</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>4</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>5</td>
        <td></td>
        <td></td>
    </tr>
</table>

¿Qué valor tendrá **contador** al terminar?

<br><br><br><br><br><br><br><br>


- **Programa 2**

```py
suma = 0

for i in range(1, 5):
    suma = suma + i

print(suma)
```

<table width="40%">
    <tr>
        <th>Iteración</th>
        <th>i</th>
        <th>suma</th>
    </tr>
    <tr>
        <td>1</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>4</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>5</td>
        <td></td>
        <td></td>
    </tr>
</table>

¿Qué valores va tomando **suma**? ¿Qué muestra finalmente?

<br><br><br><br><br>

## Ejercicio 3. Encuentra el error

Los siguientes programas tienen errores. Explica qué ocurre y corrígelos.

- **Programa 1: queremos mostrar los números del 1 al 10.**

```py
for i in range(1, 10):
    print(i)
```

¿Qué hace?

<br><br>


¿Como se soluciona?

<br><br><br><br>




- **Programa 2: queremos mostrar cinco veces la palabra "Hola".**

```py
for i in range(5)
    print("Hola")
```

¿Qué hace?

<br><br>

¿Como se soluciona?

<br><br><br><br><br>


- **Programa 3: queremos contar desde 1 hasta 5.**

```py
contador = 1

while contador <= 5:
    print(contador)
```

¿Qué hace?

<br><br>

¿Como se soluciona?

<br><br><br><br><br>



- **Programa 4: queremos sumar los números del 1 al 5.**

```py
suma = 0

for i in range(1, 6):
    suma = i

print(suma)
```

¿Qué hace?

<br><br>

¿Como se soluciona?

<br><br><br><br><br>


## Ejercicio 4. Cuenta de diferentes formas

Crea cuatro programas independientes:

a) Muestra los números del 1 al 20.

b) Muestra los números pares del 2 al 30.

c) Muestra los números del 50 al 0, descendiendo de 5 en 5.

d) Pide un número al usuario y muestra su cuenta atrás hasta llegar a 0.

## Ejercicio 5. Contamos y acumulamos

Estos dos conceptos son fundamentales para resolver problemas con bucles.

a) Pide 5 números al usuario y muestra cuántos ha introducido.

b) Pide 5 números y calcula su suma.

c) Pide 5 números y calcula su media.

d) Pide 5 números y cuenta cuántos son positivos, cuántos negativos y cuántos son cero.

*Antes de programar, piensa qué variables necesitas y para qué sirve cada una.*




