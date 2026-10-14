# **Biblioteca de prompts — Laboratorio 06**

## **Prueba 1 — [Prompt vago vs. prompt estructurado]**
**Herramienta:** ChatGPT

## *Prompt (vago):*
> Escribe un correo pidiendo más plazo para un trabajo.

**Resultado (resumen):** Generó un correo genérico para solicitar más tiempo para entregar un trabajo, sin especificar el motivo ni la nueva fecha de entrega.

**Observaciones:** La respuesta fue sencilla, pero faltaban detalles sobre la situación, el destinatario y el plazo solicitado. Por eso, el correo podía ser poco específico.

## *Prompt (estructurado):*
>  
    # Rol
    Actúa como un estudiante universitario que se comunica de forma formal y respetuosa.
    # Contexto
    Debo entregar el informe del proyecto final del curso de Diseño de Interfaces el viernes,
    pero dos integrantes del equipo estuvieron enfermos esta semana.
    # Tarea
    Redacta un correo al docente solicitando una prórroga de 3 días.
    # Formato de salida
    Incluye asunto, saludo, cuerpo en máximo 2 párrafos y despedida.
    # Restricciones
    No exageres la situación, no uses más de 120 palabras y propone una nueva fecha concreta.


**Resultado (resumen):** Generó un correo formal con asunto, saludo, explicación del motivo de la solicitud, propuesta de una nueva fecha y despedida.

**Observaciones:**  

- El tono fue más formal y adecuado para dirigirse al docente.
- Incluyó información específica sobre el motivo de la solicitud.
- Presentó una estructura clara y respetó mejor las indicaciones de extensión y formato.


## **Prueba 2 — [Zero-shot y few-shot]**

**Herramienta:** ChatGPT

## *Clasificación con zero-shot:*
**Prompt utilizado:**
>
    Clasifica cada comentario como POSITIVO, NEGATIVO o NEUTRO.
    1. "La app se cierra cada vez que intento pagar."
    2. "Llegó el pedido, nada que destacar."
    3. "Me encantó lo rápido que cargan las pantallas."
    4. "Está bien, aunque el botón de ayuda es difícil de encontrar."

**Resultado (resumen):** Clasificó los cuatro comentarios según su sentimiento, sin recibir ejemplos previos.

**Observaciones:** La clasificación se realizó a partir de las instrucciones proporcionadas. El modelo tuvo que interpretar por sí mismo el sentimiento de cada comentario, sin contar con ejemplos que orientaran sus respuestas.


## *Clasificación con few-shot:*
**Prompt utilizado:**
>  
    Clasifica cada comentario siguiendo el formato de los ejemplos.

    Comentario: "Excelente diseño, todo es muy intuitivo."
    Categoría: POSITIVO | Tema: diseño

    Comentario: "Buen precio, pero la entrega tardó una semana."
    Categoría: MIXTO | Tema: entrega

    Comentario: "La app se cierra cada vez que intento pagar."
    Categoría:

    Comentario: "Está bien, aunque el botón de ayuda es difícil de encontrar."
    Categoría:



**Resultado (resumen):** Utilizó los ejemplos como referencia para clasificar los comentarios y presentar las categorías junto con sus temas.

**Observaciones:**  Los ejemplos ayudaron a establecer el formato de salida y a mostrar cuándo corresponde utilizar la categoría MIXTO. En comparación con zero-shot, el prompt proporciona referencias más claras para realizar la clasificación.

**¿Respetó el formato?** Sí, presentó cada comentario con su categoría y tema, siguiendo el formato de los ejemplos.

**¿Identificó el tema?** Sí, identificó el tema de pago para el primer comentario y navegación para el segundo.

**¿Usó la categoría MIXTO?** Sí, clasificó el segundo comentario como MIXTO porque combina una valoración positiva de la aplicación con una dificultad para encontrar el botón de ayuda.

## **Prueba 3 — Delimitadores y formato de salida**

**Herramienta:** ChatGPT

### *Resumen con delimitadores*

**Prompt utilizado:**
>
    Resume el texto delimitado por `<texto></texto>` en 3 viñetas de máximo 20 palabras cada una. Luego escribe una sola oración con la idea principal.

    **Texto utilizado:** Texto sobre la historia de Phainon Khaslana en *Honkai: Star Rail*.

**Resultado (resumen):**
- Phainon debe reunir el poder de los Titanes y las Llamas Primordiales para salvar Amphoreus.
- Destaca por su bondad, determinación y sacrificios para proteger a sus seres queridos y ofrecerles un futuro.
- Su lucha por salvar su mundo amenaza su identidad, sus vínculos y su propia felicidad.

**Idea principal:** Phainon representa el sacrificio y la resistencia de quien lucha por salvar a los demás, arriesgándose a perderse a sí mismo.

**Observaciones:** Los delimitadores permitieron identificar el texto que debía resumirse. La IA respetó las tres viñetas y el límite de 20 palabras por viñeta, además de presentar una oración con la idea principal.

### *Extracción de datos*

**Prompt utilizado:**
>
    Del siguiente mensaje extrae: nombre, curso, fecha y motivo. Devuelve primero una tabla Markdown y después el mismo contenido en JSON válido. Si algún dato no aparece, escribe "no especificado".

    Mensaje: "Hola, soy Lucía Ramos del curso de Base de Datos. Quería avisar que el martes 14 no podré asistir al laboratorio porque tengo una cita médica".

**Resultado (resumen):** La IA identificó el nombre como Lucía Ramos, el curso como Base de Datos, la fecha como martes 14 y el motivo como una cita médica. También generó un bloque JSON con los datos extraídos.

**Observaciones:** La información extraída fue correcta y el JSON presentó los datos solicitados. Sin embargo, la tabla Markdown tuvo un formato incorrecto, ya que las filas y los encabezados quedaron separados. Esto demuestra que es importante revisar tanto la información como la estructura de salida solicitada.

## **Prueba 4 — Razonamiento paso a paso y encadenamiento**

**Herramienta:** ChatGPT

### *1. Planificación de tareas*

**Prompt utilizado:**
>
    Tengo 3 tareas para esta semana: informe de laboratorio (4 h, entrega miércoles), estudiar para el examen (6 h, examen viernes) y presentación grupal (3 h, jueves). Dispongo de 3 horas libres por día de lunes a jueves.

    Piensa paso a paso: primero calcula las horas disponibles, luego verifica si alcanzan y finalmente propone un horario día por día en una tabla.

**Resultado (resumen):**

Se calcularon 12 horas disponibles durante los cuatro días, pero las tareas requieren 13 horas en total. Por ello, falta una hora para completar todas las actividades. Se propuso un horario que prioriza las fechas de entrega y se recomendó conseguir una hora adicional para completar las seis horas de estudio.

**Observaciones:**

La respuesta calculó correctamente las horas disponibles y necesarias, identificó que faltaba una hora y propuso un horario según las fechas límite. Sin embargo, el horario distribuyó solo cinco horas de estudio, por lo que fue necesario recomendar tiempo adicional.

### *2. Prompt chaining*

**Prompt 1:** 
>
    Genera el índice (máximo 5 secciones) de un artículo de blog titulado "Buenas prácticas para diseñar APIs REST".

**Resultado 1:**

1. Introducción a las APIs REST.
2. Diseño correcto de endpoints y recursos.
3. Uso adecuado de los métodos HTTP.
4. Manejo de errores y códigos de estado.
5. Seguridad y documentación de las APIs.

**Prompt 2:** 
>
    Desarrolla solo la sección 2 del índice anterior en 150 palabras, con un ejemplo de endpoint.

**Resultado 2:**

#### 2. Diseño correcto de endpoints y recursos

Al diseñar una API REST, es importante utilizar nombres claros y sencillos para identificar los recursos. Se recomienda emplear sustantivos en plural y evitar verbos en las rutas, ya que las acciones se representan mediante los métodos HTTP.

Por ejemplo, si desarrollamos una API para administrar estudiantes, podemos utilizar el siguiente endpoint:

`GET /api/estudiantes`

Este endpoint permite obtener la lista de estudiantes registrados. Para consultar un estudiante específico, podemos utilizar `GET /api/estudiantes/15`, donde el número 15 representa su identificador.

También es recomendable mantener una estructura uniforme en todas las rutas. Por ejemplo, para registrar un estudiante, se utilizaría `POST /api/estudiantes`, en lugar de crear una ruta como `/api/registrarEstudiante`.

Finalmente, debemos evitar rutas demasiado largas o confusas y organizar los recursos de manera lógica. Estas prácticas facilitan la comprensión, el mantenimiento y el uso de la API por parte de otros desarrolladores.

**Prompt 3:** 
>
    Revisa la sección que escribiste y sugiere 3 mejoras de claridad.

**Resultado 3:**

1. **Explicar los términos técnicos:** añadir una breve definición de endpoint para los lectores principiantes.
2. **Mejorar la conexión entre las ideas:** utilizar conectores para que las recomendaciones se relacionen de manera más natural.
3. **Agregar ejemplos comparativos:** mostrar una ruta incorrecta y otra correcta para que la diferencia sea más fácil de comprender.

**Observaciones:**

Los tres prompts se desarrollaron de manera consecutiva, utilizando cada respuesta como base para la siguiente. Esto permitió crear el índice, desarrollar una sección específica y proponer mejoras para que el contenido fuera más claro y comprensible.

### *Conclusión*

ChatGPT permitió organizar las tareas mediante cálculos y una tabla de horarios. Además, el encadenamiento de prompts facilitó la elaboración progresiva de un artículo, desde su estructura inicial hasta la revisión de su contenido.

## **Prueba 5 — Evaluación e iteración de prompts**

**Herramienta:** Gemini

### *1. Rúbrica de evaluación*

| Criterio | Descripción | Puntaje (1-5) |
|---|---|:---:|
| Relevancia | Responde exactamente lo solicitado | 5 |
| Precisión | La información es correcta y sin inventos | 5 |
| Formato | Respeta la estructura y extensión solicitadas | 5 |
| Tono | Es adecuado para el público objetivo | 5 |

### *2. Iteraciones — Plan de estudio de Java*

#### **Versión 1 — Prompt inicial**

**Prompt utilizado:**
>
    Crea un plan de estudio para aprender Java.

**Resultado (resumen):**

Gemini generó un plan de estudio dividido en cuatro fases, desde los fundamentos de Java hasta el desarrollo backend con Spring Boot. Incluyó temas como variables, estructuras de control, programación orientada a objetos, colecciones, bases de datos y pruebas.

#### **Versión 2 — Se agregó rol y contexto**

**Prompt utilizado:**
>
    Actúa como un tutor de programación. Soy estudiante de Diseño y Desarrollo de Software y estoy aprendiendo Java. Crea un plan de estudio para mejorar mis conocimientos.

**Resultado (resumen):**

Gemini propuso un plan más especializado, enfocado en la programación orientada a objetos, principios SOLID, patrones de diseño, pruebas unitarias y desarrollo backend. También incluyó un proyecto integrador para aplicar los conocimientos.

#### **Versión 3 — Se agregó formato y restricciones**

**Prompt utilizado:**
>
    Actúa como un tutor de programación. Soy estudiante de Diseño y Desarrollo de Software y estoy aprendiendo Java. Crea un plan de estudio de 7 días, con una hora diaria. Organiza la respuesta en una tabla con el tema, la actividad práctica y el objetivo de cada día. Empieza con conceptos básicos y termina con un ejercicio que utilice clases y objetos.

**Resultado (resumen):**

Gemini organizó el plan en una tabla de siete días, con un tema, una actividad práctica y un objetivo por sesión. La propuesta empieza con variables y operadores, continúa con condicionales, bucles, arreglos y métodos, y termina con un proyecto que utiliza clases y objetos.

### *3. Evaluación de las respuestas*

| Versión | Relevancia | Precisión | Formato | Tono | Puntaje total |
|---|:---:|:---:|:---:|:---:|:---:|
| v1 | 4 | 4 | 4 | 4 | 16/20 |
| v2 | 4 | 4 | 4 | 5 | 17/20 |
| v3 | 5 | 4 | 5 | 5 | 19/20 |

### *4. Observaciones de la iteración*

En la primera versión, el prompt era general y la respuesta presentó un plan amplio, con temas básicos y avanzados. En la segunda, agregar el rol y el contexto permitió adaptar mejor la respuesta a mi carrera, aunque el contenido seguía siendo bastante avanzado. En la tercera, especificar los siete días, el tiempo disponible y el formato de tabla hizo que el resultado fuera más organizado y práctico para seguir.

### *Conclusión*

La actividad me permitió comprobar que un prompt más específico puede generar respuestas mejor organizadas y adaptadas a lo que necesito. Agregar contexto, formato y restricciones ayuda a obtener resultados más útiles.

## **Prueba 6 — Biblioteca de prompts y publicación**

**Herramienta:** Gemini y ChatGPT

### *6.1 Plantillas reutilizables*

Las siguientes plantillas permiten reutilizar prompts en distintas situaciones, cambiando únicamente los datos que aparecen entre llaves dobles (`{{ }}`).

#### **Plantilla 1: Redacción de correo formal**

```text
Actúa como {{rol}}.

Contexto: {{situación}}.

Redacta un correo dirigido a {{destinatario}} para {{objetivo}}.

Formato: asunto, saludo, cuerpo en máximo {{n}} párrafos y despedida.

Restricciones: máximo {{palabras}} palabras y tono {{tono}}.
```

#### **Plantilla 2: Resumen de texto**

```text
Resume el siguiente texto delimitado por <texto></texto> en {{cantidad}} viñetas de máximo {{palabras_por_vineta}} palabras cada una.

Después, escribe una oración con la idea principal.

<texto>
{{texto_a_resumir}}
</texto>
```

#### **Plantilla 3: Clasificación de comentarios**

```text
Clasifica los siguientes comentarios según su sentimiento. Utiliza las categorías {{categorias}} e identifica el tema principal de cada comentario.

Devuelve los resultados en una tabla con las columnas: Comentario, Categoría y Tema.

Comentarios:
{{lista_de_comentarios}}

Si un comentario combina una valoración positiva y una negativa, utiliza la categoría MIXTO.
```