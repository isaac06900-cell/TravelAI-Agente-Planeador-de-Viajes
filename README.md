# TravelAI - Agente Planeador de Viajes

Proyecto desarrollado en n8n para asistir en la planificación de viajes mediante inteligencia artificial.

## Funcionalidades
- Generación de itinerarios
- Consulta de destinos y clima
- Conversión de divisas
- Memoria conversacional
- Consulta y almacenamiento en Google Sheets
- Modificación controlada de presupuestos
- Eliminación de viajes con confirmación
- Restricciones para operaciones fuera de alcance

## Pruebas
El archivo pruebas.csv documenta 10 casos de prueba.
Las capturas se almacenan en evidencias/.

## Limitaciones
Durante las pruebas se presentaron errores HTTP 503 de Google Gemini por alta demanda.
Un registro se guardó correctamente aunque la respuesta final del agente falló.
Se recomienda verificar registros antes de repetir operaciones de escritura.

## Integrantes
Pendiente de completar: nombres, matrículas y roles.

## Seguridad
No incluir API keys, tokens ni contraseñas en los archivos de entrega.
Revisar el JSON exportado antes de compartirlo.
## Integrantes del equipo

| Integrante | Matrícula | Rol |
|---|---|---|
| Isaac Jasiel Herrera Avila | 24040275 | Líder técnico, arquitecto y desarrollador principal del agente de IA |
| Andrew Neftali Chaidez Lopez | 24040127 | Responsable de integraciones, pruebas y aseguramiento de calidad |

## Distribución de responsabilidades

### Isaac Jasiel Herrera Avila
**Líder técnico, arquitecto y desarrollador principal del agente de IA**

- Diseño de la arquitectura general del agente TravelAI en n8n.
- Desarrollo y configuración del AI Agent mediante Google Gemini.
- Diseño y optimización del system prompt.
- Implementación de memoria conversacional.
- Desarrollo de la lógica de planificación de viajes.
- Implementación de guardrails y reglas de seguridad.
- Desarrollo de la lógica de confirmación para modificar y eliminar viajes.
- Supervisión técnica, depuración y optimización del sistema.

### Andrew Neftali Chaidez Lopez
**Responsable de integraciones, pruebas y aseguramiento de calidad**

- Configuración de Google Sheets para almacenar viajes.
- Integración de herramientas y servicios externos.
- Configuración de conexiones y credenciales.
- Elaboración y ejecución de los 10 casos de prueba.
- Registro de resultados y recopilación de evidencias.
- Documentación técnica y elaboración del README.
- Validación del funcionamiento de las integraciones.

## Trabajo colaborativo

Ambos integrantes participan en el desarrollo, las pruebas y la revisión final del proyecto.

## Reflexión técnica del proyecto

### Problemas encontrados

Durante el desarrollo y las pruebas de TravelAI encontramos diferentes dificultades técnicas.

1. **Disponibilidad de Google Gemini:** En varias ejecuciones, el modelo devolvió errores HTTP 503 debido a una alta demanda del servicio. Esto impidió obtener respuestas aunque el workflow estuviera correctamente configurado.

2. **Compatibilidad de modelos:** Algunos modelos de Gemini dejaron de estar disponibles para nuevas cuentas, lo que produjo errores HTTP 404. Fue necesario cambiar la configuración y probar alternativas compatibles.

3. **Operaciones de escritura:** En una prueba, Google Sheets guardó correctamente un viaje, pero el agente falló antes de confirmar la operación. Esto mostró el riesgo de duplicar registros si se repite una solicitud sin verificar primero los datos existentes.

4. **Seguridad de operaciones:** Se implementaron reglas de confirmación para evitar eliminar viajes accidentalmente y limitar las modificaciones a las operaciones autorizadas.

### Aprendizajes

El proyecto permitió comprender cómo integrar un agente de inteligencia artificial con memoria conversacional, herramientas externas y almacenamiento en Google Sheets.

También aprendimos la importancia de validar los datos, comprobar las operaciones antes de repetirlas, documentar los errores y establecer restricciones para proteger la información del usuario.

### Mejoras futuras

Como mejoras futuras proponemos implementar un mecanismo que evite registros duplicados, gestionar automáticamente errores temporales de los servicios externos y ampliar las pruebas de seguridad y recuperación ante fallos.
