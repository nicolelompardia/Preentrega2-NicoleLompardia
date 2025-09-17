Implementación de un Asistente de IA para la Clasificación Automatizada de Gastos
Resumen
Este proyecto aborda la ineficiencia y propensión a errores en el proceso manual de clasificación de gastos dentro de una organización. Actualmente, el equipo de compras invierte un tiempo considerable en asignar códigos de gasto a las órdenes de compra, consultando manualmente un extenso catálogo. Esta tarea repetitiva limita la productividad y afecta la calidad de los datos financieros, que son cruciales para la toma de decisiones estratégicas, el análisis de egresos y la negociación con proveedores.

La solución desarrollada es un asistente inteligente que utiliza el modelo de lenguaje avanzado Google Gemini Pro. A través de un script de Python en un entorno de Jupyter Notebook, el asistente recibe una descripción de un producto o servicio y devuelve instantáneamente el código de gasto correcto junto con un razonamiento detallado de su decisión. Para lograrlo, se emplearon técnicas de prompt engineering como Few-Shot Prompting, Chain-of-Thought y asignación de rol, entrenando al modelo en contexto con el catálogo de gastos y ejemplos específicos. El resultado es una herramienta funcional que automatiza la clasificación, validando la viabilidad de la IA para optimizar procesos financieros clave.

Introducción
Nombre del proyecto
Implementación de un Asistente de IA para la Clasificación Automatizada de Gastos (Spend Classification).

Presentación del problema a abordar
En nuestra organización, el proceso de clasificación de gastos es un pilar fundamental para la gestión financiera. Permite analizar los egresos, identificar oportunidades de ahorro y negociar eficazmente con los proveedores. Actualmente, los compradores invierten una cantidad considerable de tiempo en asignar manualmente un código de gasto a cada orden de compra. Para ello, deben consultar un extenso archivo de referencia, buscando la correspondencia entre el número de parte (part number) del material o servicio y el código de gasto correcto.

Este proceso manual no solo es propenso a errores, sino que también representa un cuello de botella que reduce la productividad y desvía la atención de tareas de mayor valor estratégico. La relevancia de solucionar esta problemática radica en la optimización directa de los recursos humanos y la mejora en la precisión de los datos financieros, lo que impacta positivamente en la toma de decisiones.

Desarrollo de la propuesta de solución
La solución se centra en el desarrollo de un asistente inteligente utilizando el modelo de lenguaje Gemini Pro. Este asistente automatizará la clasificación de gastos mediante el procesamiento de lenguaje natural. El núcleo de la solución radica en proporcionar al modelo de IA, a través de un prompt dinámico, dos conjuntos de datos clave:

La base de datos de ejemplos de part numbers con sus respectivos títulos y descripciones.

El catálogo completo de códigos de categorización de gastos con sus descripciones detalladas.

Una vez provisto de este contexto, el sistema permite a los usuarios introducir una descripción, y el asistente de IA identifica y devuelve el código de gasto correcto de manera instantánea en un formato estructurado (JSON). Para lograr esto, se diseñó un prompt específico que guía al modelo para que actúe como un experto clasificador, utilizando las técnicas avanzadas que se detallan en la sección de "Herramientas y tecnologías".

Justificación de la viabilidad del proyecto
Viabilidad Técnica: El proyecto es altamente viable. Gemini Pro posee una capacidad demostrada para procesar y relacionar grandes volúmenes de información textual, lo cual es ideal para aprender la correlación entre descripciones de materiales y categorías de gastos. La implementación se realiza en un entorno de Jupyter Notebook con Python, facilitando la experimentación y el desarrollo rápido de prototipos (POC).

Viabilidad Económica: La solución es económicamente atractiva, ya que se basa en herramientas de IA de Google a las cuales la empresa ya podría tener acceso o cuyo costo por API es marginal en comparación con el ahorro de tiempo y la reducción de errores.

Recursos y Tiempo: El desarrollo de la prueba de concepto (POC) se puede completar en un corto período. Los recursos necesarios son: acceso a la API de Gemini, un conjunto de datos de muestra y tiempo de desarrollo para el refinamiento del prompt.

Objetivos
Objetivo General
Desarrollar e implementar un asistente de IA para automatizar el proceso de clasificación de gastos, mejorando la eficiencia y precisión del equipo de compras.

Objetivos Específicos
Reducir en al menos un 80% el tiempo invertido por los compradores en la asignación de códigos de gasto.

Minimizar los errores humanos en la categorización para mejorar la calidad de los datos financieros, apuntando a una precisión superior al 90%.

Crear una prueba de concepto (POC) funcional en un Jupyter Notebook que demuestre la eficacia de la solución.

Validar la aplicabilidad de las técnicas de "Fast Prompting" para optimizar la interacción con el modelo de IA.

Metodología
El proyecto se llevó a cabo siguiendo una metodología ágil y experimental, centrada en la iteración y mejora continua del prompt.

Recopilación y Preparación de Datos: Se extrajo una muestra representativa del referencial de gastos, conteniendo descripciones de productos y sus códigos correspondientes. Estos datos se estructuraron en un diccionario de Python para ser utilizados como base de conocimiento.

Diseño del Prompt: Se creó un prompt dinámico utilizando una plantilla que asigna un rol al modelo, le proporciona contexto (las categorías de gasto) y ejemplos (técnica Few-Shot).

Implementación del Código: Se desarrolló un script en Python que integra la llamada a la API de Gemini. La función principal toma una descripción de un item, construye el prompt y procesa la respuesta JSON del modelo.

Validación y Pruebas: Se ejecutó el script con un conjunto de datos de prueba (no vistos en los ejemplos del prompt) para medir la precisión y la calidad de las clasificaciones y los razonamientos generados por el modelo.

Documentación de Resultados: Se analizaron los resultados de las pruebas para evaluar el cumplimiento de los objetivos y se documentaron las conclusiones.

Herramientas y tecnologías
Modelo de IA: Google Gemini Pro. Elegido por su avanzada capacidad de comprensión del lenguaje natural, su ventana de contexto amplia y su habilidad para seguir instrucciones complejas, como devolver respuestas en formato JSON.

Entorno de Desarrollo: Jupyter Notebook. Ideal para la creación de prototipos, la experimentación interactiva con el código y la visualización de resultados.

Lenguaje de Programación: Python, con la librería google.generativeai para interactuar con la API de Gemini.

Técnicas de Fast Prompting Utilizadas
Asignación de Rol (Role Prompting): Se le da una personalidad experta a la IA ("Actúa como un analista financiero senior...") para enfocar sus respuestas en el dominio correcto y mejorar la calidad de la clasificación.

Few-Shot Prompting: Se utilizó para dar al modelo ejemplos concretos de la tarea. Esto es crucial porque "muestra" lo que se espera en lugar de solo "decirlo", reduciendo la ambigüedad y mejorando drásticamente la precisión.

Chain-of-Thought (CoT): Se le pidió explícitamente al modelo que desglose su razonamiento. Al solicitar una clave "razonamiento" en la salida, forzamos al modelo a pensar de manera lógica antes de dar el resultado final, lo que aumenta la fiabilidad y permite auditar sus decisiones.

Implementación
El código completo de la solución se encuentra en el archivo Jupyter Notebook (.ipynb) incluido en este repositorio.

Resultados
La implementación del asistente de IA arrojó resultados muy positivos, logrando una clasificación precisa y coherente en el conjunto de pruebas.

Conclusiones
El desarrollo de este proyecto permite concluir que la implementación de un asistente de IA con Gemini Pro es una solución viable y altamente efectiva para automatizar la clasificación de gastos.
