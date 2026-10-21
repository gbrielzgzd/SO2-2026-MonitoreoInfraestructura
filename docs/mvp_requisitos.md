# MVP y requisitos propuestos

**Proyecto:** Plataforma de Monitoreo de Infraestructura TI  
**Equipo:** LGS SecOps  
**Actualización:** 21/10/2026

> Este documento registra el alcance tras la corrección del equipo: solo se permite utilizar Prometheus como herramienta de monitoreo. No afirma que la solución esté instalada ni probada.

## Decisiones comunicadas

- Entorno previsto: Proxmox y máquinas virtuales Linux.
- Métricas deseadas: CPU, RAM, disco y disponibilidad.
- Restricción de herramientas: únicamente Prometheus.
- Estado de instalación y pruebas: la última información disponible indicaba que las herramientas aún no estaban instaladas ni probadas; actualizar con evidencia nueva si cambió.

## Restricción técnica crítica

Prometheus es principalmente un sistema de recopilación y consulta de series temporales. Normalmente obtiene métricas desde endpoints HTTP que exponen datos en un formato compatible.

Prometheus por sí solo no obtiene automáticamente el uso de CPU, RAM y disco de una VM Linux externa ni verifica directamente la disponibilidad de un equipo externo. Para obtener esas métricas se necesita una fuente de datos compatible. La fuente puede requerir un exporter, un script o un endpoint propio, pero no se debe asumir que esos componentes están permitidos.

**Pregunta que debe resolverse con el docente:** ¿“solo Prometheus” significa que Prometheus es la única herramienta de monitoreo autorizada, permitiendo scripts/endpoints propios, o que está prohibido utilizar cualquier componente complementario?

Hasta tener esa respuesta, las métricas de la VM no deben declararse implementadas ni garantizarse como técnicamente alcanzables bajo las reglas de la asignatura.

## MVP propuesto sujeto a aclaración

1. Instalar y configurar Prometheus en una VM Linux autorizada.
2. Definir los objetivos de recolección permitidos por el docente.
3. Comprobar que Prometheus puede acceder a cada objetivo permitido.
4. Ejecutar consultas PromQL sobre métricas realmente disponibles.
5. Documentar qué indicadores se obtuvieron y cuáles no se pudieron obtener bajo la restricción.
6. Guardar configuración, resultados y capturas de pruebas.

## Requisitos funcionales deseados

| ID | Requisito | Condición de aceptación |
|---|---|---|
| RF-01 | Obtener métricas de CPU de la VM Linux. | Solo se considera cumplido si existe una fuente permitida y Prometheus recoge valores reales. |
| RF-02 | Obtener métricas de RAM. | Solo se considera cumplido si existe una fuente permitida y se verifican los valores. |
| RF-03 | Obtener métricas de disco. | Solo se considera cumplido si existe una fuente permitida y se verifican los valores. |
| RF-04 | Comprobar disponibilidad. | Debe definirse un método permitido y probar respuestas disponibles/no disponibles. |
| RF-05 | Consultar las métricas mediante Prometheus. | Una consulta PromQL devuelve datos reales para el objetivo configurado. |
| RF-06 | Documentar la validación. | Se guardan comandos, configuración sin secretos, resultados y observaciones. |

RF-01 a RF-04 quedan condicionados a la fuente de métricas que permita la consigna. No se deben presentar como completados si no existe una fuente compatible autorizada.

## Componentes

- **Permitido según la corrección:** Prometheus.
- **No incluir sin autorización explícita:** Grafana, Node Exporter, Blackbox Exporter, PostgreSQL, TimescaleDB, otros exporters o herramientas de monitoreo.
- **Pendiente de aclarar:** si se permite escribir un script o endpoint propio para exponer métricas de Linux. Esto no se debe instalar ni implementar como requisito confirmado hasta recibir autorización.

## Pruebas necesarias

- Verificar que el servicio Prometheus está activo.
- Validar la sintaxis de su archivo de configuración.
- Comprobar los objetivos de scraping permitidos.
- Ejecutar consultas PromQL y conservar los resultados.
- Si se autoriza una fuente de métricas para Linux, comprobar CPU, RAM, disco y disponibilidad por separado.
- Registrar errores y limitaciones sin alterar los resultados para hacerlos parecer exitosos.

## Evidencia pendiente

- Versión y estado real de Prometheus.
- Archivo de configuración utilizado, sin credenciales.
- Capturas de objetivos y consultas.
- Resultado de cada prueba.
- Confirmación del docente sobre scripts/endpoints propios.
- Actualización del cronograma de acuerdo con el progreso real.

**Regla de documentación:** ninguna métrica se marca como funcional sin evidencia real y reproducible.
