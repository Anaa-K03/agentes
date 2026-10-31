# Conocimiento extraído de los materiales

Se leyeron los seis PDF completos mediante extracción de todas sus páginas: 92 páginas en total. Se revisaron visualmente las 18 páginas de Cápsulas para recuperar ejemplos representados como imágenes. La numeración siguiente es la página física del PDF; algunas diapositivas imprimen otra numeración. No se reproducen documentos íntegros.

| Documento | Páginas | Aporte útil y límites |
|---|---:|---|
| Charla 2 — Operación Bajo Presión | 25 | pp. 5–7 evidencia y capas; 9–13 telemetría/correlación/KQL; 15–20 500, URL, contrato, CORS y cascada; 22–24 seis pasos, ejemplo y bitácora. Escenarios ilustrativos, no causas reales E1–E6. |
| Copa | 10 | pp. 1–4 entorno/accesos; 5 formato de respuestas; 7 secuencia/repos/portal; 8–10 CTFd, dispositivos, IA y comunicaciones. Transcripción automática incompleta; no tratar sus frases ambiguas como especificación final. |
| Cápsulas Informativas — Microsoft | 18 | 17 conceptos en orden: Azure, RG, App Service, API, frontend/backend, DevOps, IaC, Terraform, observabilidad, logs, KQL, App Insights, excepciones/500, CORS, health, configuración y pensamiento diagnóstico. pp. 9–11 ejemplos KQL ilustrados. |
| Sesión 1 — Observabilidad Inteligente con Dynatrace | 21 | pp. 3–5 señales/Grail; 6–11 VMs, contenedores, Kubernetes y topología; 12–15 servicios, latencia, fallos, tráfico, saturación, PurePath; 17–19 DQL. La sesión 2 se anuncia al final, pero no fue adjuntada. |
| Guía del Estudiante — Dynatrace | 14 | Playground → University → Essentials. Guía describe 9 lecciones y unas 4 h 30 min. Registro, términos y contraseña los realiza cada participante; no se crearon cuentas. |
| Conceptos Clave de Observabilidad en Dynatrace | 4 | pp. 1–2 señales, DQL, recorrido end-to-end, RUM/APM/infraestructura y negocio; 3–4 LiveDebugger, AppSec y Business Events. Disponibilidad depende del tenant/instrumentación, no se promete habilitación. |

## Correcciones técnicas para evitar falsas conclusiones

- Ausencia de requests no prueba que no llegó tráfico: revisar ventana, recurso, instrumentación, muestreo, filtros e ingestión antes de concluir. Charla 2 p. 7 simplifica este punto.
- Un `x-ms-request-id` no es necesariamente `operation_Id`. Obtener el ID de operación real de la telemetría y conservar ambos si existen.
- 4xx y 5xx ayudan a ubicar la investigación, pero un proxy, contrato mal implementado o validación backend puede originar un 4xx. No culpar automáticamente al frontend.
- `/health`, `/health/deep` y `/api/status` son ejemplos del workshop. Descubrir las rutas reales y el significado de su respuesta; no añadir endpoints nuevos por suposición.
- “Cada traza sin muestreo” en las diapositivas Dynatrace es una simplificación del material: verificar cobertura, configuración y políticas reales; una traza ausente no demuestra ausencia de ejecución.
- No se presupone que OneAgent, LiveDebugger, AppSec, RUM o Business Events estén instalados, licenciados o permitidos en el entorno del reto.

## Sitio de workshops

Se verificó el catálogo de [workshops](https://hackathoncopa.com/workshops): fundamentos Azure; APIs/frontend/backend; Git/GitHub/Terraform; observabilidad/KQL; troubleshooting; y Dynatrace. Se comprobaron los temas y la presencia de enlaces a grabaciones, no se reprodujeron ni transcribieron los videos. Los PDF adjuntos constituyen el contenido estudiado, no todo lo que pudo decirse en cada grabación.
