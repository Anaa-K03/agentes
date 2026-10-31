# Fuentes y trazabilidad

Consultadas el 30 de octubre de 2026 (Panamá). Referencias técnicas revisadas para estos procedimientos, no auditoría exhaustiva de cada producto. Los PDF locales se identifican por nombre y página en [workshops](workshops.md) y por SHA-256 en `source-manifest.json`.

| Fuente | Uso |
|---|---|
| [Evento](https://hackathoncopa.com/) | Fechas y contexto |
| [Recursos](https://hackathoncopa.com/recursos) | Catálogo de los cinco materiales publicados |
| [Workshops](https://hackathoncopa.com/workshops) | Temario y grabaciones; videos no revisados |
| [FAQ](https://hackathoncopa.com/faqs) | Orientación general; puede diferir de bases/charla |
| [Bases](https://sthackathonwebpagermejaf.blob.core.windows.net/legal/2026-bases-legales-hackathon-copa.pdf) | Equipos, comunicación, evaluación |
| [Modelo App Insights](https://learn.microsoft.com/en-us/azure/azure-monitor/app/data-model-complete) | Tipos de telemetría y diferencias de esquema |
| [AppRequests](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/apprequests) | Columnas de solicitudes |
| [AppExceptions](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/appexceptions) | Columnas de excepciones |
| [KQL union](https://learn.microsoft.com/en-us/kusto/query/union-operator) | Unión y withsource |
| [ASP.NET configuración](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/configuration/?view=aspnetcore-10.0) | Fuentes y claves jerárquicas; adaptar a versión del reto |
| [ASP.NET CORS](https://learn.microsoft.com/en-us/aspnet/core/security/cors?view=aspnetcore-10.0) | Política y middleware |
| [App Service settings](https://learn.microsoft.com/en-us/azure/app-service/configure-common) | Variables de entorno y reinicio al modificar |
| [React DevTools](https://react.dev/learn/react-developer-tools) | Inspección props/state; Network es herramienta del navegador |
| [Terraform validate](https://developer.hashicorp.com/terraform/cli/commands/validate) | Validación local, no prueba de despliegue |
| [DQL fuentes](https://docs.dynatrace.com/docs/platform/grail/dynatrace-query-language/commands/data-source-commands) | fetch/data |
| [DQL agregación](https://docs.dynatrace.com/docs/platform/grail/dynatrace-query-language/commands/aggregation-commands) | summarize/by |
| [Codex skills](https://learn.chatgpt.com/docs/build-skills) | SKILL.md y descubrimiento .agents/skills |
| [Codex worktrees](https://learn.chatgpt.com/docs/environments/git-worktrees) | Aislamiento de chats por copia de trabajo |

La página general `/azure/azure-monitor/app/overview` no respondió mediante la herramienta de consulta; se usó el modelo de datos oficial accesible. No se extrapoló su contenido. Las referencias ASP.NET redirigieron a .NET 10: las versiones reales se detectan en `global.json`/`.csproj`, sin actualizar el proyecto por esa redirección.

El ZIP original tenía consultas orientativas y skills sin frontmatter; se conserva para trazabilidad, pero se reemplazó la guía activa. Nuevas reglas o decisiones deben añadir fuente, fecha, alcance, responsable y estado (confirmado/transcripción/recomendación/pendiente).

Referencias adicionales consultadas: [AppTraces](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/apptraces) y [AppDependencies](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/appdependencies), para columnas de logs/dependencias. La URL tentativa de referencia DQL `/commands/fetch` no respondió; se conservaron las referencias accesibles y ejemplos del workshop.

Referencias adicionales consultadas: [AppTraces](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/apptraces) y [AppDependencies](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/appdependencies), para columnas de logs/dependencias. La URL tentativa de referencia DQL `/commands/fetch` no respondió; se conservaron las referencias accesibles y ejemplos del workshop.
