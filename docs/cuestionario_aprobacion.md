# Cuestionario de aprobación — Plataforma de Monitoreo de Infraestructura TI

**Curso:** Sistemas Operativos (SO2-2026)  
**Equipo:** LGS SecOps  
**Actualización:** 21/10/2026  
**Estado:** documento de trabajo; no equivale a aprobación del docente.

## Cómo leer este documento

- **Confirmado por el equipo:** información comunicada directamente por el equipo.
- **Registrado en documentos previos:** información que aparecía en el informe o Gantt anterior.
- **Propuesta pendiente de aprobación:** recomendación aún no aceptada formalmente.
- **Pendiente:** dato que necesita aclaración o evidencia.

## 1. Problema y objetivo

El proyecto busca monitorear infraestructura TI sobre Proxmox y máquinas virtuales Linux, con interés en CPU, RAM, disco y disponibilidad.

Las métricas deseadas no deben describirse como implementadas hasta que Prometheus las recoja y se presenten resultados reales.

## 2. Restricción tecnológica comunicada

El equipo informó que el docente corrigió el proyecto para permitir **únicamente Prometheus** como herramienta de monitoreo.

Por tanto, el diseño actualizado no debe incluir Grafana, Node Exporter, Blackbox Exporter, PostgreSQL, TimescaleDB ni otras herramientas como parte de la solución sin autorización explícita.

## 3. Aclaración técnica necesaria

Prometheus recopila métricas de endpoints que exponen datos en un formato compatible. Por sí solo no obtiene automáticamente las métricas de CPU, RAM y disco de una VM Linux externa ni verifica directamente la disponibilidad de ese equipo.

Debe consultarse al docente:

**¿La restricción “solo Prometheus” permite crear un script o endpoint propio que exponga métricas para que Prometheus las recoja, siempre que no se instale otra herramienta de monitoreo?**

Esta decisión afecta la viabilidad de los requisitos RF-01 a RF-04. Hasta que se aclare, la documentación no debe prometer que todas las métricas del proyecto original podrán obtenerse.

## 4. Requisitos deseados

- RF-01: obtener uso de CPU de la VM Linux.
- RF-02: obtener uso de RAM.
- RF-03: obtener uso de disco.
- RF-04: comprobar disponibilidad.
- RF-05: consultar los datos disponibles mediante Prometheus.
- RF-06: documentar pruebas, resultados y limitaciones.

RF-01 a RF-04 están condicionados a una fuente de métricas permitida y comprobada. RF-05 y RF-06 pueden validarse con los objetivos y datos que estén disponibles bajo la consigna.

## 5. Alcance mínimo propuesto

1. Instalar y configurar Prometheus en un entorno Linux autorizado.
2. Confirmar los objetivos de scraping permitidos.
3. Validar la configuración y conectividad.
4. Ejecutar consultas PromQL con métricas reales disponibles.
5. Documentar resultados y limitaciones.
6. Si el docente autoriza una fuente propia de métricas, ampliar las pruebas a CPU, RAM, disco y disponibilidad de la VM.

Este alcance es una propuesta y no una afirmación de implementación terminada.

## 6. Seguridad y calidad

- No guardar contraseñas, tokens ni credenciales en GitHub.
- No exponer servicios a redes no autorizadas.
- Documentar los puertos y permisos que realmente se utilicen.
- Guardar el archivo de configuración usado y validar su sintaxis.
- Conservar evidencia de las consultas y pruebas ejecutadas.
- Distinguir en el informe resultados reales, propuestas y limitaciones.

## 7. Estado técnico

La última información técnica disponible indicaba que las herramientas aún no se habían instalado ni probado. Si el estado ha cambiado, actualizar este apartado con evidencia, no solo con una declaración.

## 8. Preguntas pendientes

- [ ] ¿Se permite crear scripts/endpoints propios para exponer métricas de Linux?
- [ ] ¿Qué método de disponibilidad acepta el docente?
- [ ] ¿La evaluación exige CPU, RAM, disco y disponibilidad de la VM externa, o basta con demostrar Prometheus y sus métricas disponibles?
- [ ] ¿Qué fecha de entrega y entregables siguen vigentes tras la corrección?
- [ ] ¿Quién realizará cada instalación, prueba y revisión?

## 9. Equipo

Responsabilidades registradas en los archivos de integrantes:
- Gabriel Zerpa — Product Owner.
- Leonardo Sebastian Garcia Mendoza — Developer.
- Alvaro Santiago Beltran Menini — Scrum Master.

## 10. Criterio de aprobación del MVP

El MVP solo debe declararse listo cuando:
1. La configuración de Prometheus sea válida.
2. Los objetivos permitidos tengan estado verificable.
3. Las consultas utilizadas devuelvan datos reales.
4. Los resultados se documenten con capturas o registros.
5. Las limitaciones impuestas por el uso exclusivo de Prometheus estén explicadas.

## Fuentes y límites

Este documento conserva el contexto del informe y Gantt anteriores, pero adapta la propuesta a la restricción comunicada por el equipo. No se han aportado resultados de instalación o pruebas que permitan afirmar que el sistema ya funciona.
