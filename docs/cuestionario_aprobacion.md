# Cuestionario de aprobación — Plataforma de Monitoreo y Observabilidad de Infraestructura TI

**Curso:** Sistemas Operativos (SO2-2026)  
**Equipo:** LGS SecOps  
**Estado:** borrador de trabajo; debe revisarse y aprobarse por el equipo.

> Criterio de honestidad: este documento distingue lo que ya aparece en el README del repositorio de lo que aún debe confirmarse. Las tecnologías mencionadas son propuestas, no se consideran implementadas por el solo hecho de estar documentadas.

## 1. Problema y valor

**Información que consta en el README:** el proyecto propone recopilar, centralizar, visualizar y analizar métricas de infraestructura TI para facilitar la detección preventiva de problemas.

**Pendiente:** identificar el escenario concreto que se monitoreará, quién experimenta el problema, qué evidencia lo demuestra y qué consecuencias específicas se buscan reducir. Redactar una explicación de menos de 30 segundos cuando se confirme el escenario.

## 2. Objetivos y éxito

**Objetivo registrado en el README:** desarrollar una plataforma de monitoreo y observabilidad que recopile, centralice, visualice y analice métricas de infraestructura TI e incorpore alertas automáticas.

**Pendiente:** establecer indicadores medibles de éxito (por ejemplo, qué métricas se recogerán, qué alertas se demostrarán y qué resultado se considerará correcto), además de objetivos específicos y evidencia de validación.

## 3. Usuarios y requisitos

**Pendiente de definir:** perfiles de usuario, necesidades, funciones detalladas, entradas y salidas de cada función y criterios de aceptación verificables. También falta priorizar requisitos de seguridad, rendimiento, disponibilidad, usabilidad y compatibilidad que correspondan al prototipo.

## 4. Alcance

**Registrado en el README:** prototipo académico de supervisión de infraestructura TI. La implementación definitiva en una infraestructura productiva de gran escala queda fuera del alcance documentado actualmente.

**Pendiente de precisar:** equipos y servicios que se incluirán en la demostración, funciones incluidas y excluidas, restricciones del entorno y qué se eliminaría si fuera necesario reducir el alcance un 40 %.

## 5. MVP

**Pendiente de aprobar:** definir una primera versión funcional que pueda demostrarse dentro del plazo del curso. Especificar las fuentes de métricas, panel mínimo, alertas mínimas y evidencia que demostrará que funciona. Separar explícitamente las funciones posteriores.

## 6. Diseño y viabilidad técnica

El README enumera como **tecnologías propuestas**:
- Prometheus
- PostgreSQL + TimescaleDB
- Grafana
- Node Exporter u otros exporters
- SNMP e ICMP

El README indica que su configuración e integración deben validarse durante la implementación. Por tanto, no se afirma aquí que estén instaladas ni integradas.

**Pendiente:** confirmar las tecnologías finales y su justificación, el sistema operativo y entorno de ejecución, la arquitectura y flujo de datos, los requisitos de hardware, las dependencias externas y las pruebas de concepto necesarias para reducir incertidumbres técnicas.

## 7. Datos, seguridad y calidad

**Pendiente:** enumerar métricas y fuentes reales; definir retención de datos, acceso a paneles, credenciales, permisos, exposición de servicios y protección de la configuración. Especificar pruebas funcionales y de integración, resultados esperados y cómo se registrarán los defectos.

## 8. Plan de desarrollo

El README indica que existe un documento Gantt que debe consultarse, pero su contenido no está incluido en este archivo.

**Pendiente de comprobar con el Gantt vigente:** tareas, responsables, estimaciones, dependencias, fechas, integración, pruebas, correcciones y documentación. Identificar las tareas cuya demora bloquearía al equipo.

## 9. Equipo y riesgos

En los archivos de integrantes del repositorio aparecen estas responsabilidades:
- Gabriel Zerpa: Product Owner.
- Leonardo Sebastian Garcia Mendoza: Developer.
- Alvaro Santiago Beltran Menini: Scrum Master.

**Pendiente:** definir entregables verificables por persona, mecanismo de revisión e integración, tres riesgos principales, mitigación de cada riesgo y plan de continuidad si un integrante no está disponible.

## 10. Preparación para comenzar

Antes de iniciar las funciones principales, el equipo debe comprobar que:
- El problema y los usuarios están definidos.
- El MVP y sus criterios de aceptación están acordados.
- El entorno y los accesos necesarios están disponibles.
- Cada integrante conoce su primera tarea.
- Las instrucciones permiten a un nuevo integrante ejecutar o comprender el prototipo.
- Las decisiones técnicas críticas tienen evidencia de viabilidad.

El cumplimiento de estos puntos aún debe verificarse; este documento no los da por completados.

## 11. Prueba de fracaso

**Pendiente:** identificar las condiciones que podrían hacer fracasar o retrasar el proyecto (alcance excesivo, falta de acceso al entorno, incompatibilidad técnica, retrasos u otras condiciones reales del equipo) y asignar a cada riesgo una medida preventiva, responsable y alternativa.

## Información que necesito del equipo para completar la versión de aprobación

1. **Entorno de prueba:** ¿qué van a monitorear realmente: máquinas virtuales, servidores Linux, equipos de red u otro entorno? ¿Usarán Proxmox u otro entorno?
2. **Métricas y alertas:** ¿qué métricas deben mostrar y qué condiciones deben generar alertas?
3. **Estado técnico real:** ¿ya instalaron o probaron Prometheus, Grafana, TimescaleDB, exporters, SNMP o ICMP? Indiquen cuáles sí, cuáles no y qué evidencias tienen.
4. **Usuarios y demostración:** ¿quién utilizará la plataforma y qué recorrido esperan demostrar en la presentación?
5. **Fecha límite y recursos:** ¿cuándo se entrega y con qué equipos, máquinas virtuales y permisos cuentan?
6. **Documentos existentes:** compartir el informe actualizado y el Gantt para extraer las fechas, requisitos y decisiones reales.

Con esas respuestas se pueden completar el cuestionario, los requisitos funcionales y no funcionales, los criterios de aceptación, el alcance del MVP, la matriz de riesgos y el plan de pruebas sin presentar propuestas como hechos.
