# Plataforma de Monitoreo y Observabilidad de Infraestructura TI

Proyecto académico de Sistemas Operativos (SO2-2026).  
**Equipo:** LGS SecOps.

## Estado real a 13/10/2026

- **Entorno elegido por el equipo:** Proxmox y máquinas virtuales Linux.
- **Métricas prioritarias elegidas:** CPU, RAM, disco y disponibilidad.
- **Estado técnico informado por el equipo:** las herramientas todavía no se han instalado ni probado.
- **Fecha de entrega comunicada:** 14/10/2026. Falta confirmar si se refiere a la aprobación del proyecto o a la entrega final.
- **Cronograma previo:** el Gantt guardado en la biblioteca del equipo marca una entrega tentativa el 05/11/2026. Debe reconciliarse con la fecha de entrega comunicada para mañana.

## Descripción

La propuesta busca centralizar la supervisión de infraestructura TI y ayudar a detectar problemas antes de que provoquen interrupciones. El informe previo plantea métricas, paneles y alertas como resultado esperado; todavía no hay evidencia registrada en este repositorio de una instalación o integración funcional.

## Documentación del repositorio

- [Cuestionario de aprobación y estado del proyecto](docs/cuestionario_aprobacion.md)
- [Definición del MVP y requisitos propuestos](docs/mvp_requisitos.md)

## Tecnologías

El informe previo propone Prometheus, Grafana, Node Exporter u otros exporters, PostgreSQL + TimescaleDB, SNMP e ICMP. **Son tecnologías propuestas y no se consideran instaladas ni validadas.** La selección final del MVP debe confirmarse tras una prueba técnica.

## Alcance mínimo propuesto

Demostrar en una VM Linux de prueba, alojada o disponible mediante Proxmox, métricas de CPU, RAM y disco, además de un indicador de disponibilidad, presentadas en un panel. Es una recomendación pendiente de aprobación del equipo/docente.

## Equipo

- Gabriel Zerpa — Product Owner.
- Leonardo Sebastian Garcia Mendoza — Developer.
- Alvaro Santiago Beltran Menini — Scrum Master.

Las responsabilidades anteriores proceden de los archivos de integrantes del repositorio. Los entregables concretos por persona deben acordarse.

## Organización y seguridad

Registrar las decisiones y tareas en docs/, documentar pruebas con capturas o registros y actualizar el Gantt según el avance real. No subir contraseñas, tokens ni credenciales al repositorio.

## Referencias técnicas incluidas en el informe previo

- https://prometheus.io/docs/
- https://grafana.com/docs/
- https://docs.timescale.com/
