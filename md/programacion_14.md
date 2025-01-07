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

