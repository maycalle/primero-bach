# 2. Machine Learning y Deep Learning

La Inteligencia Artificial (IA) ha evolucionado de forma sorprendente en los últimos años, impactando en numerosos campos como la medicina, la conducción autónoma y el reconocimiento de voz. Dentro de la IA, dos de las
ramas más importantes son **Machine Learning (ML)** y **Deep Learning (DL)**. Ambas permiten a las máquinas aprender a partir de datos, pero lo hacen con enfoques distintos.

En esta unidad exploraremos:
* Qué es el *machine learning* y en qué se diferencia de la programación tradicional.
* Tipos de *machine learning*: supervisado, no supervisado y por refuerzo.
* Qué es el *deep learning* y en qué se diferencia del *machine learning*.
* Entrenaremos modelos básicos con *Teachable Machine*.

Al final, comprenderás cómo hacer que una máquina aprenda y habrás experimentado con modelos de clasificación. ¡Vamos allá!

## 2.1  ¿Qué es el Machine Learning?

La programación tradicional se basa en escribir reglas explícitas para resolver problemas. En cambio, **Machine Learning** permite a una máquina **aprender patrones a partir de datos**, sin necesidad de ser programada de forma explícita.

<div align="center">
    <img src="/primero-bach/img/saa.png" width="80%">
</div>

Por ejemplo: 
* Si queremos que un programa distinga entre perros y gatos, con programación tradicional deberíamos escribir una lista de reglas (como "los perros tienen hocicos más largos"), lo cual puede ser complicado y poco preciso. 
* Con *Machine Learning*, simplemente le mostramos muchas imágenes de perros y gatos con sus etiquetas correspondientes, y el modelo aprende a diferenciarlos por sí mismo.

Gracias a esta tecnología, los sistemas pueden mejorar su rendimiento a lo largo del tiempo, volviéndose más precisos conforme reciben más información.

> 📌 **DATO CURIOSO:** el primer programa de Machine Learning fue creado en 1959 por Arthur Samuel, quien desarrolló un sistema que aprendía a jugar al ajedrez mejorando con la práctica. Su algoritmo se volvió tan bueno que llegó a vencer a jugadores humanos experimentados.

### 2.1.2 Tipos de machine learning

El aprendizaje automático se divide en tres grandes categorías:

* **Aprendizaje supervisado**
    * En este enfoque, el modelo aprende a partir de **datos etiquetados**. Es decir, proporcionamos ejemplos con la respuesta correcta. 
    * Por ejemplo, si queremos que un sistema detecte si un correo electrónico es spam, le mostramos miles de ejemplos de correos spam y no spam para que reconozca patrones.
    
* **Aprendizaje no supervisado**
    * En este caso, el modelo **no tiene etiquetas** y debe encontrar patrones en los datos por sí mismo. 
    * Un ejemplo común es la segmentación de clientes,donde una empresa analiza los comportamientos de compra para agrupar a sus clientes en distintos perfiles sin saber previamente cuáles son estos perfiles.

* **Aprendizaje por refuerzo**
    * Este tipo de aprendizaje es similar a la forma en que aprendemos muchas cosas: **por ensayo y error**. Un sistema de aprendizaje por refuerzo interactúa con su entorno y recibe recompensas o castigos según sus acciones. 
    * Se usa, por ejemplo, en la creación de inteligencia artificial para videojuegos o en robots que aprenden a caminar.
  
> 🔍 **Ejercicio:** Observa los siguientes ejemplos y clasifícalos según su tipo de Machine Learning:
> * Un sistema de IA que detecta fraudes bancarios.
> * Un chatbot que aprende a responder preguntas a partir de conversaciones previas.
> * Un algoritmo que recomienda música según tus canciones favoritas.

## 2.2 ¿Qué es el Deep Learning y en qué se diferencia de Machine Learning?

El **Deep Learning** es una subcategoría dentro del Machine Learning que se basa en **redes neuronales artificiales** inspiradas en el cerebro humano. 

**Diferencias clave**

<table>
    <tr>
        <th>Machine Learning</th>
        <th>Deep Learning</th>
    </tr>
    <tr>
        <td>Necesita itnervención humana para identificar patrones</td>
        <td>Aprende patrones por sí mismo a través de redes neuronales</td>
    </tr>
    <tr>
        <td>Funciona bien con volúmenes pequeños o medianos de datos</td>
        <td>Necesita grandes cantidades de datos</td>
    </tr>
</table>

Como vemos, la clave del *Deep Learning* es su capacidad para procesar grandes volúmenes de datos y extraer características complejas sin necesidad de intervención manual.

Por ejemplo:
* En *Machine Learning* tradicional, para reconocer caras en fotos, primero seleccionamos características como el contorno de ojos o la forma de la nariz. 
* Un modelo de *Deep Learning* puede aprender esas características por sí solo, gracias a sus múltiples capas de neuronas artificiales.

<div align="center">
    <img src="/primero-bach/img/ml_vs_dl.png" width="70%">
</div>


### 2.2.1 ¿Cómo funciona una red neuronal?

Una **red neuronal artificial** es un modelo matemático inspirado en el cerebro humano. Está formada por neuronas artificiales, organizadas en capas: una *capa de entrada*, varias *capas ocultas* y una *capa de salida*. 

<div align="center">
    <img src="/primero-bach/img/red_neuronal.png" width="70%">
</div>

Cada neurona recibe datos, los procesa y los transmite a las siguientes neuronas a través de conexiones ponderadas. A medida que el modelo se entrena con datos, ajusta los pesos de estas conexiones para mejorar sus predicciones. 

Este proceso de ajuste se llama **retropropagación** y permite que la red neuronal aprenda patrones complejos sin intervención manual.

Si te interesa este tema y quieres profundizar más, te recomiendo el [canal DotCSV](https://www.youtube.com/@DotCSV) donde encontrarás contenido especializado sobre inteligencia artificial y redes neuronales.

Aquí tienes un vídeo en el que explica qué es una neurona artificial. 

<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/MRIv2IwFTPg?si=W-jc6Py5se-nXoQq" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

Además, en este [enlace](https://www.youtube.com/playlist?list=PL-Ogd76BhmcB9OjPucsnc2-piEE96jJDQ) puedes acceder a una serie de vídeos más avanzados sobre el funcionamiento de las redes neuronales.

> 📌 **DATO CURIOSO:** Google Photos usa redes neuronales para reconocer rostros y objetos en tus fotos, permitiéndote buscar imágenes escribiendo palabras clave como "playa" o "perro" sin necesidad de etiquetarlas manualmente.

## 2.3 Entrenamiento de modelos con Teachable Machine

Para comprender mejor estos conceptos, utilizaremos [**Teachable Machine**](https://teachablemachine.withgoogle.com/), una herramienta de Google que permite entrenar modelos de Machine Learning de manera sencilla. 

<div align="center">
    <img src="/primero-bach/img/teachable_machine1.png" width="80%">
</div>

Con esta plataforma, podremos crear modelos que clasifiquen imágenes, sonidos o posturas sin necesidad de escribir. 

En este caso, vamos a entrenar un **modelo para que clasifique imágenes que muestren un pulgar arriba o un pulgar abajo**. El modelo aprenderá a diferenciar estas imágenes a partir de ejemplos que le proporcionemos.

**Paso 1. Acceso a Teachable Machine**

   * Accede a *Teachable Machine* > *Primeros pasos*
   * Selecciona un *Proyecto de imagen* > *Modelo de imagen estándar*

<div align="center">
    <img src="/primero-bach/img/teachable_machine2.png" width="70%">
</div>

**Paso 2. Creación de las clases**

   * Por defecto, aparecen creadas dos clases. Renómbralas como "PulgarArriba" y "PulgarAbajo" (es recomendable no dejar espacios en blanco en los nombres de las clases)

**Paso 3. Recoger imágnes**

  * Para entrenar el modelo, necesitamos proporcionar ejemplos de cada clase. Hay dos formas de añadir imágenes:

      * 📸 Capturar imágenes con la webcam
      * 📁 Subir imágenes desde el ordenador

  * Consejos para recoger buenas muestras:<br>
    ✅ Toma al menos 50 imágenes por cada clase.<br>
    ✅ Varía el ángulo y la distancia para mejorar la precisión del modelo.<br>
    ✅ Usa buena iluminación y un fondo claro.<br>

**Paso 4. Entrenamiento del modelo**

Una vez tengamos las imágenes, vamos a entrenar el modelo. En "Avanzado", encontrarás algunos parámetros que puedes ajustar para mejorar la precisión del modelo.

🔹 **Épocas (epochs)**: número de veces que el modelo revisará todas las imágenes para aprender. *Valores recomendados:* 
  * 10-20 épocas si tienes muchas imágenes 
  * 30-50 épocas si tienes pocas imágenes.

🔹 **Tamaño del Lote (batch size)**: cantidad de imágenes que el modelo analizará al mismo tiempo en cada iteración. *Valores recomendados:*
  * 16 o 32 imágenes por lote para equilibrio entre velocidad y precisión.

🔹 **Tasa de Aprendizaje (learning rate)**: velocidad con la que el modelo ajusta su aprendizaje en cada iteración. *Valores recomendados:*
  * 0.001 o 0.0001 (valores altos pueden hacer que el modelo aprenda rápido pero mal, valores bajos pueden hacer que aprenda lento pero mejor).

Para empezar, usa:
* **Épocas:** 30
* **Tamaño del lote:** 16
* **Tasa de aprendizaje:** 0.001

**Paso 5. Prueba del modelo**

Prueba el modelo proporcionando una imagen diferente, por ejemplo, con el pulgar de otro compañero/a y en diferentes posiciones y observa el resultado. Si ves que el modelo no es muy preciso, prueba con imágenes diferentes o cambia los valores de entrenamiento (épocas, lotes, ...) 
 
<div align="center">
    <img src="/primero-bach/img/teachable_machine5.png" width="40%" height="60%">
</div>

## 2.4 Análisis de Sentimientos con Python

El análisis de sentimientos es una aplicación popular del*Machine Learning* que permite determinar el tono de un texto, como si es positivo, negativo o neutral. 

Este tipo de análisis se utiliza en redes sociales, reseñas de productos y otros contextos donde es útil entender las emociones detrás de las palabras.

En este apartado, aprenderemos cómo usar la **librería TextBlob** para analizar el sentimiento de una frase escrita por el usuario.

### 2.4.1 Breve descripción del programa

El programa que implementaremos pedirá al usuario que introduzca una frase. Luego, con la ayuda de **TextBlob**, calculará dos valores importantes:

* **Polaridad:** determina si el texto es positivo (valores cercanos a 1), negativo (valores cercanos a -1) o neutral (0).
* **Subjetividad:** indica si el texto es objetivo (valores cercanos a 0) o subjetivo (valores cercanos a 1).

### 2.4.2 Código del programa

```py
from textblob import TextBlob

frase = input("Escribe una frase:\n")

resultado = TextBlob(frase)
print("Polaridad:", resultado.polarity)
print("Subjetividad:", resultado.subjectivity)
```

### 2.4.3 Explicación detallada del código

1. **Importación de la librería TextBlob**
    * *from textblob import TextBlob*
    * TextBlob es una librería de Python que facilita el procesamiento de texto, como el análisis de sentimientos o la corrección gramatical. Asegúrate de instalarla antes de ejecutar el código con: ***pip install textblob***
2. **Solicitar una frase al usuario**
    * *frase = input("Escribe una frase:\n")*
3. **Crear un objeto TextBlob**
    * *resultado = TextBlob(frase)*
    * La función TextBlob analiza automáticamente el texto introducido.
4. **Obtener la polaridad y la subjetividad**
    * *resultado.polarity*: devuelve un valor entre -1 (muy negativo) y 1 (muy positivo).
    * *resultado.subjectivity*: devuelve un valor entre 0 (muy objetivo) y 1 (muy subjetivo).

> 🔍 **Ejercicio:** 
> 1. Escribe varias frases de ejemplo y analiza los resultados.
> 2. Reflexiona sobre las aplicaciones del análisis de sentimientos, como:
> * ¿Cómo se podrían usar estos datos en redes sociales?
> * ¿Qué tan precisos son los resultados en frases irónicas o ambiguas?

## RESUMEN

✅ El Machine Learning permite a las máquinas aprender patrones a partir de datos.<br>
✅ Existen tres tipos principales: supervisado, no supervisado y por refuerzo.<br>
✅ Requiere datos limpios, entrenamiento y evaluación continua.


