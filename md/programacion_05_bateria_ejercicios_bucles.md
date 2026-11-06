# Cuaderno de ejercicios de bucles

En este bloque vamos a trabajar con `for` y `while`. No se trata solamente de repetir instrucciones, sino de entender cómo controlar las repeticiones y cómo cambia la información durante la ejecución.

## Ejercicio 1. El robot explorador

Un robot se encuentra en una posición inicial y debe avanzar por un pasillo.

Cada movimiento se representa mediante un número entero que indica los metros que avanza.

Crea un programa que:
- Pregunte cuántos movimientos debe realizar.
- En cada movimiento, solicite los metros que ha avanzado.
- Calcule la distancia total recorrida.
- Al terminar, muestre la distancia acumulada.

**Ejemplo de ejecución:** 

```py
¿Cuántos movimientos realizará el robot? 4

Movimiento 1: 3
Movimiento 2: 5
Movimiento 3: 2
Movimiento 4: 4

Distancia total: 14 metros
```

> **Reflexiona**: ¿Por qué necesitas una variable que vaya acumulando la distancia? ¿Qué ocurriría si inicializaras esa variable dentro del bucle?> 

## Ejercicio 2. Control de aforo

Un recinto tiene una capacidad máxima de 100 personas.

El programa debe solicitar cuántas personas entran en cada grupo. Después de cada entrada, debe actualizar el número de personas que hay dentro.

El proceso finalizará cuando:
- Se alcance o supere el aforo máximo.
- Se introduzca un número negativo para indicar que no entran más grupos.

Al terminar, muestra cuántas personas hay en el recinto y si se ha superado el aforo.

> **Reflexiona:** ¿Sabes de antemano cuántos grupos entrarán? ¿Qué tipo de bucle resulta más adecuado?

## Ejercicio 3. Consumo de combustible

Un vehículo realiza un viaje y el conductor quiere conocer el consumo total.

El programa solicitará:
- El número de kilómetros recorridos en cada tramo.
- Los litros de combustible consumidos en ese tramo.

Primero se preguntará cuántos tramos tiene el viaje.

Al terminar, mostrará:
- Kilómetros totales.
- Litros consumidos.
- Consumo medio en litros cada 100 kilómetros.

Para calcular el consumo medio utiliza esta fórmula: (litros consumidos/kilómetros recorridos) x 100

## Ejercicio 4. El cajero automático

Un cajero automático dispone inicialmente de 500 euros.

El usuario puede solicitar retiradas de dinero sucesivas.

El programa debe:
- Solicitar la cantidad que desea retirar.
- Comprobar que la cantidad es positiva.
- Comprobar que no supera el saldo disponible.
- Si la operación es válida, descontar el importe.
- Si no es válida, mostrar el motivo.
El proceso termina cuando el usuario introduce 0.

Al finalizar, muestra el saldo restante.

> **Reflexiona:** ¿Qué instrucciones se repiten? ¿Qué instrucciones solamente deben ejecutarse cuando la operación es válida?