# Dynatrace: del impacto a la evidencia

Base: Sesión 1, pp. 3–19; Conceptos, pp. 1–4. Dynatrace no sustituye Application Insights como fuente indicada para el track Microsoft.

1. Confirmar tenant, intervalo y zona horaria, permisos y aplicación/servicio del reto. Para práctica usar Playground; sus datos no son datos de Copa.
2. Abrir incidente/Problems disponible o servicio con síntoma. Medir latencia, tasa de fallo, tráfico y saturación; distinguir un cambio por aumento de carga de uno por caída de dependencia.
3. Seguir Service flow/topología/Smartscape disponible para ubicar salto afectado. Mapas muestran relaciones observadas, no garantizan por sí solos causalidad.
4. Abrir una traza/PurePath dentro del intervalo afectado. Conservar trace ID, servicio, operación y duración de la dependencia; comprobar si el tramo lento pertenece a red, espera, consulta o ejecución propia.
5. En Logs/Notebooks usar `fetch logs` primero con ventana acotada; inspeccionar campos y después filtrar por entidad real/namespace/trace ID si están presentes. No pegar IDs o nombres de pods del ejemplo como si fueran reales.
6. Correlacionar con P1/P2/P3: infraestructura → llamada → contrato/experiencia; comparar antes/después con condiciones comparables. Preparar cambios solo si el reto lo autoriza.

Consultas en `queries/dql/` usan [fetch](https://docs.dynatrace.com/docs/platform/grail/dynatrace-query-language/commands/data-source-commands) y [summarize](https://docs.dynatrace.com/docs/platform/grail/dynatrace-query-language/commands/aggregation-commands). No se ejecutaron en Grail. Si no hay un campo, inspeccionar registros y permisos; no confundir resultado vacío con ausencia de problema.

Guía Estudiante: el participante crea cuenta en Playground y usa esa cuenta en University → Essentials; la guía describe 9 lecciones, ~4 h 30 min. No introducir credenciales en el repo, no aceptar términos por otros integrantes. Verificar la interfaz real al registrarse.

RUM, Application Security, LiveDebugger y Business Events son capacidades de preparación, no herramientas garantizadas. Verificar instrumentación/cobertura y permisos. No instalar agentes ni activar captura de variables de producción sin autorización y revisión de datos sensibles.
