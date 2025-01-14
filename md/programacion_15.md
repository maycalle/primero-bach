# 2. Machine Learning y Deep Learning

La Inteligencia Artificial (IA) ha evolucionado de forma sorprendente en los últimos años, impactando en numerosos campos como la medicina, la conducción autónoma y el reconocimiento de voz. Dentro de la IA, dos de las
ramas más importantes son **Machine Learning (ML)** y **Deep Learning (DL)**. Ambas permiten a las máquinas aprender a partir de datos, pero lo hacen con enfoques distintos.

En esta unidad exploraremos:
* Qué es el *machine learning* y en qué se diferencia de la programación tradicional.
* Tipos de *machine learning*: supervisado, no supervisado y por refuerzo.
* Qué es el *deep learning* y en qué se diferencia del *machine learning*.
* Entrenaremos modelos básicos con *Teachable Machine*.
* Integraremos IA en Python para clasificar imágenes.

Al final, comprenderás cómo hacer que una máquina aprenda y habrás desarrollado tu propio modelo con Python. ¡Vamos allá!

## 2.1  ¿Qué es el Machine Learning?

La programación tradicional se basa en escribir reglas explícitas para resolver problemas. En cambio, **Machine Learning** permite a una máquina **aprender patrones a partir de datos**, sin necesidad de ser programada de forma explícita.

<div align="center">
    <img src="/primero-bach/img/saa.png" width="80%">
</div>

Por ejemplo, si queremos que un programa distinga entre perros y gatos, con programación tradicional deberíamos escribir una lista de reglas (como "los perros tienen hocicos más largos"), lo cual puede ser complicado y poco preciso. Con Machine Learning, simplemente le mostramos muchas imágenes de perros y gatos con sus etiquetas correspondientes, y el modelo aprende a diferenciarlos por sí mismo.

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

La clave del *Deep Learning* es su capacidad para procesar grandes volúmenes de datos y extraer características complejas sin necesidad de intervención manual.

Por ejemplo, en *Machine Learning* tradicional, si queremos que un modelo reconozca caras en fotos, primero debemos seleccionar características clave como el contorno de los ojos o la forma de la nariz. En cambio, un modelo de *Deep Learning* puede aprender esas características por sí solo, gracias a sus múltiples capas de neuronas artificiales.

<div align="center">
    <img src="/primero-bach/img/ml_vs_dl.png" width="70%">
</div>

### 2.2.1 ¿Cómo funciona una red neuronal?

Una **red neuronal artificial** es un modelo matemático inspirado en el cerebro humano. Está formada por neuronas artificiales, organizadas en capas: una *capa de entrada*, varias *capas ocultas* y una *capa de salida*. 

Cada neurona recibe datos, los procesa y los transmite a las siguientes neuronas a través de conexiones ponderadas. A medida que el modelo se entrena con datos, ajusta los pesos de estas conexiones para mejorar sus predicciones. 

Este proceso de ajuste se llama **retropropagación** y permite que la red neuronal aprenda patrones complejos sin intervención manual.

Si os gusta este tema y queréis profundizar más en él, os recomiendo que sigáis el [canal DotCSV](https://www.youtube.com/@DotCSV). 

Aquí tenéis uno de sus vídeos en los que explica qué es una neurona. En este [enlace](https://www.youtube.com/playlist?list=PL-Ogd76BhmcB9OjPucsnc2-piEE96jJDQ) podéis acceder a una serie de vídeos más avanzados sobre el funcionamiento de las redes neuronales. 

<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/MRIv2IwFTPg?si=W-jc6Py5se-nXoQq" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

> 📌 **DATO CURIOSO:** Google Photos usa redes neuronales para reconocer rostros y objetos en tus fotos, permitiéndote buscar imágenes escribiendo palabras clave como "playa" o "perro" sin necesidad de etiquetarlas manualmente.

## 2.3 Entrenamiento de modelos con Teachable Machine

Para comprender mejor estos conceptos, utilizaremos [**Teachable Machine**](https://teachablemachine.withgoogle.com/), una herramienta de Google que permite entrenar modelos de Machine Learning de manera sencilla. 

Con esta plataforma, podremos crear modelos que clasifiquen imágenes, sonidos o posturas sin necesidad de escribir
código.

<div align="center">
    <img src="/primero-bach/img/teachable_machine1.png" width="80%">
</div>


**Paso 1. Entrenar un modelo en Teachable Machine**

1. Accede a *Teachable Machine*
2. Elige *Imagen* y crea dos clases:
      * "Pulgar Arriba"
      * "Pulgar Abajo"
3. Sube varias imágenes para cada clase y entrena el modelo.
4. Descarga el modelo en formato *TensorFlow.js*

**Paso 2. Usar el modelo en Python**

```py
import tensorflow as tf
import numpy as np
from tensorflow.keras.models import load_model
from PIL import Image

# Cargar el modelo entrenado
model = load_model("model.h5")

# Cargar una imagen nueva
imagen = Image.open("pulgar_arriba.jpg").resize((224, 224))
datos = np.array(imagen) / 255.0
prediccion = model.predict(np.expand_dims(datos, axis=0))

# Interpretar resultados
print("Predicción:", "Pulgar Arriba" if prediccion[0][0] > 0.5 else "Pulgar Abajo")
```

## RESUMEN

✅ El Machine Learning permite a las máquinas aprender patrones a partir de datos.<br>
✅ Existen tres tipos principales: supervisado, no supervisado y por refuerzo.<br>
✅ Se usa en numerosos sectores: salud, finanzas, entretenimiento, redes sociales, etc.<br>
✅ Requiere datos limpios, entrenamiento y evaluación continua.


