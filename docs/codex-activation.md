# Activación y ahorro de créditos

Estas skills son archivos de instrucciones, no servicios en ejecución ni agentes persistentes creados en la cuenta. No hay sincronización entre chats. Un asistente funciona cuando una persona inicia una sesión, proporciona acceso permitido al proyecto e invoca su rol.

## En cada laptop

1. Extraer el ZIP de entrega, o clonar el repositorio cuando exista. Abrir la carpeta `copa-2026-agent-kit` como proyecto local en Codex.
2. Iniciar un chat en esa carpeta. Codex descubre las cuatro skills en `.agents/skills/`; si no aparecen, reiniciar la sesión y comprobar que la carpeta está dentro de la raíz Git/proyecto. La [documentación oficial](https://learn.chatgpt.com/docs/build-skills) describe ese descubrimiento.
3. Pegar el mensaje de su fila. Cada participante usa su propia sesión/cuenta autorizada; no compartir credenciales.

| Persona | Mensaje inicial para copiar |
|---|---|
| P1 | `Usa $copa-azure-sre. Lee agents/01-azure-sre.md. Soy P1. Empieza por inspección; prepara cambios Azure para mi aprobación. No uses Azure CLI. Te entregaré RG y evidencia permitida.` |
| P2 | `Usa $copa-backend-dotnet. Lee agents/02-backend-dotnet.md. Soy P2. Analiza el backend existente y el error activo. Propón un diff mínimo y una prueba dirigida; no despliegues.` |
| P3 | `Usa $copa-frontend-react. Lee agents/03-frontend-react.md. Soy P3. Analiza la petición de Network y el frontend existente. Contrasta URL y contrato con evidencia; no despliegues.` |
| P4 | `Usa $copa-incident-commander. Lee agents/04-incident-commander.md. Soy P4. Mantén el error activo, dueños y bitácora. Prepara respuestas CTFd con fuente; no las envíes.` |

4. Añadir al siguiente mensaje: reto/entorno, síntoma reproducido, hora, evidencia depurada, ruta absoluta al repo oficial autorizado y commit. Permitir acceso local solo a lo necesario. Si Codex no puede leer la carpeta externa, abrir el repo oficial como proyecto y proporcionar el kit por ruta/adjunto, o copiar la skill con sus referencias manteniendo estructura y sin sobrescribir instrucciones oficiales.
5. En otros asistentes sin soporte de skills, cargar `AGENTS.md`, las reglas y la definición de rol, indicando que actúe según esos archivos. Esto da un rol por conversación; no crea un “system message” privilegiado si el producto no admite esa configuración. En plataformas que sí lo admiten, usar la definición y límites compartidos como instrucciones del agente.

## Trabajo aislado

Cada laptop con clon propio evita que cuatro sesiones editen la misma carpeta. Si una persona usa varios chats en una laptop, usar worktrees o copias separadas. En Codex, elegir Worktree, rama base y después crear rama antes de publicar cambios. Ver [worktrees oficiales](https://learn.chatgpt.com/docs/environments/git-worktrees).

## Ahorro

- Cargar solo rol, procedimiento y fragmento de evidencia pertinente; no los 92 folios cada turno.
- Una pregunta concreta por experimento: “¿qué diferencia explica este 500?”, con log y archivo exactos.
- Reusar bitácora y consultas; evitar repetir investigación o búsquedas que ya tienen respuesta vigente.
- Solicitar respuestas breves y máximo tres hipótesis. Escalar a razonamiento más profundo solo si la evidencia es contradictoria.
- No activar cuatro agentes para una tarea individual ni investigaciones recursivas. Los cuatro trabajan cuando cada integrante tiene una pregunta distinta.
- No se garantizan ahorros porcentuales ni se dispone de medición de créditos de esta entrega. No se cambió modelo, facturación ni configuración de cuenta.
