# Plataforma de Monitoreo de Infraestructura TI

Proyecto académico de Sistemas Operativos (SO2-2026).  
**Equipo:** LGS SecOps.

## Estado del proyecto

- **Entorno previsto:** Proxmox y máquinas virtuales Linux.
- **Métricas requeridas por el equipo:** CPU, RAM, disco y disponibilidad.
- **Restricción indicada por el equipo:** solo se permite utilizar Prometheus como herramienta de monitoreo.
- **Estado técnico informado previamente:** las herramientas todavía no se habían instalado ni probado. Actualizar este dato cuando existan evidencias nuevas.
- **Implementación:** no se debe considerar funcional hasta que se documenten pruebas reales.

## Descripción

El proyecto busca monitorear infraestructura TI en máquinas virtuales Linux y ayudar a detectar problemas de recursos o disponibilidad. El alcance debe respetar la restricción de utilizar únicamente Prometheus como herramienta de monitoreo.

## Documentación

- [Cuestionario de aprobación y estado del proyecto](docs/cuestionario_aprobacion.md)
- [Definición del MVP y requisitos propuestos](docs/mvp_requisitos.md)

## Herramientas y limitaciones

Prometheus es la única herramienta de monitoreo autorizada según la corrección comunicada por el equipo. No se debe incluir Grafana, Node Exporter, Blackbox Exporter, PostgreSQL, TimescaleDB ni otras herramientas como parte de la solución sin autorización explícita del docente.

**Limitación técnica que debe resolverse:** Prometheus recopila métricas a través de endpoints HTTP que exponen datos en formato compatible. Por sí solo, Prometheus no expone automáticamente las métricas internas de CPU, RAM y disco de cualquier VM Linux, ni comprueba por sí mismo la disponibilidad de un equipo externo. El equipo debe confirmar con el docente si se permiten scripts o endpoints propios que expongan métricas, sin instalar herramientas adicionales. Si no se permite ningún componente complementario, el alcance medible podría limitarse a las métricas internas del propio Prometheus y no cubrir las cuatro métricas del proyecto original.

## Alcance propuesto pendiente de validación

1. Instalar y configurar Prometheus.
2. Confirmar qué endpoints de métricas están permitidos por la consigna.
3. Probar consultas y reglas de Prometheus con datos disponibles.
4. Documentar explícitamente qué métricas pueden obtenerse bajo la restricción.
5. Guardar configuraciones, pruebas y evidencias reales.

No se debe afirmar que CPU, RAM, disco o disponibilidad de las VM están monitorizados hasta comprobar cómo se obtienen y demostrarlo con resultados reales.

## Equipo

- Gabriel Zerpa — Product Owner.
- Leonardo Sebastian Garcia Mendoza — Developer.
- Alvaro Santiago Beltran Menini — Scrum Master.

Las responsabilidades proceden de los archivos de integrantes del repositorio; los entregables concretos por persona deben acordarse.

## Organización y seguridad

Registrar las decisiones en `docs/`, documentar pruebas con capturas o registros y actualizar el cronograma según el avance real. No subir contraseñas, tokens ni credenciales al repositorio.

## Documentación oficial

- https://prometheus.io/docs/
