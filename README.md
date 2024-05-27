# Mentoría 2024
¿Cómo saber si el paciente va a asistir a su consulta? Predicción de turnos médicos con Machine Learning

Mentor/a: Eugenia Haluszka

Mail de contacto: ehaluszka@unc.edu.ar

## Introducción
### Descripción y objetivo del proyecto 
El dataset a trabajar presenta información sobre los turnos médicos sacados, a través de un asistente conversacional, por los pacientes de diversos centros de salud. El objetivo de esta mentoría radica en reconocer cómo será el comportamiento de un paciente ante un determinado turno, ¿asistirá? ¿no asistirá? Identificar estas situaciones permite a la clínica poder tomar acciones previas, como por ejemplo enviar notificaciones a lxs pacientes que no vayan a asistir, entre otros beneficios.

### Con éste proyecto trataremos de responder algunas de las siguientes preguntas
- Todos los centros médicos presentan el mismo comportamiento de sus pacientes? De no ser así, ¿cuáles son las principales diferencias y a qué se le atribuye?
- ¿Existen ciertos patrones o características similares entre quienes asisten y quienes no asisten a los turnos médicos?
- ¿Cuáles son las características que resultan de gran relevancia como predictoras de asistencia a turnos? ¿Por qué cree que es así?
- ¿Cuál cree que es el hospital, especialidad y o especialista que presenta las tasas más altas de asistencia? ¿Y las más bajas? ¿Por qué cree que se da de esta manera?
- De acuerdo con la predicción de asistir o no a un turno, al observar los datos de asistencia por clínica, ¿considera que hay clases desbalanceadas? ¿Qué estrategia se podría implementar para solucionarlo?
- ¿Existe la misma asistencia durante todo el periodo estudiado?¿Cambia en algunos meses, días o semanas?¿A qué podría deberse?
- ¿Qué métricas debería considerar para evaluar mi modelo?

### Motivación
La asistencia a turnos médicos es esencial para la calidad del cuidado del paciente y la eficiencia de los recursos médicos. La no asistencia puede desperdiciar tiempo y recursos, y afectar negativamente la salud de los pacientes.

Con el avance en análisis de datos y técnicas de predicción, es posible anticipar la probabilidad de que un paciente falte a su cita. Predecir estas ausencias permite implementar estrategias como recordatorios personalizados y reprogramación proactiva, beneficiando tanto a pacientes como a proveedores de servicios de salud.

En esta serie de prácticos, desarrollaremos y evaluaremos modelos predictivos utilizando datos históricos de citas médicas. Exploraremos y prepararemos estos datos, construyendo modelos para predecir la asistencia y evaluando su efectividad. Nuestro objetivo es mejorar la gestión de citas médicas, reducir ausencias y contribuir a un sistema de salud más eficiente.

## Descripción del dataset
El dataset con el que trabajaremos este práctico consta de 47k filas (47088 para ser específicos) y 21 columnas. Corresponde a datos provenientes de turnos médicos, con el comportamiento final de si la persona asistió o no (attendance). Estos datos fueron extraídos a partir de las conversaciones que tienen las personas con el asistente conversacional, a partir del canal de Whatsapp. El dataset presentado corresponde al periodo desde el 11 de abril de 2023 al 30 de noviembre.

El significado de cada columna es el siguiente:

**doc_id**: Es el ID único que tiene cada médicx en cada clínica y sede.
**doc_full_name**: Nombre y apellido de cada especialista anonimizado.
**msp_name**: Nombre de la especialidad médica.
**msp_id**: ID de la especialidad médica único en cada clínica y sede.
**hos_id**: Nombre de la clínica anonimizado.
**heq_id**: ID de la sede de cada clínica. Hay algunos centros médicos que son monosede y otros multisede.
**hin_name**: Nombre de la obra social, particular o servicio de seguro de salud con el cual realiza la consulta médica.
**hin_id**: ID del hin_name el cual resulta único en cada clínica y sede.
**age_avg**: Estimación del promedio de edad calculado a partir del DNI de lxs pacientes.
**dni_asistance_rate**: Tasa de asistencia de cada paciente. Cantidad de turnos que ha asistido cada paciente históricamente/Cantidad de turnos que ha sacado cada paciente históricamente*100.
**doc_asistance_rate**: Tasa de asistencia de cada especialista por hospital y sede. Cantidad de pacientes que han asistido históricamente por especialista/Cantidad de pacientes que han sacado turno históricamente por especialista*100.
**msp_asistance_rate**: Tasa de asistencia de cada especialidad médica por hospital y sede. Cantidad de pacientes que han asistido históricamente por especialidad/Cantidad de pacientes que han sacado turno históricamente por especialidad*100.
**hosheq_asistance_rate**: Tasa de asistencia global de cada hospital y sede. Cantidad de pacientes que han asistido históricamente por hospital y sede/Cantidad de pacientes que han sacado turno históricamente por hospital y sede*100.
**app_start_dt**: Fecha del turno médico.
**action_A_count**: Cantidad de turnos sacados históricamente por el paciente a través del asistente conversacional.
**action_B_count**: Cantidad de turnos cancelados históricamente por el paciente a através del asistente conversacional.
**action_C_count**: Cantidad de veces que el paciente consultó su turno (ver citas pendientes).
**app_days_gap**: Distancia en días entre la fecha en que la persona realizó la solicitud del turno y la fecha del turno efectivamente.
**patient_id**: ID único de cada paciente dentro de cada clínica y sede.
**event_id**: ID único de cada turno médico global.
**attendance**: Variable que indica 0 si la persona no asistió a su turno programado y 1 si la persona asistió.
