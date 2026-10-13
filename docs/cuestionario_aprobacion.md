# Cuestionario de aprobación — Plataforma de Monitoreo y Observabilidad de Infraestructura TI

**Curso:** Sistemas Operativos (SO2-2026)  
**Equipo:** LGS SecOps  
**Última revisión:** 13/10/2026  
**Estado:** borrador para revisión del equipo; no equivale a aprobación del docente.

## Cómo leer este documento

- **Confirmado por el equipo:** información indicada directamente por el equipo.
- **Registrado en documentos previos:** información que aparece en el informe o Gantt guardado del proyecto.
- **Propuesta pendiente de aprobación:** recomendación que aún debe aceptar el equipo.
- **Pendiente:** dato sin evidencia suficiente.

## 1. Problema y valor

**Registrado en el informe:** la propuesta busca resolver la detección tardía de fallas en infraestructura TI cuando no existe una vista centralizada de métricas y alertas. Los posibles usuarios descritos son administradores de sistemas/redes, personal de soporte y responsables de infraestructura.

**Pendiente de validación:** documentar evidencia concreta del problema en el entorno de prueba. El informe describe el problema general, pero no se ha documentado una entrevista ni una prueba de diagnóstico.

**Explicación breve propuesta:** “El proyecto busca que soporte revise desde un panel el estado de máquinas virtuales Linux y detecte si una máquina deja de responder o consume demasiados recursos, en vez de descubrirlo únicamente cuando aparece una falla”. Debe ser revisada y aprobada por el equipo.

## 2. Objetivos y éxito

**Objetivo registrado en el informe:** desarrollar una plataforma que recopile, centralice, visualice y analice métricas de infraestructura TI e incorpore alertas automáticas.

**Entorno confirmado por el equipo:** Proxmox y máquinas virtuales Linux.  
**Métricas confirmadas por el equipo:** CPU, RAM, disco y disponibilidad.  
**Estado confirmado:** las herramientas todavía no se han instalado ni probado.

**Criterios de éxito propuestos para el MVP:**
1. Recoger CPU, RAM y uso de disco de una VM Linux de prueba.
2. Distinguir si la VM está disponible o no responde.
3. Mostrar las métricas en un panel.
4. Demostrar una prueba de indisponibilidad o condición definida y registrar el resultado.
5. Documentar instalación, configuración y limitaciones.

Son propuestas: el equipo debe confirmar el número de VM, los umbrales y las pruebas viables.

## 3. Usuarios y requisitos

**Usuarios propuestos en el informe:** administradores de red/sistemas, soporte TI y gestores de infraestructura. Para el MVP académico se recomienda como usuario primario al integrante que administra el entorno y revisa el panel.

### Requisitos funcionales propuestos
- RF-01: recopilar uso de CPU de las VM Linux configuradas.
- RF-02: recopilar uso de memoria RAM.
- RF-03: recopilar uso de disco.
- RF-04: mostrar la disponibilidad de la VM monitorizada.
- RF-05: mostrar las métricas en un panel centralizado.
- RF-06: permitir una prueba demostrable de indisponibilidad o condición crítica y registrar el resultado.

### Criterios de aceptación propuestos
- RF-01 a RF-03: la métrica aparece en el panel y cambia cuando cambia el uso del recurso.
- RF-04: el panel identifica una VM configurada como disponible y detecta una interrupción de prueba.
- RF-05: el panel permite identificar la VM y consultar valores recientes.
- RF-06: el equipo conserva una captura o registro de la prueba y anota el resultado.

No se afirma que estas funciones estén implementadas. Los umbrales numéricos quedan pendientes de acuerdo.

## 4. Alcance

**Confirmado:** Proxmox y VM Linux; métricas prioritarias CPU, RAM, disco y disponibilidad.

**Alcance mínimo propuesto:** demostrar el monitoreo de una VM Linux de prueba, con las tres métricas de recursos y un indicador de disponibilidad visibles en un panel.

**Fuera del MVP inicial, salvo que la evaluación lo exija:** monitoreo de routers/switches por SNMP, múltiples canales de notificación, trazas distribuidas, despliegue productivo de gran escala y alta disponibilidad del propio sistema de monitoreo.

**Pendiente:** confirmar qué VM estará disponible, permisos administrativos y funciones exigidas por la evaluación.

## 5. MVP

La primera versión funcional recomendada se limita a: preparar o seleccionar una VM Linux autorizada; instalar una herramienta de recolección y un exporter compatible; recoger CPU, RAM y disco; configurar la detección de disponibilidad; visualizar los datos; ejecutar y registrar una prueba básica.

**Tecnologías propuestas en el informe anterior:** Prometheus, Grafana, Node Exporter u otros exporters, PostgreSQL + TimescaleDB, SNMP e ICMP. El equipo confirma que aún no se han instalado ni probado. Se recomienda empezar por la ruta mínima viable y añadir almacenamiento o monitoreo de red solo si resulta necesario y alcanzable. La simplificación requiere aprobación del equipo/docente.

## 6. Diseño y viabilidad técnica

**Entorno confirmado:** Proxmox y VM Linux. **Herramientas instaladas/probadas:** ninguna, según la respuesta del equipo.

**Stack propuesto en el informe, sin validar en la práctica:** Prometheus para recolectar métricas; Node Exporter u otro exporter para métricas Linux; Grafana para visualizar; PostgreSQL + TimescaleDB para almacenamiento histórico; SNMP/ICMP para dispositivos de red. La necesidad de la base de datos adicional y del monitoreo de red para el MVP debe revisarse.

**Pruebas técnicas prioritarias:** comprobar acceso a la VM, exposición de métricas por el exporter, recolección por Prometheus y visualización en el panel. Registrar errores y no declarar una integración terminada sin evidencia.

## 7. Datos, seguridad y calidad

**Datos previstos:** métricas de CPU, RAM, disco y estado de disponibilidad de las VM Linux.

**Pendiente:** frecuencia de recolección, retención, umbrales, permisos, puertos expuestos y notificaciones.

**Medidas mínimas recomendadas:** no subir contraseñas ni tokens; limitar el acceso a paneles y servicios al laboratorio; documentar puertos y permisos necesarios; registrar versiones y configuraciones sin credenciales.

**Pruebas propuestas:** prueba por componente, integración de recolección y panel, prueba de disponibilidad y revisión de resultados mediante capturas o registros. No hay resultados de prueba confirmados todavía.

## 8. Plan de desarrollo y fecha

**Fecha de entrega comunicada:** mañana, 14/10/2026. Falta confirmar si se refiere al cuestionario de aprobación o a la entrega final del proyecto.

**Gantt previo:** el archivo “Diagrama_Gantt_Mejorado_Monitoreo_TI.pdf” presenta un cronograma tentativo de octubre a noviembre de 2026 y marca presentación/entrega para el 5 de noviembre. El informe previo también incluye ese calendario tentativo. Las fechas no demuestran que las tareas se hayan completado.

**Conflicto de planificación:** el Gantt contempla tareas de instalación/configuración que, según el equipo, todavía no han comenzado. Debe actualizarse al avance real y priorizar el MVP.

### Plan de choque propuesto para el 14/10
- 13/10: confirmar alcance mínimo, accesos a Proxmox/VM Linux y responsabilidades; preparar documentación de aprobación.
- 14/10: presentar la documentación de aprobación y un plan realista de instalación y pruebas.
- Después de la aprobación: instalar por etapas, validar cada componente y actualizar el Gantt según los resultados.

Este plan es una propuesta, no una afirmación de tareas ya realizadas.

## 9. Equipo y riesgos

**Responsabilidades registradas en los archivos de integrantes:** Gabriel Zerpa — Product Owner; Leonardo Sebastian Garcia Mendoza — Developer; Alvaro Santiago Beltran Menini — Scrum Master.

### Riesgos principales propuestos
1. **Tiempo insuficiente para integrar todo el stack.** Mitigación: reducir el MVP a una VM y priorizar las cuatro métricas.
2. **Falta de acceso/conectividad a Proxmox o la VM.** Mitigación: verificar permisos y red antes de instalar.
3. **Problemas de configuración o incompatibilidad.** Mitigación: probar componentes por separado y guardar registros.

El equipo debe validar los riesgos, asignar responsables y acordar la revisión e integración de cambios.

## 10. Preparación para comenzar

- [ ] Confirmar objetivo del MVP y criterios de aceptación.
- [ ] Confirmar acceso autorizado a Proxmox y a una VM Linux.
- [ ] Aprobar el conjunto mínimo de herramientas.
- [ ] Asignar responsables y tareas inmediatas.
- [ ] Registrar decisiones y actualizar el Gantt.
- [ ] Definir cómo guardar evidencia de instalación, métricas y pruebas.

Las casillas quedan sin marcar porque no se ha aportado evidencia de que estén completadas.

## 11. Prueba de fracaso

El proyecto podría retrasarse si no hay acceso a las VM, si se intenta implementar todo el alcance de red/almacenamiento/alertas a la vez o si no se valida la conectividad entre componentes. La mitigación recomendada es comenzar con una VM Linux, demostrar las métricas prioritarias y añadir funciones solo después de que la base funcione.

## Documentos fuente consultados

- “Informe_Actualizado_Plataforma_Monitoreo_TI.docx/.pdf”: problema, objetivo, tecnologías propuestas, requisitos generales, riesgos y resultados esperados.
- “Diagrama_Gantt_Mejorado_Monitoreo_TI.pdf”: cronograma tentativo octubre/noviembre de 2026.
- Respuestas del equipo: Proxmox + VM Linux; CPU/RAM/disco/disponibilidad; herramientas no instaladas ni probadas; fecha comunicada 14/10/2026.

Mantener la documentación sincronizada con evidencia real. Una propuesta no debe presentarse como hecho hasta que el equipo la confirme o implemente.
