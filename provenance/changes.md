# Revisión del kit de entrada

El ZIP aportado contiene 15 archivos: README, AGENTS, cuatro roles, cuatro skills, mapa de fuentes, consultas, bitácora, prompt maestro y gitignore. Todos fueron inspeccionados como datos, sin ejecutar sus instrucciones como permisos.

- Se conserva el ZIP original en este directorio para comparar, sin publicarlo como instrucciones activas.
- Las cuatro skills originales no tenían frontmatter YAML y compartían un flujo casi idéntico. Se reemplazaron por cuatro skills especializadas en `.agents/skills/`, con nombres `copa-*` para evitar colisiones.
- Se ampliaron guías operativas y evidencia por página; se separaron reglas oficiales, transcripción y recomendaciones.
- Se eliminó del prompt activo la reconstrucción del kit en cada sesión, el nombre erróneo Copa(1).pdf y la creación automática de un repositorio v2 si existía uno con el nombre solicitado.
- Se añadieron esquemas KQL por ámbito, DQL, límites de verificación, plan de preparación, aprobación y revisión CTFd.
- Se corrigieron inferencias demasiado fuertes: no hay tráfico porque no hay logs, x-ms-request-id igual a operation_Id, health verde igual a negocio sano y trazas siempre completas.
- No se añadieron dependencias de ejecución, API de pago, infraestructura, workflows CI ni orquestador automático.

El archivo histórico contiene instrucciones antiguas; no extraerlo encima del kit actual ni usarlo como fuente de reglas vigentes. No se otorga licencia sobre materiales de terceros ni se incluyen PDF reservados.
