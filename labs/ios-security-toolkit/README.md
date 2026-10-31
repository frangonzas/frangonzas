# iOS Security Toolkit — Guía defensiva

> Referencia de arquitectura y revisión de seguridad para proyectos Swift/SwiftUI.

## Objetivo

Hacer visibles los controles seguros durante el diseño y desarrollo. No es una herramienta de explotación: reúne **preguntas de ingeniería defensiva** aplicables en cada revisión.

## Áreas a proteger

~~~text
Aplicación
├── Autenticación y autorización
├── Almacenamiento local
├── Transporte de red
├── Gestión de secretos y registros
├── Enlaces profundos y datos de usuarios
├── Permisos de privacidad
└── Acciones destructivas
~~~

## Guía de revisión

**Identidad:** ¿es local, remota o federada? ¿Qué establece confianza? ¿Se puede revocar una sesión robada? ¿La eliminación de cuentas es completa?

**Secretos:** ¿se evitan credenciales en Git? ¿Se excluyen tokens de los logs? ¿Se utiliza protección nativa? ¿Se puede rotar el material sensible?

**Red:** ¿se consideran no fiables las respuestas? ¿Existen tiempos de espera, TLS y reintentos limitados?

**Datos:** ¿se minimiza su recopilación? ¿Se define su conservación? ¿Se pueden borrar? ¿Se conocen las implicaciones de las copias y la sincronización?

**Experiencia de uso:** ¿se diferencian los estados sin conexión, sin autenticar y sin autorización? ¿Son comprensibles los errores y explícitas las acciones peligrosas?

## Verificación antes de publicar

- [ ] Sin secretos en código.
- [ ] Permisos y privacidad revisados.
- [ ] Eliminación destructiva probada.
- [ ] Modo sin conexión validado.
- [ ] Autorización verificada.
- [ ] Registros y dependencias revisados.
- [ ] Modelo de amenazas actualizado.

Consulta la [lista de verificación completa](../../docs/SECURITY-CHECKLIST.md).

© 2026 Fran Gonzas
