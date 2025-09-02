Introducción
Nombre del proyecto: Implementación de un Asistente de IA para la Clasificación Automatizada de Gastos (Spend Classification).

Presentación del problema a abordar: En nuestra organización, el proceso de clasificación de gastos es un pilar fundamental para la gestión financiera. Permite analizar los egresos, identificar oportunidades de ahorro y negociar eficazmente con los proveedores. Actualmente, los compradores invierten una cantidad considerable de tiempo en asignar manualmente un código de gasto a cada orden de compra. Para ello, deben consultar un extenso archivo de referencia en Google Sheets, buscando la correspondencia entre el número de parte (

part number) del material o servicio y el código de gasto correcto. Este proceso manual no solo es propenso a errores, sino que también representa un cuello de botella que reduce la productividad y desvía la atención de tareas de mayor valor estratégico. La relevancia de solucionar esta problemática radica en la optimización directa de los recursos humanos y la mejora en la precisión de los datos financieros, lo que impacta positivamente en la toma de decisiones.

Desarrollo de la propuesta de solución: La solución propuesta se centra en el desarrollo de un asistente inteligente utilizando el modelo de lenguaje Gemini Pro. Este asistente automatizará la clasificación de gastos mediante el procesamiento de lenguaje natural. El núcleo de la solución radica en entrenar al modelo de IA con dos conjuntos de datos clave:

La base de datos completa de 

part numbers con sus respectivos títulos y descripciones.

El catálogo de códigos de categorización de gastos con sus descripciones detalladas.

Una vez entrenado, el sistema permitirá a los usuarios introducir un 

part number o una descripción, y el asistente de IA identificará y devolverá el código de gasto correcto de manera instantánea. Para lograr esto, se diseñarán prompts específicos que guíen al modelo para que actúe como un experto clasificador, utilizando técnicas avanzadas de prompting para asegurar la máxima precisión y eficiencia.

Justificación de la viabilidad del proyecto:

Viabilidad Técnica: El proyecto es altamente viable. Gemini Pro posee una capacidad demostrada para procesar y relacionar grandes volúmenes de información textual, lo cual es ideal para aprender la correlación entre descripciones de materiales y categorías de gastos. La implementación se puede realizar en un entorno de Jupyter Notebook, facilitando la experimentación y el desarrollo rápido de prototipos (POC).


Viabilidad Económica: La solución es económicamente atractiva, ya que la empresa ya proporciona a sus empleados acceso a las herramientas de IA de Google, eliminando costos adicionales de licenciamiento de software.

Recursos y Tiempo: El desarrollo de la prueba de concepto (POC) se puede completar en un corto período. Los recursos necesarios son: acceso a la API de Gemini, un conjunto de datos de muestra (que puede ser anonimizado) y tiempo de desarrollo para el refinamiento de los prompts. El impacto esperado es una reducción significativa del tiempo dedicado a esta tarea, lo que se traduce en un aumento directo de la productividad del equipo de compras.

Objetivos
Objetivo General: Desarrollar e implementar un asistente de IA para automatizar el proceso de clasificación de gastos, mejorando la eficiencia y precisión del equipo de compras.

Objetivos Específicos:

Reducir en al menos un 80% el tiempo invertido por los compradores en la asignación de códigos de gasto.

Minimizar los errores humanos en la categorización para mejorar la calidad de los datos financieros.

Crear una prueba de concepto (POC) funcional en un Jupyter Notebook que demuestre la eficacia de la solución.

Validar la aplicabilidad de las técnicas de "Fast Prompting" para optimizar la interacción con el modelo de IA.

Metodología
El proyecto se llevará a cabo siguiendo una metodología ágil y experimental, centrada en la iteración y mejora continua del prompt.

Recopilación y Preparación de Datos: Se extraerá una muestra representativa y anonimizada del referencial de Google Sheets, conteniendo part numbers, descripciones y sus códigos de gasto correspondientes. Estos datos se estructurarán en un formato legible (CSV o JSON) para ser utilizados en el prompt.

Diseño Inicial del Prompt (Baseline): Se creará un primer prompt utilizando la técnica de "Few-Shot Prompting", donde se le proporcionará al modelo algunos ejemplos concretos de clasificación para que entienda el contexto y la tarea a realizar.

Experimentación y Refinamiento (Fast Prompting): Se iniciará un ciclo de experimentación rápida. Se probarán diferentes configuraciones de prompts, variando elementos como:

El rol asignado a la IA (ej. "Eres un experto en finanzas...").

La claridad y concisión de las instrucciones.

El formato de los ejemplos y de la salida deseada (ej. solicitar la respuesta en formato JSON).

El uso de la técnica Chain-of-Thought para que el modelo "razone" su respuesta antes de dar el resultado final, aumentando la precisión.

Validación y Pruebas: Cada versión del prompt se probará con un conjunto de datos de validación para medir su precisión. Se registrarán los resultados para identificar qué configuración ofrece el mejor rendimiento.

Desarrollo de la POC: Una vez identificado el prompt más eficaz, se integrará en un script de Python dentro de un Jupyter Notebook. Este notebook servirá como la demostración final, permitiendo a cualquier usuario introducir un dato y recibir la clasificación al instante.

Herramientas y Tecnologías
Modelo de IA: Google Gemini Pro. Elegido por su avanzada capacidad de comprensión del lenguaje natural y su flexibilidad para ser integrado a través de APIs.

Entorno de Desarrollo: Jupyter Notebook. Ideal para la creación de prototipos, la experimentación interactiva con el código y la visualización de resultados.

Lenguaje de Programación: Python, con la librería google.generativeai para interactuar con la API de Gemini.

Técnicas de Prompting:

Few-Shot Prompting: Se utilizará para dar al modelo ejemplos concretos de la tarea. Esto es crucial porque "muestra" lo que se espera en lugar de solo "decirlo", reduciendo la ambigüedad.

Chain-of-Thought (CoT): Se le pedirá al modelo que desglose su razonamiento. Por ejemplo: "Dado el part number X y la descripción Y, analiza las palabras clave y compáralas con las categorías de gasto. Explica por qué eliges el código Z". Esta técnica mejora la precisión en tareas de clasificación complejas.

Asignación de Rol (Role Prompting): Se le dará una personalidad experta a la IA ("Actúa como un analista financiero senior...") para enfocar sus respuestas en el dominio correcto y mejorar la calidad de la clasificación.
