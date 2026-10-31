# Verificación y pendientes de entrega

Fecha: 30 de octubre de 2026, Panamá.

## Comprobado

- Se extrajeron y leyeron todas las páginas de los seis PDF: 25 + 10 + 18 + 21 + 14 + 4 = 92. Cápsulas se revisó además visualmente para ejemplos en imágenes. No se afirma auditoría visual página a página de los otros documentos.
- Se inspeccionaron los 15 archivos del ZIP de entrada sin ejecutar instrucciones de su contenido. Se conserva el archivo original y un registro de cambios.
- Cuatro roles especializados y cuatro skills con frontmatter, nombre y descripción. Las cuatro pasaron `quick_validate.py` de skill-creator; referencias relativas verificadas.
- Enlaces locales Markdown comprobados. Fuentes técnicas consultadas y citadas con nivel de verificación explícito.
- Revisión por patrones de secretos en contenido entregado y todos los archivos del ZIP original: sin coincidencias de tokens conocidos, claves privadas o asignaciones de contraseña detectadas. Revisión limitada; no certifica ausencia de cualquier dato sensible imaginable.
- Consultas con dos esquemas KQL y DQL; sustituciones explícitas y precondiciones documentadas. No contienen valores reales del entorno del reto.
- Conexión GitHub, cuenta autenticada y permisos de escritura verificados. El repositorio suministrado `Anaa-K03/agentes` estaba vacío y público; la usuaria autorizó su uso público. La escritura del README se intentó y fue rechazada con 403 Resource not accessible by integration; no se publicó contenido ni se cambiaron permisos o visibilidad.

## No ejecutado / no verificado

- No hay agentes persistentes o chats creados para los cuatro participantes, ni orquestación automática. Los archivos requieren activación por cada integrante; el selector de skills en sus equipos queda por comprobar.
- No se ejecutaron consultas en Azure/Grail, pruebas sobre aplicaciones Copa, Terraform, despliegues ni envíos CTFd. La revisión documental no prueba compatibilidad con un tenant real.
- No se visualizaron las grabaciones completas de los workshops ni se obtuvo la Sesión 2 Dynatrace. Se estudió el temario publicado y los PDF adjuntos.
- No se usa el navegador para esta publicación. El repositorio fue creado por la usuaria y se suministró su enlace; no se creó un repositorio nuevo desde el asistente.
- Faltan nombres de participantes/cuentas de GitHub, invitaciones, RG, repos oficiales, versiones, rutas reales, preguntas CTFd, tenant y permisos de datos. No se inventaron.
- Reconfirmar al GO el límite Azure, procedimiento de Terraform/portal, alcance de cambios de configuración y colaboración por GitHub durante el evento.

## Verificación práctica siguiente

Cada integrante abre el kit y activa su skill con un ejercicio de `docs/preparation.md`. Una vez recibidos los repos, registrar inventario y ejecutar solo las pruebas existentes pertinentes. Validar consultas con la ficha de `templates/query-validation.md` y reglas finales antes de publicar evidencia. El destino público fue autorizado por la usuaria; no hace falta repetir lectura ni investigación para utilizar el kit.

Pendiente de publicación: habilitar acceso de la integración al repositorio agentes en la cuenta propietaria Anaa-K03. El listado de instalaciones accesibles no mostró esa cuenta.
