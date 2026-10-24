# Cuestionario de aprobación del proyecto — Respuestas basadas en PRTG

**Proyecto:** SO2-2026-MonitoreoInfraestructura  
**Documento base:** Informe técnico actualizado: monitoreo de infraestructura con PRTG  
**Fecha:** 24/10/2026  
**Estado:** Respuestas preliminares para revisión del equipo. Los puntos que requieren evidencia, decisiones del equipo o pruebas se identifican expresamente como pendientes.

> **Criterio de elaboración:** Las respuestas se basan en el informe de PRTG y en la información disponible del proyecto. No se afirma que PRTG esté instalado, configurado o validado; el informe lo presenta como propuesta técnica pendiente de instalación y comprobación. Los responsables, estimaciones, evidencias y acuerdos que no constan en la documentación deben completarse por el equipo.

## 1. Problema y valor

**1. ¿Pueden explicar el problema en menos de 30 segundos sin mencionar ninguna tecnología?**  
La infraestructura informática necesita supervisión para detectar a tiempo falta de disponibilidad, consumo elevado de recursos y problemas de almacenamiento. Sin una visión centralizada, los responsables pueden tardar en identificar incidentes y evaluar su impacto.

**2. ¿Quién tiene el problema y quién utilizará la solución?**  
Los posibles usuarios son las personas responsables de administrar y supervisar la infraestructura TI, así como los integrantes del equipo que necesitan observar el estado de los equipos y máquinas virtuales. Los roles concretos y usuarios finales deben confirmarse con el equipo.

**3. ¿Qué evidencia demuestra que el problema es real, relevante o necesario?**  
El informe identifica como necesidad la supervisión de disponibilidad, CPU, memoria RAM y disco en un entorno de infraestructura con Proxmox y máquinas virtuales Linux. Sin embargo, todavía deben incorporarse evidencias del entorno real, como inventario, mediciones iniciales, incidentes observados o resultados de pruebas.

**4. ¿Qué consecuencias tiene actualmente ese problema?**  
Si no se supervisa adecuadamente la infraestructura, pueden pasar inadvertidas interrupciones, saturación de CPU o memoria y falta de espacio en disco. El impacto concreto en este entorno aún debe documentarse; no se dispone de registros de incidentes en el informe.

**5. ¿Qué valor concreto aportará su solución al usuario?**  
Centralizar la observación del estado de los dispositivos y servicios supervisados, facilitar la detección de condiciones anómalas y mostrar indicadores que ayuden al equipo a diagnosticar problemas.

**6. ¿Por qué la solución es adecuada y no simplemente una aplicación interesante?**  
Porque se orienta a una necesidad operativa definida: conocer la disponibilidad y el uso de recursos de la infraestructura. PRTG se propone como herramienta principal para recoger y visualizar información mediante sensores; su adecuación definitiva debe comprobarse con una prueba en el entorno real.

## 2. Objetivos y éxito

**7. ¿El objetivo general describe un resultado concreto y comprobable?**  
Propuesta de objetivo general: implementar y validar una solución de monitoreo basada en PRTG que permita observar la disponibilidad y los indicadores de CPU, RAM y disco de los dispositivos incluidos en el alcance. Se comprobará mediante pruebas documentadas. El objetivo debe ser aprobado por el equipo.

**8. ¿Los objetivos específicos permiten dividir y comprobar el avance?**  
Sí, como propuesta: identificar los dispositivos; preparar el entorno de monitoreo; configurar los sensores necesarios; establecer umbrales o alertas cuando corresponda; comprobar la recopilación y visualización de datos; ejecutar pruebas; y documentar resultados y limitaciones.

**9. ¿Existe relación entre problema, objetivos, solución y resultados esperados?**  
La relación propuesta es: necesidad de conocer el estado de la infraestructura → objetivo de supervisar disponibilidad y recursos → configuración de PRTG y sensores → paneles, datos y pruebas que demuestren el monitoreo. La trazabilidad debe reflejarse en los requisitos y los casos de prueba del repositorio.

**10. ¿Cómo sabrán al final que tuvieron éxito?**  
Cuando los dispositivos incluidos estén identificados en PRTG, los sensores seleccionados recopilen datos válidos, la disponibilidad pueda verificarse, las alertas definidas se prueben y exista evidencia reproducible de las pruebas. Los criterios definitivos y los umbrales deben acordarse antes de la validación.

## 3. Usuarios y requisitos

**11. ¿Los usuarios y sus necesidades están suficientemente definidos?**  
Parcialmente. Se identifica como usuario principal al responsable de supervisar la infraestructura TI. Falta precisar perfiles, permisos, necesidades de consulta y quién administrará la herramienta.

**12. ¿Las funcionalidades principales se relacionan con necesidades reales?**  
Sí, en la propuesta: supervisar disponibilidad, CPU, RAM y disco responde a la necesidad de conocer el estado y la utilización de los recursos. Las funcionalidades deberán ajustarse a las capacidades de sensores disponibles y a las condiciones del entorno.

**13. ¿Las funcionalidades están descritas para que otro integrante pueda desarrollarlas sin adivinar?**  
Parcialmente. El informe establece el alcance funcional general y requisitos iniciales, pero se deben completar el inventario de dispositivos, sensores exactos, parámetros, umbrales, responsables y procedimiento de configuración.

**14. ¿Cada funcionalidad tiene criterios de aceptación verificables?**  
Se proponen criterios verificables: el dispositivo queda registrado; los sensores seleccionados muestran datos; una prueba de disponibilidad produce el estado esperado; una condición de alerta configurada genera la notificación prevista; y cada prueba conserva evidencia. Los valores y resultados concretos están pendientes de definir y ejecutar.

**15. ¿Existen requisitos de calidad además de las funcionalidades?**  
La propuesta contempla seguridad, rendimiento, disponibilidad, facilidad de uso y compatibilidad cuando sean relevantes. Deben convertirse en criterios medibles, por ejemplo acceso autenticado, permisos mínimos, acceso de red controlado y revisión de la carga de monitoreo.

## 4. Alcance

**16. ¿Está definido qué desarrollará el equipo?**  
El trabajo propuesto consiste en preparar y validar un monitoreo con PRTG para el entorno considerado, registrar dispositivos y sensores, visualizar disponibilidad y métricas de CPU, RAM y disco, comprobar alertas si se incluyen, realizar pruebas y documentar la configuración y resultados.

**17. ¿Está definido qué NO desarrollará?**  
Como límite inicial, no se propone construir desde cero una plataforma de monitoreo que sustituya las funciones propias de PRTG. La automatización avanzada, integraciones adicionales, monitoreo de servicios no identificados y funciones no necesarias para el MVP quedan fuera hasta que el equipo las apruebe expresamente.

**18. ¿Han identificado funcionalidades interesantes pero innecesarias?**  
Sí, pueden aplazarse integraciones avanzadas, automatizaciones complejas y ampliaciones a dispositivos o servicios que no sean indispensables para demostrar el monitoreo básico. La lista final debe aprobarse por el equipo.

**19. ¿El alcance es realista para el tiempo, conocimientos y recursos disponibles?**  
Parece abordable si se limita a un conjunto definido de dispositivos y a las métricas principales. La viabilidad depende de disponer de acceso al entorno, recursos para instalar o utilizar PRTG, conectividad y tiempo para configurar y probar. Estos puntos aún deben confirmarse.

**20. Si redujeran el proyecto un 40 %, ¿qué conservarían y qué eliminarían?**  
Conservaría la instalación o preparación mínima de PRTG, un dispositivo o conjunto pequeño representativo, comprobación de disponibilidad, métricas esenciales de CPU/RAM/disco y pruebas documentadas. Aplazaría integraciones, automatizaciones y ampliaciones no esenciales.

## 5. MVP

**21. ¿Existe una primera versión funcional claramente definida?**  
Se propone un MVP que supervise un conjunto acotado de dispositivos y muestre disponibilidad y las métricas principales mediante sensores de PRTG. Todavía debe fijarse el inventario exacto y confirmarse que el entorno permite obtener esas métricas.

**22. ¿El MVP resuelve una parte real del problema?**  
Sí, si permite al equipo observar de forma centralizada el estado de los dispositivos incluidos y detectar una pérdida de disponibilidad o una utilización anómala de recursos. Esto debe demostrarse con pruebas, no asumirse antes de implementarlo.

**23. ¿Puede terminarse dentro del tiempo disponible?**  
No puede asegurarse con la información actual. Se debe contrastar el MVP con el Gantt, los recursos disponibles, el acceso a la infraestructura y la complejidad de configuración de los sensores.

**24. ¿Las funcionalidades posteriores están separadas del MVP?**  
Como propuesta, el MVP incluye disponibilidad, CPU, RAM, disco y validación básica. Las integraciones adicionales, reportes avanzados, automatizaciones y ampliación a más dispositivos se consideran posteriores hasta que el equipo acuerde otra cosa.

## 6. Diseño y viabilidad técnica

**25. ¿La solución es técnicamente viable con las tecnologías y recursos del equipo?**  
En principio, el informe propone PRTG Network Monitor para supervisar un entorno con Proxmox y máquinas virtuales Linux. La viabilidad no está demostrada todavía: deben comprobarse los requisitos de instalación, licenciamiento o límites de uso aplicables, conectividad, permisos y compatibilidad de cada sensor.

**26. ¿Han identificado las partes técnicamente más difíciles o inciertas?**  
Sí: conseguir acceso seguro a los dispositivos; determinar qué sensores sirven para cada equipo o sistema operativo; habilitar los protocolos y permisos necesarios; validar la recolección de CPU, RAM y disco; y configurar alertas sin generar falsos positivos.

**27. ¿Han validado o previsto validar las tecnologías e integraciones críticas?**  
La validación está prevista, pero aún no consta como realizada. Se debe ejecutar una prueba piloto con uno o pocos dispositivos y registrar la configuración, los datos obtenidos, los errores y las limitaciones.

**28. ¿Las decisiones tecnológicas están justificadas por las necesidades?**  
La elección de PRTG se justifica en el informe por su enfoque de monitoreo basado en dispositivos y sensores y por la necesidad de observar disponibilidad y recursos. La decisión final debe apoyarse en la prueba piloto y en la revisión de requisitos, recursos y condiciones de uso.

**29. ¿Han identificado dependencias externas?**  
Las dependencias previsibles son el entorno Proxmox/Linux que se supervisará, conectividad entre el sistema de monitoreo y los equipos, credenciales y permisos apropiados, recursos para ejecutar PRTG y acceso a su documentación. La disponibilidad concreta de cada dependencia debe verificarse.

**30. ¿Existe una estructura técnica inicial clara?**  
La estructura inicial propuesta es: entorno de infraestructura → dispositivos supervisados → sensores de PRTG → datos y estados de monitoreo → paneles, alertas y evidencias de prueba → documentación en el repositorio. Los detalles de red y configuración deben documentarse cuando se implementen.

## 7. Datos, seguridad y calidad

**31. ¿Qué información manejará el sistema y de dónde provendrá?**  
Se espera manejar estados de disponibilidad y métricas de uso de CPU, memoria RAM y disco procedentes de los dispositivos supervisados mediante los sensores configurados. El inventario exacto y la frecuencia de recopilación deben definirse.

**32. ¿Han identificado restricciones de datos, privacidad, seguridad, permisos o acceso?**  
Deben protegerse las credenciales, limitar el acceso a la consola de monitoreo, utilizar permisos mínimos y restringir la conectividad a lo necesario. No se deben incluir contraseñas, tokens ni datos sensibles en GitHub. Las reglas concretas de acceso y red siguen pendientes de validación.

**33. ¿Han definido cómo comprobarán que las funcionalidades funcionan?**  
Se propone verificar la presencia de los dispositivos, la lectura de los sensores, la coherencia de los valores, la detección de una pérdida controlada de disponibilidad y el comportamiento de las alertas configuradas. Cada resultado debe compararse con el criterio esperado y registrarse como evidencia.

**34. ¿Existe una estrategia inicial de pruebas?**  
Sí, como propuesta: prueba de conectividad; prueba de detección del dispositivo; prueba de recopilación de CPU, RAM y disco; prueba de disponibilidad; prueba de alertas; y revisión de permisos y acceso. Deben registrarse fecha, entorno, pasos, resultado y evidencia. Las pruebas todavía deben ejecutarse.

## 8. Plan de desarrollo

**35. ¿El Gantt contiene tareas concretas?**  
El proyecto cuenta con un Gantt mencionado entre sus materiales, pero no se ha confirmado aquí si sus tareas actuales incluyen todos los pasos específicos de PRTG. Se recomienda comprobarlo y añadir instalación/preparación, inventario, sensores, alertas, pruebas, correcciones y documentación.

**36. ¿Cada tarea tiene responsable?**  
No consta en el informe de PRTG. El equipo debe asignar un responsable verificable a cada tarea en el Gantt o en GitHub Projects.

**37. ¿Las tareas tienen estimaciones razonables?**  
No se dispone de estimaciones confirmadas en el informe. Deben estimarse tras revisar disponibilidad de recursos y complejidad de la prueba piloto.

**38. ¿Las dependencias entre tareas están identificadas?**  
Deben quedar explícitas. Por ejemplo, configurar sensores depende de contar con acceso y conectividad; probar alertas depende de tener sensores operativos; cerrar la documentación depende de registrar los resultados de las pruebas.

**39. ¿El Gantt contempla desarrollo, integración, pruebas, correcciones y documentación?**  
Debe verificarse en el Gantt actual. La planificación actualizada debería contemplar preparación de PRTG, integración con dispositivos, validación, corrección de problemas y documentación final.

**40. ¿Qué tareas podrían bloquear al resto del equipo?**  
La falta de acceso a la infraestructura, permisos insuficientes, incompatibilidad o falta de datos de los sensores y ausencia de recursos para ejecutar PRTG. Conviene resolver estos puntos al principio mediante una prueba piloto.

## 9. Equipo y riesgos

**41. ¿Cada integrante tiene una responsabilidad concreta y verificable?**  
Tomando como referencia los roles que ya figuran en el README y en los archivos de integrantes del repositorio, se propone distribuir el trabajo de la siguiente manera. Es una asignación inicial basada en los roles existentes y debe ser revisada y aceptada por el equipo:

- **Gabriel Zerpa — Product Owner:** definir y priorizar los requisitos del monitoreo; coordinar la confirmación del alcance del MVP; mantener claros los criterios de aceptación para disponibilidad, CPU, RAM y disco; y validar con el equipo que las entregas respondan a las necesidades del proyecto.
- **Leonardo Sebastian Garcia Mendoza — Developer:** liderar la preparación técnica de PRTG; documentar y realizar, una vez autorizado el entorno, la configuración de dispositivos y sensores; revisar los datos y consultas disponibles; y registrar configuraciones y resultados técnicos sin incluir credenciales.
- **Alvaro Santiago Beltran Menini — Scrum Master:** coordinar el seguimiento del Gantt y GitHub Projects; organizar Issues, dependencias y bloqueos; facilitar la revisión periódica del avance; y verificar que las tareas tengan responsables, evidencias y estado actualizado.

**Trabajo compartido:** las pruebas de aceptación, revisión de resultados, documentación final y decisiones sobre cambios de alcance deben revisarse entre los integrantes. Estas responsabilidades son una propuesta derivada de los roles registrados, no evidencia de que ya hayan sido formalmente aprobadas.

**42. ¿Existe un mecanismo acordado para revisar e integrar el trabajo?**  
Se propone usar GitHub como centro de coordinación: Gabriel prioriza los requisitos y confirma los criterios de aceptación; Leonardo documenta los cambios técnicos y las pruebas de configuración; y Alvaro mantiene el seguimiento de tareas, fechas, dependencias y bloqueos. Cada actividad debe registrarse como Issue con responsable, resultado esperado y evidencia de cierre. GitHub Projects puede mostrar el estado y el Gantt debe actualizarse según el avance real. Los cambios importantes en documentación o configuración deben revisarse por otro integrante antes de integrarse. Este mecanismo se propone para organizar el trabajo; el equipo todavía debe confirmar que lo adopta.

**43. ¿Cuáles son los tres riesgos principales?**  
1. PRTG o los sensores no pueden obtener las métricas requeridas en el entorno disponible.  
2. Faltan acceso, permisos o conectividad entre PRTG y los dispositivos.  
3. La configuración, las pruebas o las correcciones consumen más tiempo del previsto.

**44. ¿Qué mitigación corresponde a cada riesgo?**  
1. Ejecutar una prueba piloto temprana y validar cada métrica antes de ampliar el alcance.  
2. Revisar conectividad, permisos y reglas de red con anticipación, aplicando privilegios mínimos.  
3. Priorizar el MVP, asignar responsables y estimaciones, registrar bloqueos en Issues y reservar tiempo para pruebas y correcciones.

**45. ¿Qué harían si una persona clave deja de estar disponible?**  
Mantener instrucciones y decisiones en el repositorio, registrar la configuración sin secretos, documentar el estado de cada tarea y asignar un suplente. Cada actividad crítica debería tener suficiente documentación para que otro integrante pueda continuarla.

## 10. Preparación para desarrollar

**46. ¿Hay alguna decisión fundamental pendiente que pueda bloquear el inicio?**  
Sí: confirmar el alcance exacto del MVP, los dispositivos que se supervisarán, la disponibilidad del entorno y los recursos necesarios para PRTG, los sensores aplicables y los criterios de aceptación.

**47. ¿Existe algún requisito importante que todavía no comprendan suficientemente?**  
Deben precisarse los sensores disponibles para cada sistema, el método de acceso a los dispositivos, los umbrales de alerta, la frecuencia de consulta, los permisos necesarios y las limitaciones de la versión o modalidad de PRTG que se utilice.

**48. ¿Falta alguna dependencia, información, permiso, herramienta o recurso?**  
No puede afirmarse que falte un recurso específico sin verificarlo. Es necesario comprobar acceso al entorno Proxmox/Linux, conectividad, credenciales autorizadas, equipo donde ejecutar PRTG y condiciones de uso aplicables. Los faltantes deben registrarse antes de depender de ellos.

**49. Si mañana comenzaran a programar, ¿cada integrante sabría qué construir primero?**  
Con la distribución inicial propuesta, el primer trabajo sería coordinado: Gabriel definiría y priorizaría el alcance del piloto y sus criterios de aceptación; Leonardo realizaría la validación técnica de PRTG con un dispositivo autorizado, comprobando conectividad y sensores compatibles; y Alvaro registraría la tarea, las dependencias, los bloqueos y las fechas en GitHub Projects/Gantt. Los integrantes revisarían juntos los resultados antes de ampliar el monitoreo. Esta secuencia es una propuesta de trabajo, no una confirmación de que el piloto ya se haya ejecutado.

**50. ¿Un nuevo integrante comprendería el problema, el MVP y el siguiente trabajo solo con el repositorio?**  
El informe de PRTG explica la orientación técnica, las métricas y las pruebas propuestas. Para que la incorporación sea completa, el repositorio debe mantener también el problema, los objetivos aprobados, el MVP definitivo, el inventario, las decisiones, el Gantt actualizado, las Issues y las evidencias de ejecución.

## 11. Prueba de fracaso

**51. ¿Qué tendría que ser cierto para que el proyecto fracasara?**  
Que no se logre recoger información válida de los dispositivos; que no haya permisos o conectividad; que el alcance exceda el tiempo disponible; que no se realicen pruebas; o que la configuración y los resultados no se documenten y no puedan reproducirse.

**52. ¿Existe una estrategia para evitar o controlar esas condiciones?**  
Se propone validar PRTG temprano con una prueba piloto, reducir el alcance al MVP, confirmar permisos y conectividad, asignar responsables y fechas, ejecutar pruebas con criterios verificables y mantener evidencias y decisiones en GitHub. La estrategia debe revisarse periódicamente y su eficacia se comprobará durante la implementación.

## Conclusión

La propuesta de monitoreo con PRTG está definida a nivel inicial: se pretende supervisar disponibilidad, CPU, RAM y disco en un entorno Proxmox/Linux, y validar la configuración mediante pruebas documentadas. No obstante, la documentación disponible no demuestra que la herramienta esté instalada o funcionando, ni confirma responsables, cronograma detallado, inventario definitivo o resultados de pruebas.

**Próximas acciones recomendadas:**
1. Revisar y aprobar la distribución inicial de responsabilidades propuesta para Gabriel Zerpa (Product Owner), Leonardo Sebastian Garcia Mendoza (Developer) y Alvaro Santiago Beltran Menini (Scrum Master).
2. Aprobar el alcance y los criterios de aceptación del MVP.
3. Confirmar recursos, acceso, conectividad y condiciones de uso de PRTG.
4. Realizar una prueba piloto y guardar evidencias sin incluir credenciales.
5. Actualizar Gantt/GitHub Projects con tareas, responsables, estimaciones y dependencias.
6. Actualizar este cuestionario con resultados reales cuando se complete cada validación.

## Referencias

- Informe del proyecto: [Informe técnico actualizado: monitoreo de infraestructura con PRTG](./informe_prtg.md).
- PRTG Network Monitor: https://www.paessler.com/prtg
- Manual oficial de PRTG: https://www.paessler.com/manuals/prtg
- Documentación de sensores: https://www.paessler.com/manuals/prtg/sensors
- Cuestionario original de aprobación del proyecto: *Cuestionario_Aprobacion_Proyecto_SO.pdf*.
