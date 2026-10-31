# Preparación económica y práctica

Plan propuesto para el tiempo disponible antes del 31 de octubre de 2026; ajustar a la agenda final del evento. No aceptar anticipadamente invitaciones reservadas al GO.

1. **20 minutos, todos:** reglas, roles, cuentas propias ya accesibles, Git/IDE/navegador y cuatro chats con skill. Confirmar qué dispositivo/IA/datos/GitHub permite el mentor. No compartir contraseñas.
2. **30 minutos por especialidad, en paralelo humano:** P1 portal/Failures/KQL; P2 stack/configuración .NET; P3 Network/URL/CORS; P4 bitácora, CTFd y DQL. Usar los PDF por páginas citadas, no repetir todo el material en cada agente.
3. **30 minutos, ejercicio de mesa:** reproducir verbalmente los casos de abajo con evidencia simulada etiquetada. Cada rol debe dar una prueba discriminante y un cierre con criterios observables. Sin Azure ni despliegues de pago.
4. **15 minutos:** simular traspaso de evidencia y aprobación; comprobar que nadie declara resultados que no observó. Preparar checklist impreso/local si faltara red.
5. **Si hay tiempo adicional:** Playground y Essentials de Dynatrace; recorrer servicio → traza → logs. El curso completo descrito en la guía requiere unas 4 h 30 min; no es prerrequisito inventado de participación.

## Ejercicios y respuesta esperada

- **Simulado A:** UI vacía, Network muestra DNS de host genérico. P3 localiza fuente URL y build/runtime; P1 verifica URL asignada e instrumentación antes de interpretar ausencia de requests. No diagnosticar CORS sin evidencia.
- **Simulado B:** petición 500 y excepción nombra setting ausente. P2 sigue primera línea propia/proveedor, P1 contrasta presencia; un cambio autorizado y validación de la misma petición. No adivinar valor ni ocultar la excepción.
- **Simulado C:** API devuelve 200 por cliente HTTP, navegador bloquea origen. Verificar CORS y error subyacente, origen exacto/política activa; validar en navegador. No ampliar a *.
- **Simulado D:** servicio tarda 2 segundos y una dependencia concentra latencia. P4/P2 siguen traza y logs, P1 contrasta saturación; no concluir falta de índice sin evidencia de consulta/plan.
- **Simulado E:** no hay logs después de un fix. Comprobar intervalo/recurso/instrumentación/ingestión; no declarar curado el sistema.

Completar un ensayo útil significa que los cuatro producen evidencia, hipótesis refutable, dueño y prueba de cierre sin interferencia. Estos ejercicios no han sido ejecutados contra una aplicación ni equivalen a evaluación automática de agentes.
