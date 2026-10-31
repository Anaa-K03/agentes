# Consultas y nivel de verificación

Se contrastaron los esquemas y operadores con fuentes oficiales accesibles, sin ejecutar consultas contra Azure ni Grail. “Revisada documentalmente” no significa validada en el tenant ni resultado real del reto. No se dispone de credenciales, tablas ni datos del evento. Usar la [ficha de validación](../templates/query-validation.md) cuando se obtenga acceso.

| Archivo | Ámbito | Precondiciones |
|---|---|---|
| [Application Insights](../queries/kql/application-insights.kql) K1–K5 | Logs desde recurso App Insights, tablas minúsculas | requests/exceptions/traces/dependencies disponibles; operation_Id observado |
| [Log Analytics](../queries/kql/log-analytics.kql) W1–W5 | Workspace, tablas App* | Acceso al ámbito propio y columnas TimeGenerated/OperationId; no otros equipos |
| [DQL logs](../queries/dql/logs.dql) D1–D4 | Logs/Notebooks de Dynatrace Grail | D1 descubre atributos; D2 loglevel; D3 Kubernetes; D4 trace.id ingerido |

Ejecutar **un bloque por vez**. Reemplazar REEMPLAZAR_* solo por valor observado. No hacer consultas amplias sobre recursos de otros equipos. Filtrar recurso/rol de la propia aplicación si el ámbito reúne varias apps. Si una tabla falta, comprobar esquema e instrumentación; no usar una unión tolerante a errores para ocultar la ausencia de fuentes.

## Diferencias que provocan errores frecuentes

| App Insights | Workspace | Significado |
|---|---|---|
| requests | AppRequests | Solicitudes |
| exceptions | AppExceptions | Excepciones |
| traces | AppTraces | Logs de aplicación, no spans de trazado |
| dependencies | AppDependencies | Llamadas a dependencias |
| timestamp | TimeGenerated | Tiempo del registro |
| operation_Id | OperationId | Correlación distribuida |
| duration | DurationMs | Duración en ms |
| type / outerMessage | ExceptionType / OuterMessage | Tipo/mensaje externo |

Fuentes: [modelo de telemetría](https://learn.microsoft.com/en-us/azure/azure-monitor/app/data-model-complete), [AppRequests](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/apprequests), [AppExceptions](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/appexceptions), [KQL union](https://learn.microsoft.com/en-us/kusto/query/union-operator). También se contrastaron [AppTraces](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/apptraces) y [AppDependencies](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/appdependencies); confirmar esquema efectivo en portal antes de ejecutar W3/W4.

K1/K2 son versiones de Charla 2 p. 13; K3/K4 añaden límite/ID y nombre de unidad; K5 usa withsource para identificar tabla sin depender de itemType. Una unión puede producir columnas adicionales si tipos difieren: inspeccionar esquema real. Las consultas cuentan registros observados: no usar count como volumen total de solicitudes si hay muestreo. Comprobar ItemCount/itemCount y política cuando la pregunta requiera volumen real. P95 representa los datos recibidos, sin garantía de distribución completa.

En DQL, [fetch/data](https://docs.dynatrace.com/docs/platform/grail/dynatrace-query-language/commands/data-source-commands) y [summarize/by](https://docs.dynatrace.com/docs/platform/grail/dynatrace-query-language/commands/aggregation-commands) fueron revisados. Namespace/pod/trace.id son atributos condicionales, no columnas universales garantizadas. Cero filas puede significar filtro, tiempo, permisos, retención o ausencia de ingestión. No prueba salud ni ausencia de tráfico.
