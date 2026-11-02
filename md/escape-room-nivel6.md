# NEXUS: Protocolo de emergencia

## Situación inicial

Son las 08:42. En la **estación de investigación NEXUS** se ha producido un fallo general de seguridad. El sistema ha bloqueado las comunicaciones, ha desconectado varios módulos y ha activado el protocolo de evacuación.

El personal de la estación está a salvo en el refugio, pero el sistema central no responde. Para recuperar el control es necesario superar cinco comprobaciones de seguridad.

El ordenador central os irá proporcionando informes de lo sucedido. En ellos encontraréis la información necesaria para resolver cada prueba.

**Vuestra misión:** analizar los informes, desarrollar los programas Python necesarios y conseguir los códigos que permitan avanzar.

### Normas de la misión

- Trabajad en equipo y aseguraos de que todos comprendéis cada solución.
- Antes de programar, identificad qué datos necesitáis y organizadlos.
- Cada prueba debe resolverse mediante un programa Python.
- Ejecutad el programa y comprobad que el resultado es correcto.
- Introducid el código obtenido en el cuestionario correspondiente de AULES.
- No avancéis a la siguiente prueba hasta que el sistema confirme que habéis superado la anterior.

---

## PRUEBA 1. Restablecer la energía

<sub>Terminal de mantenimiento · 08:46</sub>

El fallo de seguridad ha desconectado la alimentación principal. La estación dispone de tres generadores auxiliares, pero el informe de mantenimiento advierte de que no todos pueden utilizarse.

**Informe de mantenimiento**

> Durante la última revisión se registraron los siguientes datos:
>
> - El generador **ALFA** estaba funcionando correctamente y proporcionaba 12 unidades de energía.
> - El generador **BETA** proporcionaba 8 unidades, pero se encontraba en estado inestable. El técnico recomendó no conectarlo.
> - El generador **GAMMA** estaba funcionando correctamente y proporcionaba 15 unidades de energía.
>
> El sistema de emergencia solo permite utilizar generadores que estén en estado estable. La energía de los generadores inestables debe descartarse.

**Lo que tenéis que hacer**

1. Analizad el informe e identificad qué generadores pueden utilizarse.
2. Cread un programa que calcule la energía total disponible.
3. Mostrad por pantalla el resultado con el mensaje `ENERGÍA DISPONIBLE:`.
4. El resultado numérico será el código necesario para desbloquear la siguiente terminal.

Guardad el programa como `prueba1.py`.

---

## PRUEBA 2. Recuperar las comunicaciones

<sub>Terminal de comunicaciones · 08:53</sub>

La alimentación auxiliar ha permitido encender el sistema de comunicaciones. Sin embargo, la señal recibida es débil y contiene interferencias.

El equipo de comunicaciones ha recuperado el siguiente registro:

**Informe de recepción**

> Se han recibido nueve paquetes de datos, numerados consecutivamente del 1 al 9. El sistema ha conseguido recuperar un valor numérico de cada paquete:
>
> | Paquete | Valor recibido |
> |---:|---:|
> | 1 | 8 |
> | 2 | 3 |
> | 3 | 1 |
> | 4 | 9 |
> | 5 | 4 |
> | 6 | 7 |
> | 7 | 2 |
> | 8 | 6 |
> | 9 | 5 |
>
> El técnico de comunicaciones explica que la interferencia afecta a los paquetes impares. Los paquetes pares contienen la información válida y deben utilizarse para reconstruir la señal.

**Lo que tenéis que hacer**

1. Cread una lista con los valores recibidos, respetando el orden de los paquetes.
2. Recuperad únicamente los valores correspondientes a los paquetes pares. No debéis seleccionar los valores uno a uno: utilizad una operación sobre la lista que permita obtenerlos directamente.
3. Calculad la suma de los valores recuperados.
4. Mostrad por pantalla el mensaje `SEÑAL RECUPERADA:` seguido del resultado.

Guardad el programa como `prueba2.py`. El resultado numérico será el siguiente código de acceso.

---

## PRUEBA 3. Comprobar las cápsulas de evacuación

<sub>Centro de evacuación · 09:02</sub>

Las comunicaciones vuelven a funcionar. El sistema central informa de que hay varias cápsulas de evacuación preparadas, pero no todas son seguras.

Antes de autorizar la evacuación, es necesario revisar el manifiesto de las cápsulas.

**Informe de inspección**

> El equipo de seguridad ha registrado los siguientes datos:
>
> - **ASTER:** llegó a las 02:10. Dispone de 14 unidades de energía y su precinto está intacto.
> - **BOREAL:** llegó a las 03:15. Dispone de 21 unidades de energía y su precinto está intacto.
> - **CERES:** llegó a las 01:45. Dispone de 18 unidades de energía, pero su precinto está dañado.
> - **DRACO:** llegó a las 02:50. Dispone de 25 unidades de energía y su precinto está intacto.
> - **EOS:** llegó a las 00:55. Dispone de 16 unidades de energía y su precinto está intacto.
> - **FENIX:** llegó a las 02:20. Dispone de 30 unidades de energía y su precinto está intacto.
> - **GAIA:** llegó a las 01:30. Dispone de 11 unidades de energía, pero su precinto está dañado.
>
> El protocolo de evacuación establece que una cápsula solo puede utilizarse si cumple **las tres condiciones siguientes**:
>
> - Ha llegado antes de las 03:00.
> - Tiene al menos 15 unidades de energía.
> - Su precinto está intacto.
>
> El sistema necesita conocer la energía total disponible en las cápsulas autorizadas y cuántas cápsulas cumplen los requisitos. Para generar el código de validación, hay que sumar ambos resultados.

**Lo que tenéis que hacer**

1. Extraed del informe los datos de las siete cápsulas.
2. Organizadlos en listas relacionadas: una para los nombres, otra para las horas de llegada, otra para la energía y otra para el estado de los precintos.
3. Recorred las cápsulas y comprobad si cada una cumple las tres condiciones del protocolo.
4. Para las cápsulas válidas, acumulad su energía y contabilizad cuántas hay.
5. Calculad el código de validación sumando la energía total y el número de cápsulas autorizadas.
6. Mostrad por pantalla el mensaje `CÓDIGO DE EVACUACIÓN:` seguido del resultado.

**Importante:** una cápsula solo es válida si cumple todas las condiciones, no basta con cumplir una o dos.

Guardad el programa como `prueba3.py`.

---

## PRUEBA 4. Reconstruir el inventario de emergencia

<sub>Almacén técnico · 09:14</sub>

El sistema ha autorizado las cápsulas necesarias para la evacuación. Ahora hay que comprobar que el almacén dispone de los componentes necesarios para activar el protocolo.

El inventario informático quedó parcialmente desactualizado durante el fallo.

**Informe de incidencias del almacén**

> El último inventario registrado contenía los siguientes componentes:
>
> | Componente | Unidades registradas |
> |---|---:|
> | Batería | 3 |
> | Cable | 8 |
> | Fusible | 2 |
> | Llave de seguridad | 1 |
> | Sensor | 5 |
>
> Tras revisar el almacén, el técnico ha comunicado tres incidencias:
>
> - Los dos fusibles están dañados y deben retirarse del inventario.
> - La llave de seguridad se ha perdido y debe eliminarse del registro.
> - Ha llegado un paquete con dos unidades adicionales de cable, que deben incorporarse al inventario.
>
> El sistema necesita conocer el número total de unidades disponibles después de actualizar el inventario.

**Lo que tenéis que hacer**

1. Cread dos listas relacionadas: una con los nombres de los componentes y otra con sus cantidades.
2. Actualizad ambas listas según las incidencias del informe.
   - Cuando eliminéis un componente, debéis eliminar también su cantidad correspondiente.
   - Cuando aumente la cantidad de un componente, debéis modificar el valor correspondiente en la lista de cantidades.
3. Calculad el número total de unidades disponibles.
4. Mostrad por pantalla el mensaje `UNIDADES DISPONIBLES:` seguido del resultado.

Guardad el programa como `prueba4.py`.

---

## PRUEBA 5. Activar el protocolo de restauración

<sub>Terminal central · 09:25</sub>

La estación ya dispone de energía, las comunicaciones están recuperadas, las cápsulas han sido verificadas y el inventario está actualizado.

Solo queda una última comprobación: demostrar que el equipo ha obtenido correctamente los cuatro códigos anteriores.

El sistema central muestra el siguiente mensaje:

**PROTOCOLO DE SEGURIDAD FINAL**

> Para restaurar el sistema es necesario introducir el código maestro.
>
> El código maestro se obtiene sumando los cuatro códigos conseguidos durante las pruebas anteriores.
>
> Por seguridad, el sistema solo permite tres intentos. Si el código introducido es correcto, se restaurará el sistema. Si se agotan los tres intentos sin introducir el código correcto, el acceso quedará bloqueado.

**Lo que tenéis que hacer**

1. Cread una lista con los cuatro códigos obtenidos en las pruebas anteriores.
2. Calculad el código maestro sumando los valores de esa lista.
3. Desarrollad un programa que solicite el código maestro al usuario.
4. El programa debe permitir un máximo de tres intentos.
5. Si el código introducido es correcto, debe mostrar `PROTOCOLO RESTAURADO` y finalizar.
6. Si se agotan los tres intentos, debe mostrar `ACCESO BLOQUEADO`.

Guardad el programa como `prueba5.py`.

**Cuando el sistema confirme la restauración, habréis completado la misión.**

---

## Entrega final

Cada equipo debe entregar en AULES los cinco archivos Python:

- `prueba1.py`
- `prueba2.py`
- `prueba3.py`
- `prueba4.py`
- `prueba5.py`

Los programas deben estar completos y funcionar correctamente. Durante la revisión, cualquier integrante del equipo podrá tener que explicar cómo ha obtenido los datos, qué operaciones ha realizado y por qué ha utilizado esas estructuras de programación.