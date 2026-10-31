# Copa 2026 — Kit de cuatro asistentes

Preparación para diagnosticar aplicaciones existentes, no construir una aplicación nueva.
Revisión: 30 de octubre de 2026, hora de Panamá. Kit independiente; no es material oficial ni contiene soluciones E1–E6.

## Empezar en cinco minutos

1. Leer [reglas y dudas](knowledge/rules.md) y [primeros 30 minutos](docs/first-30-minutes.md).
2. Asignar un integrante a cada [rol](docs/team-operation.md).
3. Abrir una copia local del kit en Codex; iniciar un chat propio e invocar la skill de su rol. Copiar el mensaje de [activación](docs/codex-activation.md).
4. Usar los repositorios oficiales únicamente cuando los entregue la organización. Registrar URL y commit, sin copiar secretos al kit.
5. Trabajar sobre la evidencia actual del error desbloqueado; un cambio, una validación, una respuesta humana.

| Integrante | Asistente | Skill | Foco |
|---|---|---|---|
| P1 | Azure SRE | `$copa-azure-sre` | Portal Azure, IaC entregada, despliegues, KQL |
| P2 | Backend Detective | `$copa-backend-dotnet` | C#, configuración, excepciones, contrato API |
| P3 | Frontend Detective | `$copa-frontend-react` | React, Network, URL, CORS, integración |
| P4 | Incident Commander | `$copa-incident-commander` | Secuencia, bitácora, validación, borradores CTFd; Dynatrace |

Son cuatro definiciones y cuatro skills reutilizables. No se han creado procesos autónomos, cuentas ni chats persistentes; los archivos por sí solos no ejecutan agentes. Cada participante inicia su propia sesión. Las sesiones no se sincronizan automáticamente.

## Contenido

- [Activación exacta y ahorro de créditos](docs/codex-activation.md).
- [Operación simultánea, ramas y acceso a Azure](docs/team-operation.md).
- [Plan de preparación y ejercicios](docs/preparation.md).
- [Azure](docs/azure.md), [Dynatrace](docs/dynatrace.md), [diagnóstico por síntoma](docs/troubleshooting.md).
- [Consultas KQL/DQL y nivel de verificación](docs/queries.md), archivos en `queries/`.
- [Resumen de los seis PDF](knowledge/workshops.md), [fuentes](knowledge/source-map.md), [reglas](knowledge/rules.md).
- [Incorporar repos oficiales](docs/update-knowledge.md), [publicación y visibilidad](docs/github-private.md).
- Plantillas en `templates/`; definiciones en `agents/`; skills descubribles en `.agents/skills/`.
- [Verificación y pendientes](VERIFICATION.md), [cambios respecto al ZIP](provenance/changes.md).

No se incluyen los PDF, sus transcripciones completas, grabaciones ni datos de la competición. El contenido Markdown del ZIP original se conserva como archivo histórico en `provenance/original-kit.zip`; no se debe activar su prompt antiguo.

## Estado y destino de publicación

Repositorio elegido por la usuaria: [Anaa-K03/agentes](https://github.com/Anaa-K03/agentes). Su visibilidad **pública** fue autorizada expresamente en este chat, sustituyendo la preferencia inicial de un repositorio privado llamado copa-2026-agent-kit. El kit conserva su nombre descriptivo, sin renombrar el repositorio.

Preparado y verificado localmente. La subida al repositorio autorizado se intentó, pero GitHub devolvió 403 Resource not accessible by integration; no se publicó ningún archivo. Falta habilitar acceso de la integración para este repositorio en la cuenta propietaria. Consultas contrastadas con documentación, sin ejecución en Azure/Grail. No se realizaron despliegues ni envíos CTFd. Consulte `VERIFICATION.md` para el alcance preciso.
