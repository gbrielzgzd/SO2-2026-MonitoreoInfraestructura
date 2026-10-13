# MVP y requisitos propuestos

**Proyecto:** Plataforma de Monitoreo y Observabilidad de Infraestructura TI  
**Equipo:** LGS SecOps  
**Última actualización:** 13/10/2026

> Este documento es una propuesta de trabajo, no una constancia de implementación. El equipo indicó que todavía no ha instalado ni probado las herramientas.

## Decisiones confirmadas por el equipo

- Entorno previsto: Proxmox y máquinas virtuales Linux.
- Métricas prioritarias: CPU, RAM, disco y disponibilidad.
- Estado técnico: las herramientas aún no se han instalado ni probado.
- Fecha de entrega comunicada: 14/10/2026; falta confirmar si corresponde al cuestionario de aprobación o a la entrega final.

## Contexto del informe previo

El informe propone centralizar métricas y ayudar a detectar fallas de forma preventiva. Propone Prometheus, Grafana, Node Exporter u otros exporters, PostgreSQL + TimescaleDB, SNMP e ICMP. Estas tecnologías todavía requieren instalación y validación. El Gantt previo marca una entrega tentativa el 05/11/2026, por lo que debe aclararse la diferencia con la fecha comunicada para mañana.

## MVP recomendado

La recomendación es iniciar con una sola VM Linux de prueba y demostrar:

1. Recopilación de uso de CPU.
2. Recopilación de uso de RAM.
3. Recopilación de uso de disco.
4. Detección de disponibilidad de la VM.
5. Visualización de métricas en un panel.
6. Una prueba documentada que demuestre la recolección y detección de disponibilidad.

El equipo y el docente deben aprobar el alcance antes de considerarlo definitivo.

## Requisitos funcionales propuestos

| ID | Requisito | Criterio de aceptación propuesto |
|---|---|---|
| RF-01 | Recoger CPU de la VM Linux. | La métrica aparece en el panel y cambia cuando varía la carga. |
| RF-02 | Recoger uso de RAM. | El panel muestra la métrica de memoria de la VM. |
| RF-03 | Recoger uso de disco. | El panel muestra el uso del disco monitorizado. |
| RF-04 | Detectar disponibilidad. | Una VM disponible se identifica como activa y una interrupción de prueba se detecta. |
| RF-05 | Centralizar la visualización. | El panel permite identificar la VM y consultar sus métricas recientes. |
| RF-06 | Registrar la validación. | Se conserva captura o registro con resultado y observaciones de la prueba. |

Estos criterios son propuestas iniciales; falta que el equipo los apruebe y defina umbrales numéricos si corresponden.

## Requisitos no funcionales propuestos

- **Seguridad:** no almacenar credenciales en GitHub; limitar accesos a los servicios del laboratorio.
- **Usabilidad:** panel con nombres claros para VM y métricas.
- **Mantenibilidad:** registrar pasos de instalación y configuración sin secretos.
- **Confiabilidad de datos:** verificar que los datos se actualicen y anotar interrupciones o limitaciones.

No se han fijado métricas cuantitativas de rendimiento o disponibilidad; se deben acordar si el docente las exige.

## Arquitectura técnica candidata

1. **Infraestructura:** Proxmox y una VM Linux autorizada.
2. **Recolección:** Prometheus y un exporter compatible, por ejemplo Node Exporter.
3. **Visualización:** Grafana.
4. **Almacenamiento adicional:** PostgreSQL + TimescaleDB aparecen en el informe anterior; confirmar si son necesarios para la demostración mínima.
5. **Monitoreo de red:** SNMP e ICMP aparecen en el informe previo; se consideran fuera del primer MVP salvo que la evaluación lo requiera.

La arquitectura es candidata, no está desplegada ni validada.

## Plan inmediato propuesto

- **13/10:** confirmar alcance, permisos y acceso a la VM; aprobar requisitos.
- **14/10:** entregar la documentación de aprobación y presentar un plan realista de implementación. Si la fecha se refiere al proyecto completo, revisar inmediatamente el alcance y consultar al docente.
- **Después de la aprobación:** instalar por etapas, comprobar cada componente, guardar evidencia y actualizar el Gantt según el avance real.

## Riesgos y mitigación

| Riesgo | Mitigación propuesta |
|---|---|
| Tiempo insuficiente para integrar todo el stack. | Empezar por una VM y las cuatro métricas prioritarias. |
| Falta de acceso a Proxmox o a la VM. | Verificar permisos y conectividad antes de instalar. |
| Error de configuración o incompatibilidad. | Probar componentes por separado y guardar registros de error. |

## Evidencia pendiente

- Captura o registro de acceso a la VM de prueba.
- Versiones de las herramientas que se instalen.
- Configuración sin credenciales.
- Capturas de métricas reales.
- Resultado de la prueba de disponibilidad.
- Gantt actualizado con responsables, fechas y dependencias reales.

No debe marcarse ninguna función como terminada hasta contar con la evidencia correspondiente.
