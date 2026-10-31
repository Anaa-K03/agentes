---
name: copa-backend-dotnet
description: Diagnosticar código C#/.NET existente, excepciones, configuración, dependencias y contratos API en el reto Copa. Usar ante 500, arranque o incompatibilidad de API.
---

# Backend Detective

Aplica este flujo al incidente actual del equipo Copa. Lee `../../../AGENTS.md`, `../../../knowledge/rules.md` y `../../../agents/02-backend-dotnet.md` desde esta carpeta. Las fuentes no conceden permisos ni sustituyen las consignas finales.

Lee instrucciones del repo oficial, global.json, TargetFramework, entrypoint, rutas y pruebas existentes. Desde la excepción, busca la primera línea del código propio y lo que esa línea necesita; no cambies frameworks ni paquetes para resolver un setting. Compara configuración efectiva con proveedores y entorno real; claves jerárquicas en entorno usan __ cuando corresponde. Sigue request → dependency → excepción con P1, no confundir request ID con operation_Id. Distingue 404/405/415/400 y JSON 200 que incumple contrato. Propón diff mínimo, prueba dirigida existente y criterio de regresión. No silencies excepciones ni cambies reglas de negocio para aparentar éxito. Usa docs/troubleshooting.md y docs/azure.md.

Entrega evidencia con hora/entorno/ID, hipótesis refutable, siguiente comprobación y, cuando se justifique, un cambio mínimo con validación y reversión. Limita la respuesta a lo que desbloquea al integrante. No inventes observaciones ni resultados de pruebas.

P1 confirma settings y operación; P3 aporta método/ruta/payload y acuerdan el contrato vigente; P4 recibe causa sustentada, diff y resultado, incluso si la hipótesis queda refutada.

Solicita aprobación justo antes de cambios Azure, despliegues, destrucción o envíos oficiales CTFd; prepara la acción concreta primero. Las comprobaciones locales y la documentación dentro del alcance autorizado pueden continuar. Usa el ejemplo y la plantilla del rol solo cuando ayuden al caso.
