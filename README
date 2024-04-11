# Mentoría 2024
Análisis de datos conversacionales: intenciones detras de palabras

Mentor/a: Eugenia Haluszka

Mail de contacto: eugeniahaluszka10@gmail.com

Introducción
Descripción del problema
En una clínica hay tareas que son rutinarias y automatizables y otras que no. La gente que va a una clínica llega con distintos problemas a resolver, con distintos grados de urgencia.

Nosotres en mi equipo de la empresa Kunan pensamos una solución para las tareas de urgencia baja y que tienen gran potencial de automatización, con el espíritu de que eso libere la carga a personas de tener trabajos repetitivos, para que estas personas se puedan enfocar en los casos más urgentes o que necesiten expertise humano.

Un trabajo repetitivo que se presenta en un entorno clínica es el de atender a pedidos por

sacar un turno para un médico de una especialidad, en una sede, en un horario.
consultar los turnos vigentes que un paciente tiene.
cancelar un turno vigente
Nosotres ofrecemos como producto un chatbot, o asistente conversacional, que usa Machine Learning para poder mantener una conversación y realizar acciones. Además de ocuparse de esas tres tareas principales, se le agregan

poder pasar a hablar con un humano (lo que nosotres llamamos handoff)
responder preguntas frecuentes (¿dónde queda la clínica? ¿qué horarios de atención tienen? ¿qué médicos hay?)
La funcionalidad de handoff es muy importante ya que una de las características innatas de los modelos de Machine Learning es que pueden fallar. Un fallo en un bot conversacional se ve como: no entender la intención detrás de una expresión del usuarie, no poder reconocer y extraer correctamente entidades (como lo son nombres de personas, dnis, teléfonos, especialidades médicas, etc), o perder el hilo de una conversación. Para que en estos casos la persona usuaria tenga una forma de suplir la necesidad que la llevó a hablar con el bot, ofrecemos una integración con un sistema de mensajería directo con operadores humanos.

En la mayoría de las clínicas la gente realiza estas acciones enlistadas hablando con une secretarie directamente, a través de Whatsapp, o usando una interfaz gráfica de la página web de la clínica. Pensar en términos de interfaces gráficas como la de un sitio web es algo con un poco más de tradición dentro del desarrollo de productos de software, sobre todo en comparación a las interfaces conversacionales. Whatsapp tiene, especialmente en latinomérica, gran adopción por parte de las personas, que están acostumbradas a usarlo como una interfaz conversacional para el acceso a múltiples servicios.

Un asistente conversacional ofrece una interfaz textual conversacional para la toma de acciones. En vez de apretar botones las personas van guiando a un chatbot a través de opciones en formularios.

Este producto tiene ese desafío doble: ser un producto de NLP en español y ser un producto de Datos en la industria.

Motivación
Cada persona al relacionarse con un producto de software trae consigo su universo de saberes, sus necesidades y sus costumbres, que decantarán en su percepción sobre qué cosas son "fáciles" de hacer con un software y qué cosas serán "complicadas".

En las interfaces conversacionales se abre una puerta más de saberes y exigencias pre-existentes en las personas usuarias: la del lenguaje. Los lenguajes humanos están inscriptos a geografías, son maleables y dinámicos, entre otras características

Descripción del dataset
El dataset con el que trabajaremos este práctico consta de 21k filas. Corresponde a conversaciones reales de pacientes con el bot, con datos recolectados por el canal de comunicación de Whatsapp, con datos que corresponden desde diciembre de 2021 hasta marzo del 2022. Tiene mensajes de cada conversación, tanto emitidos por el bot como por el usuario y taggeados correspondientemente.

From_anon: Número de teléfono emisor del mensaje. (Anonimizado)
To_anon: Número de teléfono receptor del mensaje.(Anonimizado)
Hospital: Nombre del hospital.
Tel_hospital: Teléfono del hospital.
Body: Cuerpo del mensaje.
Status: Indica si el mensaje se recibió/leyó.
SentDate: Año, mes, día, hora, minutos y segundos en el que se envió el mensaje.
Fecha: Año, mes y día formato: aaaa-mm-dd
Dia: día del mes
Hora: hora del mensaje (hh)
Messages: Siempre vale 1. Columna creada para utilizar agrupaciones.
Direction: Dirección del mensaje ya sea de entrada (inbound) o salida (outbound-api). A estas columnas se le agregan varias que que surgen de analizar mensajes del bot:
Appointment_msp: Mensaje de turno confirmado con la especialidad solicitada.
Appointment: valor dicotómico 1 indica que sacó turno y 0 que no.
Cancellation_msp: Mensaje de turno cancelado que contiene la especialidad cancelada.
Cancelled: valor dicotómico 1 indica que canceló efectivamente el turno y 0 que no se canceló.
Consult: valor dicotómico 1 indica que se consultaron los turnos y 0 que no se consultaron
Consult_Appoint: cuerpo del mensaje sobre la consulta realizada.
Fail_HH: valor dicotómico donde 1 indica que no se solicitó HH y no se logró la comunicación.
Got_HH: valor dicotómico donde 1 indica que la persona solicitó y logró contactarse con HH.
No_correlation: valor dicotómico donde 1 indica que el bot detectó que la persona preguntó algo que no tenía que ver con las funcionalidades del bot.
not_DNI: valor dicotómico donde 1 indica que el paciente proveyó un DNI que no estaba registrado como cliente de esa clínica
Error_Interno : valor dicotómico donde 1 indica que hubo un error interno del bot
Error_501 : valor dicotómico donde 1 indica que hubo un error en los sistemas clínicos con los cuales el bot está integrado
Has_Cupo: valor dicotómico donde 1 indica que el médico seleccionado no tiene cupo de turnos para una obra social.
Ask_Kunan: valor dicotómico donde 1 indica que el bot menciona quien es kunan. Esto sirve para ver como funcionan los intent del bot.
Falla_Api_externo:valor dicotómico donde 1 indica que se encontró un error de falla de api externo.
Many_Fallbacks_Goto_HH: valor dicotómico donde 1 indica que el bot tuvo varios problemas de entendimiento y detectó la necesidad de pasar automáticamente a un humano
