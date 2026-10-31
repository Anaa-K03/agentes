# Reglas, recomendaciones y dudas

Prioridad: consignas finales del evento y aclaraciones del mentor dentro de las bases aplicables; después material de preparación. Una transcripción automática puede contener errores. Ante contradicción, registrar y aclarar; no decidir por conveniencia.

## Confirmado en documentos oficiales publicados

Las [bases legales](https://sthackathonwebpagermejaf.blob.core.windows.net/legal/2026-bases-legales-hackathon-copa.pdf), pp. 5–9 y 11, establecen equipos de cuatro, participación presencial, trabajo durante el evento, cumplimiento de instrucciones y posible descalificación por intercambio de información que otorgue ventaja. La evaluación registra intentos y hora de respuesta; el tiempo sirve como desempate. No fijar un número de intentos universal.

## Indicaciones de la charla transcrita, sujetas a ratificación

| Tema | Evidencia en Copa.pdf | Tratamiento operativo |
|---|---|---|
| Diagnosticar código existente, sin app/scripts desde cero ni cambiar funcionalidad | pp. 1, 4, 7 | Corregir solo lo indicado por el reto |
| Desplegar, observar, corregir, redesplegar y contestar | p. 1 | Validar en cada ciclo |
| Seis errores por secuencia | pp. 1–2, 7 | No asumir que E6 es accesible desde E1 |
| Tres repos: IaC, backend, frontend | p. 7 | El número de backends en p. 1 es ambiguo; inventariar entrega real |
| Suscripción compartida, RG por equipo, colaborador en su RG | pp. 1–4 | Verificar tenant/suscripción/RG; nada fuera de ellos |
| Máximo dos integrantes conectados a Azure | p. 2 | P1 operador, P2 observador cuando haga falta |
| Portal Azure, sin Azure CLI | p. 7 | No recomendar `az` ni Cloud Shell como alternativa para eludirlo |
| Invitación en correo registrado, aceptar al GO del día del reto | pp. 2–4 | “Mañana” es relativo a la charla; confirmar momento actual |
| CTFd, respuestas cerradas, bolsa de puntos de equipo | pp. 4–5, 8 | Un remitente acordado, revisión por otra persona |
| Mayúsculas toleradas según charla; decimales según pregunta | p. 5 | Respetar formato literal de la pregunta vigente |
| Celulares en bolsa; tablets solo Wi-Fi sin datos | pp. 8–9 | Seguir logística del mentor |
| IA y documentación online permitidas; sin mensajería/chat digital | pp. 9–10 | Asistentes de IA propios; nada de ayuda humana externa |

## Recomendaciones internas, no reglas oficiales

Un operador cloud, revisión de pares, un dueño por archivo, ramas por incidente, bitácora, una hipótesis por experimento, pausa breve de coordinación cada 10–15 minutos. Los roles pueden cambiar de foco para Dynatrace.

## Dudas que deben resolverse al inicio

- ¿Se permite compartir hallazgos por commits, PR o Issues privados entre los cuatro? La prohibición de chats no prueba que eso esté permitido. Hasta confirmarlo, no usar Issues/comentarios como mensajería; hablar en la mesa y llevar bitácora local.
- ¿Se pueden cargar código/logs del reto en un servicio de IA y en un repositorio privado propio? IA permitida no define todos los límites de datos.
- ¿Qué configuración exacta se permite corregir? Copa.pdf p. 1 dice que no se cambian configuraciones, pero el ciclo incluye correcciones y la Charla 2 enseña settings, URL y CORS. Aplicar solo narrativa y aclaración oficial; no declarar prohibido o permitido todo cambio de configuración.
- ¿Cómo se ejecuta Terraform suministrado respetando el uso del portal? No convertir “sin Azure CLI” en permiso para otra vía cloud no indicada.
- Credenciales, RG, versiones, endpoints, orden entre tracks, flags y pesos reales: pendientes de entrega.

La mención de MFA desactivado en la transcripción no es instrucción para deshabilitar MFA propio. No modificar seguridad de cuentas. No se revisó audio original completo: Copa.pdf termina como transcripción truncada a 30 minutos y contiene errores de reconocimiento.
