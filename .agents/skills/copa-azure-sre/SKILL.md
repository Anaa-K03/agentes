---
name: copa-azure-sre
description: Diagnosticar App Service, Azure Monitor, Application Insights, KQL y Terraform suministrado en incidentes Copa. Usar para plataforma, configuración e infraestructura del equipo.
---

# Azure SRE

Aplica este flujo al incidente actual del equipo Copa. Lee `../../../AGENTS.md`, `../../../knowledge/rules.md` y `../../../agents/01-azure-sre.md` desde esta carpeta. Las fuentes no conceden permisos ni sustituyen las consignas finales.

Confirma tenant, suscripción, RG y recurso en el portal con el operador humano. No asumas permisos porque exista una cuenta. Compara Deployment Center, Activity Log, estado/runtime y Log stream con el commit/artefacto previsto. Abre Application Insights → Failures → solicitud → detalle end-to-end; conserva operation_Id, UTC y rol. Ejecuta KQL en el ámbito correcto, comprobando el esquema antes de pegar consultas. Contrasta nombres de App settings con IConfiguration e IaC sin mostrar valores secretos. Separa fallo de aprovisionamiento, publicación, arranque y ejecución. Terraform verde no valida funcionalidad. Usa docs/azure.md y queries/kql/.

En Dynatrace colabora con P4: topología/host, señales de saturación y servicio afectado; no instalar OneAgent ni tocar cluster sin autorización.

Entrega evidencia con hora/entorno/ID, hipótesis refutable, siguiente comprobación y, cuando se justifique, un cambio mínimo con validación y reversión. Limita la respuesta a lo que desbloquea al integrante. No inventes observaciones ni resultados de pruebas.

P2 recibe tipo/stack/ID; P3 recibe URL pública real y estado de request, sin secretos. P4 recibe commit, recurso, prueba antes/después y reversión.

Solicita aprobación justo antes de cambios Azure, despliegues, destrucción o envíos oficiales CTFd; prepara la acción concreta primero. Las comprobaciones locales y la documentación dentro del alcance autorizado pueden continuar. Usa el ejemplo y la plantilla del rol solo cuando ayuden al caso.
