# Azure: procedimiento de observación

Usar portal según Copa.pdf p. 7. No se requiere Azure CLI para esta guía. No se probó ningún acceso cloud.

1. En el portal confirmar directorio, suscripción asignada y RG exacto. Revisar rol disponible sin cambiarlo. Si falta invitación o acceso, escalar al mentor; no crear recursos en suscripción personal.
2. Abrir App Service → Overview para estado/URL/runtime. Revisar Deployment Center/logs de publicación y Activity Log en intervalo del fallo. Separar fallo de despliegue de error de aplicación ya publicada.
3. Ante 500: Application Insights vinculado → Failures → request → detalles end-to-end. Anotar UTC, nombre, resultCode, rol y operation_Id; stack y dependencia relevante depurados. No identificar automáticamente x-ms-request-id con operation_Id.
4. En Logs, confirmar tablas `requests` o `AppRequests`. Aplicar consultas del esquema correcto. Para configuración, comparar solo nombres/presencia en App Service → Environment variables/Configuration con código e IaC, sin copiar valores secretos.
5. Si falta telemetría: confirmar recurso y ventana, instrumentation/connection string sin exponerla, arranque y retraso de ingestión. Contrastar Log stream/Live Metrics cuando estén habilitados. No habilitar instrumentación automáticamente: es un cambio cloud que requiere aprobación.
6. Medir el flujo real y endpoint de salud si existe. Una app Running o un HTTP 200 de liveness no certifican disponibilidad funcional.

Según [App Service](https://learn.microsoft.com/en-us/azure/app-service/configure-common), sus settings llegan como variables de entorno y su modificación puede reiniciar la app. Planificar impacto y preservar la fuente autorizada para evitar que un redeploy sobrescriba un arreglo manual.

En [.NET](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/configuration/?view=aspnetcore-10.0), los proveedores determinan precedencia y `__` puede representar `:` en variables de entorno. Verificar cómo el proyecto construye su configuración antes de recomendar una clave. No revelar connection strings.

## Terraform suministrado

Leer README, versiones requeridas, provider lock, variables, backend de estado y destinos antes de ejecutar. No generar infraestructura del reto desde cero. `terraform fmt -check` revisa formato; `terraform validate` requiere directorio preparado y valida consistencia, no permisos/cuotas ni funcionamiento real ([referencia](https://developer.hashicorp.com/terraform/cli/commands/validate)). En una copia de preparación, `terraform init -backend=false` puede descargar providers y módulos: revisar origen y scripts antes; no es un despliegue ni aprobación para conectarse al backend remoto.

`plan` consulta infraestructura y puede contener secretos; seguir el procedimiento cloud oficial y autorización requerida. Nunca guardar estado, plan ni tfvars privados en Git. Antes de apply/despliegue, P1 muestra acción exacta, RG, diff/plan, cambios de reemplazo/destrucción, prueba y reversión. Si el resultado requiere borrar/recrear, pedir aprobación específica. No forzar unlock, importar estado o ejecutar destroy como troubleshooting rutinario.

Reversión: preparar último commit/artefacto conocido y valores previos guardados de forma segura por el operador. Revertir solo el cambio propio aprobado, sin pisar trabajo paralelo; también la reversión cloud requiere autorización conforme al alcance acordado. No asumir slots o backups si no existen.
