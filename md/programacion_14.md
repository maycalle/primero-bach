# 1. Introducción a la Inteligencia Artificial

En esta unidad exploraremos qué es la **Inteligencia Artificial (*IA*)** y cómo se utiliza en aplicaciones cotidianas. Aprenderemos conceptos clave como **Machine Learning** y **Deep Learning**, entre otros.

A través de actividades prácticas:
* Entrenaremos modelos básicos con *Teachable Machine*.
* Los integraremos en programas de Python para clasificar imágenes.
* Reflexionaremos sobre las posibilidades, limitaciones y riesgos éticos de la IA.
  
Al finalizar, comprenderás cómo funcionan estas tecnologías y habrás creado tu primer modelo de IA.

## 1.1 ¿Qué es la IA?

La **inteligencia artificial (IA)** es una rama de la informática que permite a las máquinas realizar tareas que normalmente requieren inteligencia humana, como aprender, razonar, resolver problemas o tomar decisiones. En pocas palabras, es como enseñar a las máquinas a *pensar y aprender por sí mismas*, pero siempre dentro de las tareas específicas para las que han sido entrenadas.

**¿Dónde encontramos la IA?**

La IA está cada vez más presente en nuestra vida diaria, aunque a veces no lo notemos. Aquí tienes algunos ejemplos prácticos:

* **Reconocimiento facial:** tu móvil desbloquea la pantalla al detectar tu rostro.
* **Asistentes virtuales:** Siri o Alexa responden preguntas y realizan tareas con tu voz.
* **Sistemas de recomendaciones:** Netflix, Spotify o YouTube analizan lo que te gusta para sugerirte contenido.
* **Conducción autónoma:** los coches como los de Tesla utilizan IA para detectar señales de tráfico, peatones y otros vehículos.

También se utiliza en videojuegos, donde los personajes controlados por la máquina reaccionan a tus movimientos, haciendo el juego más dinámico y en redes sociales, priorizando publicaciones basándose en lo que más interactúas.

## 1.2 ¿Cómo funciona la IA?

La inteligencia artificial necesita datos para aprender (*datos de entrenamiento*), y estos datos deben pasar por un proceso que los transforme en conocimiento útil. Este proceso se puede resumir en cuatro pasos:

1. **Recoger y preparar los datos:** se toman los datos de diferentes fuentes y se organizan para que sean comprensibles por la máquina. Por ejemplo, transformar fotos o textos en números que el sistema pueda analizar.
2. **Almacenar los datos como conocimiento:** una vez procesados, los datos se guardan de forma que puedan ser consultados cuando sea necesario. Esto permite a la máquina *recordar* la información.
3. **Analizar e interpretar:** el sistema analiza los datos almacenados para encontrar patrones o entender relaciones. Por ejemplo, aprender que una pelota es redonda observando muchas imágenes de pelotas.
4. **Generar nuevo conocimiento:** la IA utiliza lo aprendido para hacer deducciones o predicciones. A este proceso se le llama *inferencia*, y es lo que hace que un programa sea realmente *inteligente*. Por ejemplo, predecir que mañana lloverá basándose en datos meteorológicos.

#### 1.2.1 El modelo y la importancia de los datos de entrenamiento

El resultado del aprendizaje de la IA se llama **modelo**. Un modelo es el sistema entrenado que utiliza los datos procesados para tomar decisiones o hacer predicciones.

El modelo será tan bueno como los datos que reciba. Si los datos son incompletos, incorrectos o están sesgados, el modelo puede cometer errores importantes. 

Por ejemplo:
* Un modelo entrenado con imágenes poco claras no podrá identificar correctamente objetos en fotos nuevas.
* Un modelo que use datos con prejuicios podría tomar decisiones injustas, como discriminar en la selección de candidatos para un trabajo.

Por eso, al trabajar con IA, es fundamental utilizar datos de calidad, variados y bien preparados para que el modelo sea confiable y efectivo.

#### 1.2.2 Machine learning

El **aprendizaje automático**, también llamado **machine learning**, es una parte muy importante de la inteligencia artificial. De hecho, muchas veces se confunden ambos términos porque están muy relacionados. 

Básicamente, el aprendizaje automático es la capacidad que tienen algunos programas o sistemas para mejorar su funcionamiento con el tiempo, sin necesidad de que una persona los programe constantemente. Esto se logra porque el sistema analiza datos que va acumulando o recibe indicaciones externas sobre si está haciendo bien o mal su tarea. Así, puede adaptarse y volverse más eficiente en la resolución de problemas.

Para entender el aprendizaje automático, primero hay que diferenciarlo de la programación tradicional. En un programa convencional, el programador escribe un conjunto de reglas claras (como condiciones, bucles o instrucciones) para que, a partir de unos datos de entrada, se obtenga un resultado específico.

En cambio, en el aprendizaje automático, el enfoque es distinto: en lugar de definir reglas manualmente, se le proporciona al sistema datos de entrada junto con los resultados que deberían obtenerse. A partir de esta información, el sistema aprende por sí mismo a identificar patrones y deducir las reglas necesarias para predecir nuevos resultados cuando reciba datos diferentes en el futuro.

<div align="center">
    <img src="img/saa.png" width="80%">
</div>

**Tipos de aprendizaje automático**

En el aprendizaje automático, existen diferentes maneras en las que un sistema puede aprender. Se pueden clasificar en cuatro tipos principales:

* **Aprendizaje supervisado:** en este tipo de aprendizaje, el sistema recibe información sobre si está realizando bien o mal su tarea. Es decir, se le proporcionan datos junto con sus respuestas correctas para que aprenda a identificar patrones. Este es el método más común en la actualidad y se usa, por ejemplo, en aplicaciones de reconocimiento de imágenes o en asistentes virtuales que aprenden a responder preguntas.

* **Aprendizaje no supervisado:** a diferencia del anterior, aquí el sistema no recibe respuestas correctas previamente, sino que debe encontrar patrones por sí mismo en los datos. Un buen ejemplo de esto son los algoritmos que predicen los gustos de un usuario basándose en la música que escucha o las páginas web que visita, recomendándole contenido similar.

* **Aprendizaje semi-supervisado:** este método combina las estrategias anteriores. Al principio, el sistema recibe algunas respuestas correctas (aprendizaje supervisado) para orientarse, pero luego empieza a trabajar de manera más autónoma (aprendizaje no supervisado). También puede ocurrir al revés: el sistema primero agrupa datos similares sin ayuda y, posteriormente, una persona etiqueta esas categorías para mejorar su precisión. Un ejemplo sería un sistema que clasifica fotos en grupos y, después, un humano nombra cada grupo (por ejemplo, "perros", "gatos" y "paisajes").

* **Aprendizaje por refuerzo:** en este caso, el sistema aprende mediante prueba y error. Cada vez que toma una decisión, recibe una recompensa si lo ha hecho bien o un castigo si se ha equivocado. Con el tiempo, mejora su estrategia para obtener mejores resultados. Este tipo de aprendizaje se usa mucho en videojuegos o en inteligencia artificial para robots, donde el sistema debe aprender a moverse o tomar decisiones basándose en la experiencia acumulada.

### 1.2.3 Deep learning


Introducción al Deep Learning y las Redes Neuronales
El aprendizaje profundo (deep learning) es una técnica avanzada de aprendizaje automático (machine learning) que permite a los ordenadores aprender de manera más parecida a como lo hace el cerebro humano. Para lograr esto, se utilizan redes neuronales artificiales, un tipo de modelo matemático inspirado en el funcionamiento de las neuronas en nuestro cerebro.

¿Cómo funcionan las redes neuronales?
Las redes neuronales artificiales están formadas por capas de nodos (neuronas artificiales) que procesan la información:

Capa de entrada: Recibe los datos (por ejemplo, una imagen o un sonido).
Capas ocultas: Analizan la información y detectan patrones.
Capa de salida: Genera el resultado final (por ejemplo, identificar si una imagen muestra un perro o un gato).
Cuantas más capas tiene una red neuronal, más profundo es su análisis, lo que permite que el sistema aprenda de manera más precisa.

El aprendizaje profundo, o deep learning, es una rama del aprendizaje automático que permite a los sistemas analizar datos de manera más profunda y detallada para generar resultados más precisos. Para entenderlo mejor, veamos dos ejemplos:

**Ejemplo 1: Diagnóstico Médico**
Imaginemos que queremos desarrollar un sistema de autodiagnóstico de enfermedades. En un modelo básico de aprendizaje automático (machine learning), primero recopilamos datos importantes de miles de pacientes, como edad, peso y presión sanguínea. Luego, junto con esos datos, proporcionamos el diagnóstico final que recibió cada paciente (por ejemplo, resfriado o meningitis). Con esta información, el sistema aprende a relacionar los datos de entrada con posibles diagnósticos.

Pero, ¿qué pasaría si en lugar de introducir manualmente los datos relevantes, el sistema pudiera analizar directamente un informe médico en formato PDF y extraer por sí mismo la información clave para emitir un diagnóstico? En este caso, el modelo haría un análisis más profundo de los datos de entrada sin necesidad de una fase previa de selección manual. Este tipo de modelo pertenece al aprendizaje profundo (deep learning), ya que es capaz de procesar la información de manera más avanzada.

**Ejemplo 2: Clasificación de Tomates**
Supongamos que queremos crear un sistema para identificar distintos tipos de tomates. En un modelo de machine learning, haríamos una tabla con características como el color, el tamaño, la forma y la textura de cada tomate, junto con su categoría (por ejemplo, tomate canario o tomate pera). Luego, entrenaríamos al sistema para que, cuando introduzcamos las características de un nuevo tomate, pueda clasificarlo correctamente.

Sin embargo, con deep learning, en lugar de introducir manualmente estas características, el sistema podría simplemente analizar una imagen del tomate y extraer automáticamente sus características (como forma, tamaño y color) para clasificarlo. Incluso podría detectar detalles que nosotros no habíamos considerado en nuestra tabla.

La técnica más habitualmente empleada dentro de la rama del deep learning son las redes neuronales profundas, entendiendo como profundas el hecho de que estén compuestas por varias capas, lo que les permitirá jerarquizar las características principales de los datos de entrada.

## 1.3 Tipos de IA

Entre las clasificaciones de inteligencia artificial que podemos encontrar, una de las más habituales es la que distingue entre inteligencia artificial fuerte y débil.

* Un sistema de **inteligencia artificial fuerte** es aquel capaz de reproducir todas las capacidades humanas, sin centrarse en una única tarea. También se le conoce como AGI (inteligencia artificial general). Son sistemas capaces de aprender conceptos o técnicas nuevas por sí mismos, y por iniciativa propia. En la actualidad no existe (aún) ningun sistema real de IA fuerte, pero podemos encontrar algunos ejemplos ilustrativos de lo que supone en algunas películas o series de ciencia ficción. Por ejemplo, el asistente *Jarvis* de *IronMan*, o el robot *Sony* de la película *Yo robot*. Actualmente, este futuro se ve más cercano gracias a herramientas muy versátiles, como ChatGPT.
* En cambio, un sistema de **inteligencia artificial débil** es aquel que se especializa en una tarea en concreto, y aprende y mejora sobre esa tarea. En este sector sí podemos encontrar varios ejemplos en la vida real: sistemas que aprenden a reconocer caras, o a jugar al juego de la serpiente, o a detectar tumores en radiografías u otras imágenes...

## 1.4 Limitaciones y Riesgos

Aunque la IA es poderosa, tiene limitaciones importantes:

* **Dependencia de datos:** si los datos están sesgados o son insuficientes, la IA puede cometer errores. Por ejemplo, un sistema de contratación podría discriminar si se entrena con datos sesgados.
* **Falta de creatividad y empatía:** la IA solo resuelve problemas para los que fue entrenada. No puede improvisar como un humano. Un asistente virtual no entiende chistes ni sarcasmos.
* **Riesgos éticos:** 
    * Privacidad: muchas IA recopilan datos personales.
    * Pérdida de empleos: automatización en sectores como la manufactura o atención al cliente.

