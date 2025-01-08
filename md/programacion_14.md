# 1. Introducción a la Inteligencia Artificial

La **Inteligencia Artificial (IA)** ya forma parte de nuestro día a día, pero ¿cómo funciona realmente? En este bloque, exploraremos sus fundamentos y aprenderemos sobre **Machine Learning** y **Deep Learning**, las tecnologías que permiten a las máquinas "aprender" a partir de datos.

¿Cómo lo haremos? A través de actividades prácticas:
* Entrenaremos modelos básicos con Teachable Machine.
* Integraremos IA en Python para clasificar imágenes.
* Reflexionaremos sobre sus oportunidades, limitaciones y dilemas éticos.

Al final, no solo entenderás cómo funciona la IA, sino que habrás creado tu propio modelo de inteligencia artificial. ¡Vamos allá!

## 1.1 ¿Qué es la IA?

La **Inteligencia Artificial (IA)** es la capacidad de las máquinas para realizar tareas que normalmente requieren inteligencia humana, como aprender, razonar, resolver problemas o tomar decisiones.

>📌 DATO CURIOSO: El término *Inteligencia Artificial* fue acuñado en 1956 por John McCarthy, un científico que soñaba con crear máquinas que "pensaran" por sí mismas.

## 1.2 ¿Dónde encontramos la IA en nuestra vida diaria?

La IA está cada vez más presente en nuestra vida diaria, aunque a veces no lo notemos. Aquí tienes algunos ejemplos:

* Tu móvil desbloqueándose con tu cara → Reconocimiento facial.
* Netflix recomendándote series que te gustan → Algoritmos de recomendación.
* Siri, Alexa o Google Assistant respondiendo preguntas → Procesamiento de lenguaje natural.
* Google Maps calculando la ruta más rápida → Análisis de datos en tiempo real.
* Filtros de redes sociales detectando tu rostro y aplicando efectos → Visión por computadora.
* Coches autónomos como Tesla → Sistemas de IA analizan el tráfico, peatones y señales de tráfico para conducir sin intervención humana.
* IA en los videojuegos → Los enemigos en un shooter reaccionan a tus movimientos, los NPC (personajes no juagadores) en juegos de rol actúan de forma más realista.

> 🔍 EJERCICIO RÁPIDO:
> ¿Cuánta IA has usado hoy? Haz una lista de todas las veces que has interactuado con sistemas de IA desde que te has despertado. A continuación, compara tu lista con la de tu compañero/a:
> * ¿Quién usó más IA?
> * ¿En qué áreas de la vida se usa más IA? (entretenimiento, comunicación, transporte, etc.)
> * ¿Hubo alguna IA que tu compañero/a anotó y que tú no habías notado?

## 1.2 ¿Cómo funciona la IA?

Para que una máquina "aprenda", necesita datos. La IA analiza grandes volúmenes de información y encuentra patrones para tomar decisiones.

> 📌 Ejemplo: Un sistema de IA que reconoce gatos en fotos necesita ver miles de imágenes de gatos para aprender a identificarlos.

La IA aprende siguiendo estos cuatro pasos:

1. **Recoger datos:** se recopilan datos de distintas fuentes. Por ejemplo, fotos de gatos y perros para entrenar un sistema de clasificación de animales.
2. **Procesar y almacenar información:** se organizan los datos en un formato que la máquina pueda entender. Por ejemplo: convertir imágenes en valores numéricos que representen colores y formas.
3. **Aprender patrones:** el sistema analiza los datos almacenados para encontrar patrones o entender relaciones. Por ejemplo, detectar que los gatos suelen tener orejas puntiagudas y ojos grandes.
4. **Generar predicciones:** la IA utiliza lo aprendido para hacer deducciones o predicciones. A este proceso se le llama *inferencia*, y es lo que hace que un programa sea realmente *inteligente*. Por ejemplo: *"Esta imagen tiene orejas puntiagudas y ojos grandes, es un gato."*

## 1.3 Tipos de IA

No todas las IA son iguales. Se pueden clasificar en dos grandes tipos:

* **Inteligencia artificial fuerte (general)**: es aquella capaz de reproducir todas las capacidades humanas, sin centrarse en una única tarea. También se le conoce como AGI (inteligencia artificial general). Son sistemas capaces de aprender conceptos o técnicas nuevas por sí mismos, y por iniciativa propia. En la actualidad no existe (aún) ningun sistema real de IA fuerte, pero podemos encontrar algunos ejemplos ilustrativos de lo que supone en algunas películas o series de ciencia ficción. Por ejemplo, el asistente *Jarvis* (IronMan), o el robot *Sony* (Yo, robot). Actualmente, este futuro se ve más cercano gracias a herramientas como ChatGPT.
* **Inteligencia artificial débil (específica)**: es aquella que se especializa en una tarea en concreto, y aprende y mejora sobre esa tarea. En este sector sí podemos encontrar varios ejemplos en la vida real: sistemas que aprenden a reconocer caras, o a jugar al juego de la serpiente, o a detectar tumores en radiografías u otras imágenes.

## 1.4 Riesgos y beneficios de la IA

La Inteligencia Artificial está revolucionando múltiples sectores, con grandes ventajas pero también riesgos importantes. Veamos algunos ejemplos concretos.

* **Beneficios**
  - **Medicina y diagnóstico**: un sistema de IA desarrollado por *Google Health* y *DeepMind* logró detectar cáncer de mama con mayor precisión que los radiólogos. Un estudio publicado en Nature en 2020 mostró que la IA redujo los falsos positivos y falsos negativos en mamografías.
  - **Accesibilidad y traducción automática:** *Google Translate* y *Whisper AI* de OpenAI han mejorado la accesibilidad para personas con discapacidad auditiva al generar subtítulos en tiempo real con gran precisión. También, las IA pueden describir imágenes para personas con discapacidad visual.
  - **Creatividad y arte:** herramientas como *DALL·E* de OpenAI y *Runway ML* permiten a los diseñadores crear imágenes, animaciones y efectos especiales con IA. DALL·E puede generar imágenes a partir de texto, mientras que Runway ML ha sido utilizada en producciones de Hollywood.
 
* **Riesgos éticos y sociales**
    * **Desinformación y noticias falsas:** con IA generativa es cada vez más difícil diferenciar lo real de lo falso. Se han creado deepfakes de políticos diciendo cosas que nunca dijeron, manipulando la opinión pública en elecciones.
    * **Sesgo y discriminación:** si los datos están sesgados, la IA tomará decisiones injustas. En EE.UU., un sistema de IA para predecir reincidencia criminal recomendaba penas más largas para personas de raza negra debido a datos históricos sesgados.
    * **Privacidad:** muchas IA recopilan datos personales sin que los propietarios sean plenamente conscientes de eso. Por ejemplo, algoritmos que rastrean lo que compras en internet o casos como los de  China, donde se usan sistemas de reconocimiento facial para monitorear a la población en tiempo real.
    * **Impacto en el empleo especializado:** a diferencia de la automatización industrial, la IA está empezando a reemplazar trabajos creativos e intelectuales. Por ejemplo, algunos medios de comunicación han reemplazado periodistas por IA para redactar noticias básicas. También, estudios de doblaje han comenzado a usar IA para replicar voces en lugar de contratar actores de voz.

> 🔍 EJERCICIO EN GRUPO: Forma un equipo de 3 o 4 personas y os convertiréis en detectives de IA. Vuestra misión es investigar cómo se está usando la IA en un campo específico y presentar vuestros hallazgos a la clase.
> 
> Fase 1: Elegid un campo donde se use IA. Cada equipo elegirá un área donde la IA tenga un papel importante. Aquí tenéis algunas opciones: 
> * Salud y Medicina → Diagnóstico de enfermedades, cirugías con IA, análisis de imágenes médicas
> * Transporte y conducción autónoma → Coches como Tesla, control del tráfico, predicción de rutas.
> * Videojuegos → NPCs inteligentes, personalización de experiencia, generación de mundos.
> * Entretenimiento y redes sociales → Recomendaciones de Netflix/Spotify, algoritmos de TikTok e Instagram.
> * Educación → IA en clases virtuales, herramientas como ChatGPT para estudiar.
> * Finanzas y comercio → IA en bancos, predicciones de la bolsa, atención al cliente con chatbots.
> 
> Fase 2: Investigad y responded a estas preguntas
> * ¿Qué problema soluciona la IA en este campo? 
> * ¿Cómo funciona? (explicación básica sin tecnicismos, pero clara).
> * Ejemplos reales: empresas, aplicaciones o proyectos que ya estén usando esta tecnología.
> * Beneficios y riesgos: ¿cuáles son las ventajas y los posibles problemas que puede causar?
> 
> ⚠️ Consejo: Buscad información en artículos, vídeos o páginas web oficiales.
> 
> Fase 3: Preparad vuestra presentación
> * Tendréis 5 minutos para presentar lo que habéis investigado. Podéis elegir el formato que más os guste (presentación, poster o infografía, role-play o simulación sobre cómo funciona la IA en ese campo, mini-video explicativo, etc)
>
> Fase 4: Reflexión final y debate. Después de todas las presentaciones, haremos una discusión en clase:
> * ¿Cuál fue el uso de la IA más sorprendente?
> * ¿Hay algún sector donde la IA pueda ser un problema más que una solución?
> * ¿Cómo os imagináis la IA en estos campos dentro de 10 años?


## RESUMEN

✅ La IA permite a las máquinas aprender y tomar decisiones basadas en datos.<br>
✅ Existen diferentes tipos de IA: débil (especializada en una tarea) y fuerte (aún teórica).<br>
✅ La IA ya está presente en nuestra vida diaria, desde asistentes virtuales hasta videojuegos y coches autónomos.<br>
✅ Aunque tiene ventajas, también presenta riesgos como el sesgo, la privacidad y la automatización del trabajo.
