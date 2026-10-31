# Incorporar entrega oficial sin rehacer el kit

Mantener el kit separado de IaC/backend/frontend. Al recibirlos, el dueño humano de cada componente registra URL autorizada, rama, SHA, instrucciones aplicables, versiones (`global.json`, `.csproj`, package.json/lockfile, Terraform requirements), rutas, nombres de configuración sin valores y endpoints reales. Usar `templates/repository-intake.md`.

Leer las instrucciones de cada repo antes de introducir AGENTS o skills; no sobrescribir las oficiales. No copiar código/logs al GitHub propio sin permiso de la organización. Si son reservados, guardar el inventario local excluido o mantener solo referencias permitidas.

Crear una actualización pequeña de conocimiento: hecho → fuente/archivo/línea/SHA → fecha → impacto sobre guía/consulta → responsable → estado. P4 revisa contradicciones con `knowledge/rules.md`; el especialista revisa los detalles de su dominio. Las recomendaciones descartadas se marcan sustituidas, no se siguen como norma.

Para consultas: confirmar tabla/campos del tenant, ejecutar primero con ventana corta, registrar revisión documental y ejecución real por separado en `templates/query-validation.md`. Actualizar solo la consulta afectada; no afirmar “verificada en producción” por una revisión de sintaxis.

Antes de integrar: revisión de secretos, enlaces, esquema, instrucciones oficiales y prueba dirigida. Versionar el kit por commit; un cambio de guía no despliega ninguna aplicación. Revalidar reglas al GO y si el mentor comunica una modificación.
