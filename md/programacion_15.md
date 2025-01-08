# 2. Machine Learning – Cómo aprenden las máquinas

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
