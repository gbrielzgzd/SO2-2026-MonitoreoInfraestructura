# Informe técnico actualizado: monitoreo de infraestructura con PRTG

**Proyecto:** Plataforma de Monitoreo de Infraestructura TI  
**Asignatura:** Sistemas Operativos II (SO2-2026)  
**Equipo:** LGS SecOps  
**Fecha de actualización:** 24/10/2026  
**Estado:** Propuesta técnica pendiente de instalación y validación

## 1. Introducción

El proyecto tiene como propósito monitorear la infraestructura TI del entorno académico, previsto con Proxmox y máquinas virtuales Linux. Se busca observar el uso de recursos y la disponibilidad de los equipos para identificar oportunamente posibles problemas.

A partir del cambio de herramienta comunicado por el equipo, este informe plantea utilizar **PRTG Network Monitor** como herramienta principal de monitoreo. Este documento es una versión nueva y complementaria: no reemplaza ni elimina los documentos anteriores del repositorio.

## 2. Objetivo general

Proponer una solución de monitoreo basada en PRTG que permita supervisar la disponibilidad y el uso de recursos de la infraestructura seleccionada, registrar resultados y generar alertas cuando se detecten condiciones que requieran atención.

### Objetivos específicos

- Identificar los servidores, máquinas virtuales y servicios que se incluirán en el monitoreo.
- Evaluar y configurar sensores compatibles con los equipos seleccionados.
- Obtener, cuando la configuración y los permisos lo permitan, indicadores de CPU, memoria RAM, almacenamiento y disponibilidad.
- Definir umbrales de alerta apropiados para los indicadores seleccionados.
- Documentar la configuración y validar el funcionamiento mediante pruebas reproducibles.
- Conservar evidencia de los resultados sin publicar contraseñas, tokens ni otros secretos.

## 3. Herramienta seleccionada: PRTG Network Monitor

PRTG Network Monitor es una plataforma de monitoreo de infraestructura que organiza la supervisión mediante dispositivos y sensores. Los sensores comprueban indicadores concretos, por ejemplo disponibilidad, tráfico, uso de recursos o estado de servicios, según el protocolo y el tipo de equipo.

La selección de sensores depende de la tecnología monitoreada, de la conectividad, de los permisos disponibles y de las funciones admitidas por la versión de PRTG instalada. Por eso, las métricas previstas en este informe son objetivos por validar y no resultados que ya se hayan obtenido.

**Documentación oficial:**  
- Sitio de PRTG: https://www.paessler.com/prtg  
- Manual de PRTG: https://www.paessler.com/manuals/prtg  
- Sensores de PRTG: https://www.paessler.com/manuals/prtg/sensors

## 4. Alcance propuesto

### Incluido en la propuesta

- Preparar una instancia de PRTG en un equipo compatible con los requisitos oficiales de la versión elegida.
- Registrar los dispositivos y servicios que el equipo tenga autorización para monitorear.
- Seleccionar y configurar sensores para disponibilidad y, cuando sea técnicamente posible, CPU, RAM y disco.
- Establecer umbrales iniciales de alerta que se ajustarán después de observar el comportamiento real.
- Revisar los estados, datos históricos y alertas desde la interfaz de PRTG.
- Documentar configuración, limitaciones, pruebas y evidencias.

### Fuera del alcance hasta contar con confirmación

- Afirmar que PRTG ya está instalado, configurado o funcionando.
- Asegurar compatibilidad con cada componente del entorno sin probar el sensor correspondiente.
- Publicar direcciones, credenciales o datos de infraestructura que puedan comprometer la seguridad.
- Implementar cambios en producción sin autorización del responsable del entorno.

## 5. Indicadores que se desean monitorear

| Indicador | Propósito | Validación necesaria |
|---|---|---|
| Disponibilidad | Detectar si un equipo o servicio responde. | Elegir un sensor y un método de comprobación adecuado; verificar estados disponibles y no disponibles. |
| CPU | Observar la utilización del procesador. | Confirmar que el sistema operativo o dispositivo exponga la métrica mediante un método compatible y autorizado. |
| Memoria RAM | Identificar consumo elevado o falta de memoria. | Configurar un sensor compatible y contrastar sus datos con el sistema monitoreado. |
| Disco | Revisar espacio utilizado, libre o estado de almacenamiento, según el sensor. | Confirmar qué métrica entrega el sensor y comprobarla en el equipo objetivo. |
| Alertas | Avisar cuando un indicador supere el umbral establecido o un servicio deje de responder. | Simular o identificar una condición controlada y comprobar que la notificación se genere. |

No todos los indicadores necesariamente se obtendrán con un único sensor. La disponibilidad de cada uno depende del dispositivo, del método de acceso y de la versión instalada.

## 6. Diseño de implementación propuesto

1. **Inventario:** identificar las máquinas virtuales Linux, el host o entorno Proxmox y los servicios que se pueden monitorear.
2. **Revisión de requisitos:** comprobar los requisitos oficiales de instalación de PRTG y elegir dónde se ejecutará.
3. **Conectividad y permisos:** verificar rutas de red, firewall y el método autorizado para consultar cada equipo.
4. **Alta de dispositivos:** registrar los objetivos de monitoreo en PRTG.
5. **Selección de sensores:** escoger sensores apropiados para disponibilidad y para las métricas de recursos que estén soportadas.
6. **Configuración inicial:** establecer intervalos de sondeo y umbrales razonables, evitando generar alertas excesivas.
7. **Pruebas:** validar cada sensor por separado y registrar sus resultados.
8. **Documentación:** guardar capturas, configuración no sensible, observaciones y problemas encontrados.
9. **Revisión:** ajustar los sensores y umbrales según la evidencia obtenida.

La supervisión de Proxmox y de las máquinas virtuales Linux debe validarse de manera específica. Antes de elegir un sensor se comprobará en el manual de PRTG la compatibilidad y los requisitos de acceso; no se presupone que todos los indicadores estén disponibles automáticamente.

## 7. Requisitos funcionales propuestos

| ID | Requisito | Criterio de aceptación |
|---|---|---|
| RF-01 | Registrar los dispositivos seleccionados. | Los dispositivos autorizados aparecen configurados en PRTG con identificación clara. |
| RF-02 | Comprobar disponibilidad. | El sensor elegido refleja correctamente un caso disponible y un caso no disponible controlado. |
| RF-03 | Consultar CPU. | Un sensor compatible entrega valores y estos se contrastan con una fuente del sistema objetivo. |
| RF-04 | Consultar memoria RAM. | Un sensor compatible entrega valores verificables de memoria. |
| RF-05 | Consultar almacenamiento. | Un sensor compatible muestra la métrica de disco definida para el alcance. |
| RF-06 | Generar alertas. | Se demuestra una alerta ante una condición de prueba documentada. |
| RF-07 | Conservar evidencia. | Se almacenan capturas y resultados sin secretos ni información sensible innecesaria. |

RF-03, RF-04 y RF-05 solo se marcarán como cumplidos cuando exista evidencia real de que los sensores obtienen datos correctos.

## 8. Plan de pruebas

- **Prueba 1 — Servicio de monitoreo:** verificar que PRTG esté instalado y que sus servicios estén activos.
- **Prueba 2 — Conectividad:** comprobar que el equipo de monitoreo pueda alcanzar los objetivos autorizados.
- **Prueba 3 — Disponibilidad:** validar el comportamiento del sensor frente a un objetivo accesible y un caso de fallo controlado.
- **Prueba 4 — CPU:** comparar los valores reportados por PRTG con una fuente de referencia del equipo monitoreado.
- **Prueba 5 — RAM:** contrastar la lectura del sensor con el estado de memoria del sistema.
- **Prueba 6 — Disco:** verificar que el sensor represente correctamente la métrica de almacenamiento seleccionada.
- **Prueba 7 — Alertas:** confirmar que una condición de prueba genere el estado o la notificación configurada.
- **Prueba 8 — Evidencias:** registrar fecha, objetivo, sensor, resultado esperado, resultado observado y observaciones.

Para cada prueba se debe indicar si fue aprobada, fallida o pendiente. No se deben modificar resultados para aparentar que una prueba fue exitosa.

## 9. Requisitos no funcionales y seguridad

- Limitar el monitoreo a equipos para los que el equipo tenga autorización.
- Utilizar credenciales con los permisos mínimos necesarios.
- No almacenar contraseñas, tokens, claves privadas ni credenciales en GitHub.
- Restringir el acceso a la consola de PRTG y a sus notificaciones según las necesidades del equipo.
- Mantener nombres de dispositivos y sensores consistentes.
- Documentar la versión instalada y los cambios relevantes de configuración.
- Considerar la licencia, los límites de sensores y los requisitos del sistema antes de desplegar la solución.

## 10. Riesgos y aspectos pendientes

- **Compatibilidad:** algunos sensores pueden requerir protocolos, agentes, permisos o configuraciones específicas.
- **Acceso de red:** reglas de firewall o rutas pueden impedir que PRTG consulte los dispositivos.
- **Permisos:** los datos de CPU, RAM o disco pueden no estar disponibles sin habilitar un método de consulta autorizado.
- **Licenciamiento y recursos:** se debe comprobar que la versión seleccionada y la capacidad del equipo sean suficientes para el número de sensores previsto.
- **Alertas excesivas:** umbrales o intervalos inadecuados pueden generar notificaciones innecesarias.
- **Estado real desconocido:** la documentación disponible no demuestra que PRTG haya sido instalado ni probado; debe actualizarse cuando exista evidencia.

## 11. Evidencias que se deben incorporar

- Versión y estado de instalación de PRTG.
- Inventario de dispositivos que se autoriza monitorear.
- Lista de sensores configurados y explicación de su propósito.
- Capturas de los estados y valores obtenidos.
- Resultados de las pruebas de disponibilidad, CPU, RAM, disco y alertas.
- Problemas encontrados y medidas correctivas aplicadas.
- Configuración relevante sin contraseñas ni secretos.
- Referencias a la documentación oficial consultada.

## 12. Conclusión

PRTG Network Monitor se propone como la herramienta principal para el monitoreo de la infraestructura del proyecto. Su uso permitirá centralizar la supervisión mediante dispositivos, sensores, históricos y alertas, siempre que se configuren métodos compatibles con los sistemas objetivo.

La disponibilidad y las métricas de CPU, RAM y disco son objetivos de la propuesta, no funcionalidades verificadas todavía. La implementación se considerará satisfactoria únicamente después de configurar los sensores adecuados, contrastar los datos con los sistemas monitoreados y conservar evidencias reproducibles.

## 13. Referencias

- Paessler, PRTG Network Monitor: https://www.paessler.com/prtg
- Paessler, Manual de PRTG: https://www.paessler.com/manuals/prtg
- Paessler, documentación de sensores: https://www.paessler.com/manuals/prtg/sensors
