---
layout: post
title: Conversatoria sobre la inteligencia artificial en la medicina
date: 2025-02-04 13:42
description: compartí mi experiencia sobre las aplicaciones de la IA en la medicine en el Grupo Hospitalario Kennedy, Guayaquil
tags: research 
categories: blog-post
disqus_comments: true
related_posts: true
authors:
  - name: Xuelong An
toc:
  sidebar: left
thumbnail: /assets/img/kennedy-1.jpg
featured: true
---
# El Rol de la Inteligencia Artificial en la Medicina


Tuve la maravillosa oportunidad de dar una presentación junto con el ex-Ministro de Salud y fundador del Grupo Hospitalario Kennedy Dr. Teófilo Lama. En esta, compartí mi experiencia entorno a los usos de la inteligencia artificial (IA) en la medicina. 

El tema principal de la conversatoria trata sobre el "Pasado, Presente y Futuro de la Medicina", en donde el Dr. Lama compartió su carrera en la medicina, cómo esta ha avanzado a través del tiempo y nos contagió con su entusiasmo e interés sobre cómo la IA poco a poco sinergiza con la medicina. 

<figure>
  <img src="/assets/img/kennedy-2.jpg" alt="Sorry. Image couldn't load." width="auto" height="auto">
  <figcaption id="cell-embedder">El pasado, presente y futuro de la medicina con Dr. Lama </figcaption>
</figure>

Durante mi turno, estructuré mi presentación en base a una conversación con un amigo quien estudia medicina:

- ¿A quién asiste la IA: al paciente o al doctor?
- Costos de implementación de la IA
- Casos ejemplares

## La IA como un asistente de diagnóstico

Compartí mi tesis de mi masterado en UCL, ilustrando un caso en donde la IA actúa como asistente de patólogos para el análisis a gran escala de tejido colorectal para identificar poblaciones de células en fase G0, lo cual es relevante para estudiar resistencia a quimioterapia y relapso. Compartí mi demo en: https://awxlong.github.io/assets/img/pathoinsightmil_demo.mp4

El costo de implementar este sistema en un local médico es bastante alto. En un lado esto es debido a la alta complejidad del dato, pues las imágenes que representan la digitalización de una biopsia contiene más de 1 millón de píxeles. Por ende para entrenar estos modelos de aprendizaje profundo, así como almacenar estas imágenes, requerirían clústeres y servidores, lo cual no necesariamente estaría disponible. 

<figure>
  <img src="/assets/img/kennedy-3.png" alt="Sorry. Image couldn't load." width="auto" height="auto">
  <figcaption id="cell-embedder">El presente y futuro de la medicina con la IA</figcaption>
</figure>

## La IA como un asistente para lidiar con obligaciones burocráticas

Otro uso de la IA concierne implementarlo como un asistente para automatizar el llenado de formularios varios, que constituyen trabajo tedioso que todo doctor enfrenta día a día. Compartí mi proyecto sobre YachayMed https://github.com/awxlong/medical_asr. Este sistema transcribe conversaciones entre doctor y paciente con el fin de facilitar el llenado de un reporte médico de un paciente. 

En este caso, el costo de implementación sería menor debido a que el avance y accesibilidad de modelos de lenguaje es mayor que los de imágenes. En parte esto es debido a que las transcripciones tienen menor complejidad de datos (son cortas, y más o menos consisten de alrededor de 700-1000 palabras para una conversación de casi 10 minutos). Además, paralelo al movimiento de código abierto, la integración de modelos de lenguaje abre bastantes oportunidades en el ámbito médico. 

Claro, lo más accesible y fácil de implementar sería modelos estadísticos/aprendizaje mecánico como regresión lineal o logística para el análisis masivo de bases de datos como formularios de Excel. Hay problemas bastantes interesantes que pueden ser resueltos como predicción de sobrevivencia o readmisión.  

<figure>
  <img src="/assets/img/kennedy-1.jpg" alt="Sorry, an unanticipated error occured and the image can't load." width="100%" height="auto">
  <figcaption id="afold"> Conversación y discusión sobre la IA en la medicina </figcaption>
</figure>

Las diapositivas que empleé se encuentran anexado. Hay diapositivas extras explicando qué son redes neuronales y cómo han sido entrenadas. 

{% pdf "/assets/pdf/tertulia_ia.pdf" %}