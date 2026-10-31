# Procedimientos concretos por síntoma

Ejemplos de workshop, no mapa de E1–E6. Detectar → Observar → Analizar → Hipótesis → Corregir → Validar. Para cada propuesta: archivo/recurso, dueño, evidencia, diff mínimo, riesgo, aprobación cloud, reversión.

| Síntoma | Primera prueba que discrimina | Causa a comprobar y posible corrección mínima | Validación y dueño |
|---|---|---|---|
| API 500 | Reproducir misma llamada; Failures/exception + ID y primera línea propia | Config, inicialización, dato o dependencia según stack; corregir solo causa evidenciada | Misma petición y respuesta esperada, sin nueva excepción; P2 + P1 |
| Variable ausente/inválida | Comparar clave leída con nombre/presencia real y proveedor efectivo | Jerarquía __, entorno, typo o IaC que sobrescribe; proponer ajuste en fuente autorizada | Reinicio/redeploy aprobado, inicialización y flujo; P2/P1 |
| Publicación fallida | Leer primer error completo de deployment/build, no solo el último resumen | Versión/runtime, artefacto, ruta salida, permisos/cuota según mensaje; usar script entregado | Deployment exitoso del SHA esperado + arranque + flujo; P1 |
| UI vacía, DNS/URL errónea | Network: host/método real; comparar URL de recurso asignado | Fuente de base URL y etapa de build/runtime; reconstruir si se embebe | Bundle nuevo, URL correcta, datos visibles; P3 |
| 404/405/415/400 o JSON 200 incorrecto | Comparar Network request/response con contrato real | Ruta, verbo, Content-Type o propiedad JSON; acordar lado que incumple contrato | Prueba API y UI con payload válido; P2/P3 |
| Mensaje CORS | Verificar si la respuesta subyacente falla; revisar Origin, OPTIONS si existe y headers | Origen exacto protocolo+host+puerto, política activa, orden middleware; corregir backend/plataforma autorizada | Navegador permite respuesta, no solo Postman; P3/P1/P2 |
| Servicio lento/no disponible | Correlacionar dependency/traza con métricas y logs | DNS, TLS, timeout, conexión, saturación o downstream; distinguir fallo transitorio de configuración | Misma transacción, latencia y dependencia comparables; P1/P2 |
| Health verde, negocio roto | Leer implementación real de health y ejecutar flujo afectado | Liveness no comprueba dependencias/flags; investigar readiness existente y warnings | Resultado funcional esperado y señales sin regresión; todos |

## CORS: comprobación detallada

Capturar origen y URL reales sin cookies/tokens. No todas las solicitudes requieren preflight; falta de OPTIONS no prueba error. Si hay OPTIONS, revisar status, redirect, Allow-Origin, Allow-Methods y Allow-Headers según solicitud. Un 500 sin cabecera CORS puede verse como CORS en navegador: arreglar la causa subyacente antes de ampliar política. Identificar si la política vive en App Service o ASP.NET; no activar ambas a ciegas. Nunca wildcard con credenciales, `mode: no-cors` ni desactivar seguridad del navegador.

## Evidencia mínima útil

Petición no sensible, hora con zona, status y cuerpo depurado, ID real, rol/servicio, primer error/stack, versión observada, configuración por nombre/presencia. Un HAR puede contener secretos: depurarlo antes de compartir; preferir un fragmento mínimo. No registrar rutas con tokens de acceso.

## Qué cuenta como validación

Registrar comando o acción efectivamente realizada, entorno, SHA/artefacto y resultado observado. Una compilación correcta solo prueba compilación. Prueba local no prueba cloud. Health sin semántica no prueba negocio. Respuesta preparada no prueba aceptación CTFd. Si faltan rutas/acceso/datos, conservar estado pendiente.
