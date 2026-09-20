# Agente IA para Gestión de Reclamos Operativos

## Descripción

Este proyecto fue desarrollado como parte del curso de Automatización con IA de Coderhouse.

El objetivo es automatizar la recepción, clasificación y registro de reclamos operativos relacionados con carga aérea de importación.

El flujo fue desarrollado en n8n y utiliza un Agente de IA que recibe la consulta del usuario mediante un chat, identifica los datos necesarios, clasifica el reclamo y registra la información en Google Sheets.

## Objetivo del flujo

Automatizar el procesamiento de reclamos provenientes de Atención al Cliente, reduciendo tareas manuales y mejorando la trazabilidad de los casos.

Para procesar un reclamo se identifican los siguientes datos:

- Número de caso
- Número de guía madre
- Número de guía hija
- Motivo del reclamo

El agente clasifica cada reclamo en una de las siguientes categorías:

- CARGA_EXTRAVIADA
- BONIFICACION_DEMORA_OPERATIVA
- GUIA_CAIDA
- OTROS

## Funcionamiento

El flujo sigue las siguientes etapas:

1. El usuario inicia la conversación mediante un Chat Trigger.
2. El agente de IA analiza la consulta y extrae los datos del reclamo.
3. Simple Memory permite mantener el contexto de la conversación.
4. Structured Output Parser genera una salida estructurada con los datos obtenidos.
5. Se valida si se encuentran disponibles todos los datos obligatorios.
6. Si faltan datos, el flujo solicita al usuario la información necesaria.
7. Si los datos están completos, el reclamo continúa para su registro.
8. Google Sheets almacena la información del caso junto con la fecha y hora de registro.
9. Se envía un correo de Log de Control para mantener trazabilidad de la ejecución.
10. Finalmente, el chat confirma al usuario que el reclamo fue registrado correctamente.

## Tecnologías utilizadas

- n8n
- Inteligencia Artificial / LLM
- Groq Chat Model
- Simple Memory
- Structured Output Parser
- Google Sheets
- Gmail
- Chat Trigger

## Validaciones

El flujo contempla diferentes controles:

- Verificación de datos obligatorios.
- Prevención del registro de información incompleta.
- Clasificación automática del motivo del reclamo.
- Salida estructurada mediante Output Parser.
- Registro de fecha y hora de ejecución.
- Log de Control mediante correo electrónico.
- Confirmación al usuario una vez registrado el reclamo.

## Resultado

El proyecto permite centralizar y estructurar información que originalmente puede recibirse como texto libre, transformándola en datos utilizables para seguimiento y análisis posterior.

Esto permite mejorar la trazabilidad de los reclamos y reducir tareas administrativas manuales.

## Autor

Vanesa Cigarroa

Proyecto realizado para Coderhouse.
