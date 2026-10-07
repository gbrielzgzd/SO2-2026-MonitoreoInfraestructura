# Plataforma de Monitoreo y Observabilidad de Infraestructura TI

Proyecto académico de Sistemas Operativos (SO2-2026).

## Descripción
El proyecto propone una plataforma para recopilar, centralizar, visualizar y analizar métricas de infraestructura TI, con el objetivo de facilitar la detección preventiva de problemas.

## Objetivo
Desarrollar una plataforma de monitoreo y observabilidad que permita recopilar, centralizar, visualizar y analizar métricas de infraestructura TI e incorporar alertas automáticas.

## Alcance
Prototipo académico para supervisión de infraestructura TI. La implementación definitiva en una infraestructura productiva de gran escala queda fuera del alcance documentado actualmente.

## Tecnologías propuestas
- Prometheus
- PostgreSQL + TimescaleDB
- Grafana
- Node Exporter / otros exporters
- SNMP e ICMP

Estas tecnologías aparecen en la propuesta del proyecto; la configuración e integración deben validarse durante la implementación.

## Estructura del repositorio
```text
.
├── README.md
├── .gitignore
├── docs/
│   ├── proyecto/
│   │   ├── informe/
│   │   ├── presentacion/
│   │   └── gantt/
│   ├── requisitos/
│   ├── arquitectura/
│   ├── diseno/
│   ├── pruebas/
│   ├── manuales/
│   └── referencias/
├── src/
├── config/
├── dashboards/
├── database/
│   ├── migrations/
│   └── scripts/
├── tests/
│   ├── functional/
│   └── integration/
├── scripts/
└── resources/
    ├── diagrams/
    ├── images/
    └── examples/
```

## Documentación
Los documentos fuente del proyecto son el informe actualizado y el diagrama de Gantt. Deben ubicarse en:
- `docs/proyecto/informe/`
- `docs/proyecto/gantt/`

La presentación se añadirá en `docs/proyecto/presentacion/` cuando esté disponible.

## Estado actual
La documentación inicial describe objetivos, alcance, requisitos propuestos, arquitectura general, tecnologías consideradas, riesgos y un cronograma tentativo. La implementación técnica debe añadirse y documentarse conforme se desarrolle.

## Flujo de trabajo
1. Registrar cada tarea, bug o mejora como una GitHub Issue.
2. Asignar responsable, área y prioridad.
3. Crear una rama por tarea cuando corresponda.
4. Vincular Pull Requests con las Issues.
5. Actualizar el estado en GitHub Projects.
6. Documentar pruebas y decisiones técnicas en `docs/`.

## Seguridad
No incluir contraseñas, tokens, claves privadas ni datos sensibles. Las configuraciones de ejemplo deben permanecer libres de credenciales.

## Cronograma
Consultar el documento Gantt. Sus fechas son tentativas y deben contrastarse con el avance real.

## Referencias
- https://prometheus.io/docs/
- https://grafana.com/docs/
- https://docs.timescale.com/
