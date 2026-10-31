# Cuatro personas, cuatro asistentes

| Persona | Trabajo simultáneo en el error activo | Acceso Azure | Propiedad de cambios |
|---|---|---|---|
| P1 | Plataforma, publicación, KQL y correlación | Operador | IaC suministrada y cloud autorizado |
| P2 | Excepción, código, configuración y contrato | Segundo acceso cuando se necesite | Backend |
| P3 | Petición navegador, URL, payload y UX | Normalmente ninguno | Frontend |
| P4 | Priorizar, bitácora, preguntas y validación cruzada | Ninguno; recibe evidencia | Documentación e integración |

Para Dynatrace: P4 toma impacto/Problems/Service flow y DQL; P1 topología/infraestructura, P2 dependencias y trazas de servicios, P3 experiencia usuario/RUM si disponible. No se presupone que ambos tracks corran a la vez. Con narrativa final, repartir por dependencia y puntaje real, sin dejar un incidente crítico sin dueño.

## Evitar conflictos

Cada integrante trabaja con clon/carpeta propia. En repos oficiales, leer primero sus instrucciones y permisos de rama; el kit no los modifica. Un dueño por archivo incluso si se usan ramas distintas. Si un fix cruza backend y frontend, acordar contrato primero, dividir diffs y desplegar en el orden definido por dependencias.

Convención propuesta: `fix/e1-azure`, `fix/e1-backend`, `fix/e1-frontend`; sustituir e1 por error real desbloqueado. P4 revisa y coordina integración; no necesita ser administrador ni dueño del repositorio. Nadie reescribe historia ni sobreescribe cambios ajenos. Registrar repo, SHA, artefacto y validación; desplegar desde el commit integrado aprobado. No “último que guardó” como control de versiones.

## Compartir hallazgos

Antes del evento se puede preparar el kit por GitHub privado. Durante la competencia, obtener aclaración del mentor sobre commits/PR/Issues como colaboración entre los cuatro. No usar comentarios como chat si está prohibido; nunca pedir ayuda a personas externas por GitHub. Si se permite, cada persona entrega un archivo independiente `incidents/E1/P1.md` (etc.) usando la plantilla. P4 es el único editor de `incidents/index.md`; integra sin que cuatro editen una misma tabla. Los permisos de publicación del material del reto también deben estar confirmados.

Alternativa inmediata: comunicación verbal en la mesa y bitácora local en laptop P4; los otros tres muestran evidencia depurada en pantalla. No introducir plataformas nuevas para sortear reglas.

## Ciclo breve por error

1. P4 lee pregunta/narrativa y define error activo, resultado esperado y dueño.
2. P1/P2/P3 recogen evidencia distinta; anotan hora/entorno/ID.
3. Cada uno entrega síntoma → dato → hipótesis → prueba discriminante → resultado. Una hipótesis refutada se conserva para no repetirla.
4. Un responsable prepara cambio mínimo; otro revisa diff, prueba y alcance permitido. P4 prepara autorización concreta con la plantilla.
5. Aprobado el cambio, P1 ejecuta el procedimiento cloud suministrado. Un único despliegue o ajuste a la vez. Si cambia el alcance o el plan resulta destructivo, detener antes de ejecutarlo.
6. P2/P3 verifican el flujo afectado; P1 confirma telemetría y versión. P4 actualiza evidencia y borrador CTFd.
7. Revisor verifica formato y fuente. El participante designado aprueba/envía y registra aceptación real. Luego se habilita la siguiente etapa, si la plataforma así funciona.

Si pasan 10–15 minutos sin nueva evidencia (recomendación interna), parar cambios, releer el primer error completo, confirmar ámbito temporal/recursos y llevar al mentor una pregunta concreta. No repetir redeploys a ciegas ni intentar adivinar respuestas.
