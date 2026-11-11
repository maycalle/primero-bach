# HTLM EXAM 26-27 SMR

- Name: 
- Group: 

## Ejercicio 1. Listas y formato de texto (2,5 puntos)

Escribe el código HTML necesario para representar la siguiente información:

**Elementos químicos**

1. Metales
   - Hierro
   - Cobre
   - Aluminio
2. No metales
   - Oxígeno
   - Carbono

Añade, después de la lista, el siguiente párrafo:

"Los elementos químicos se clasifican según sus propiedades. Algunos, como el hierro, son muy utilizados en la industria".

**Requisitos de formato:**

- El texto "Elementos químicos" que aparece al principio debe ser el encabezado principal de la página.
- El texto "elementos químicos" que aparece en el párrafo debe aparecer en negrita.
- "propiedades" debe aparecer en cursiva.
- "hierro" debe aparecer resaltada en amarillo (como si la hubiéramos destacado con un rotulador fosforito)

## Ejercicio 2. Listas (1,5 puntos)

Escribe el código HTML necesario para mostrar la siguiente información:

<dl>
    <dt>CPU</dt>
    <dd>The main processor of the computer.</dd>
    <dt>RAM</dt>
    <dd>Temporary memory used while the computer is running.</dd>
    <dt>SSD</dt>
    <dd>A fast storage device that uses flash memory. </dd>
<dl>

## Ejercicio 3. Construye una tabla HTML (2,5 puntos)

Escribe el código HTML necesario para crear una tabla con la siguiente información:

<table border="1">
    <caption>Programa del festival</caption>
    <thead>
        <tr>
            <th>Día</th>
            <th>Actuación</th>
            <th>Hora</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="2">Viernes</td>
            <td>Grupo A</td>
            <td>20:00</td>
        </tr>
        <tr>
            <td>Grupo B</td>
            <td>22:00</td>
        </tr>
        <tr>
            <td>Sábado</td>
            <td colspan="2">Descanso</td>
        </tr>
    </tbody>
</table>

**Requisitos:**

- La tabla debe incluir una sección específica para la fila de encabezados y otra para las filas que contienen los datos.
- La primera fila debe identificar las columnas mediante celdas de encabezado.
- Debes utilizar las combinaciones de celdas indicadas en el ejemplo.

## Ejercicio 4. Imagen, enlace y formato de texto (3,5 puntos)

Escribe el código HTML necesario para realizar las siguientes tareas:

- Mostrar una imagen llamada `marte.jpg`, situada en la carpeta `imagenes`.
- La imagen debe tener el siguiente texto alternativo: "Superficie rojiza del planeta Marte" .
- La imagen debe tener un ancho de 300 píxeles y un alto de 400 píxeles.
- Al hacer clic sobre la imagen, se debe acceder a `https://science.nasa.gov/mars/`.
- Debajo de la imagen debe aparecer el texto: "Marte es conocido como el planeta rojo".
- Agrupa la imagen y el texto que aparece debajo en un mismo elemento, indicando que el texto es el pie o descripción de la imagen.

A continuación, añade un párrafo con el siguiente texto:

"La superficie de Marte tiene una temperatura media de -65°C y una extensión de 144.800.000 km². Su atmósfera contiene CO₂ y su gravedad es un 38 % de la terrestre."


