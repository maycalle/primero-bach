# 1. Introducción a la Inteligencia Artificial

En esta unidad exploraremos qué es la **Inteligencia Artificial (*IA*)** y cómo se utiliza en aplicaciones cotidianas como asistentes virtuales, recomendaciones y reconocimiento de imágenes. Aprenderemos conceptos clave como el **Aprendizaje Automático (*Machine Learning*)** y las **Redes Neuronales**.

A través de actividades prácticas:
* Entrenaremos modelos básicos con *Teachable Machine*.
* Los integraremos en programas de Python para clasificar imágenes.
* Reflexionaremos sobre las posibilidades, limitaciones y riesgos éticos de la IA.
  
Al finalizar, comprenderás cómo funcionan estas tecnologías y habrás creado tu primer modelo de IA aplicando tus propias ideas.

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

La IA funciona a través de algoritmos y datos. El sistema sigue estos pasos generales:

1. **Entrenamiento:** se proporcionan grandes conjuntos de datos al sistema. Por ejemplo, para reconocer gatos, le mostramos miles de imágenes etiquetadas como "gato" o "no gato".
2. **Identificación de patrones:** la IA analiza las características comunes en los datos (como la forma de las orejas de un gato o su color).
3. **Predicción o decisión:** cuando se le muestra una nueva imagen, la IA compara las características aprendidas con la nueva entrada y decide si es un gato.

El modelo será tan bueno como los datos que reciba. Datos incompletos o incorrectos pueden llevar a errores en los resultados obtenidos.

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

