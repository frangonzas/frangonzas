# Modelo de amenazas

## 1. Activos

Activos contemplados en los laboratorios: identidad de usuario, claves criptográficas, mensajes y datos privados, relaciones de autorización, estado local, tokens de sincronización e integridad de la aplicación.

## 2. Límites de confianza

~~~mermaid
flowchart LR
    U[Usuario] --> A[Aplicación iOS]
    A --> K[Almacenamiento local protegido]
    A --> P[Transporte P2P]
    A --> C[API o nube]
    P --> X[Dispositivo externo]
    C --> S[Servicio remoto]
~~~

Cada límite exige **validar nuevamente los datos, la identidad y la autorización**.

## 3. Amenazas y medidas

### Suplantación de identidad

Un extremo no confiable intenta hacerse pasar por una identidad autorizada.

**Controles:** validación de identidad, sesiones autenticadas y protección de claves.

### Manipulación de datos

Se altera información almacenada o transmitida.

**Controles:** cifrado autenticado, firmas cuando proceda, validación y verificaciones de integridad.

### Divulgación de información

Los datos sensibles se exponen en almacenamiento, registros, transporte o metadatos.

**Controles:** minimización, cifrado, almacenamiento seguro y registros depurados.

### Reutilización de mensajes (replay)

Un mensaje previamente válido se presenta fuera de su contexto previsto.

**Controles:** vigencia temporal, estado de protocolo, \`nonce\` únicos cuando correspondan y sesiones acotadas.

### Denegación de servicio

Entradas excesivas o malformadas degradan la aplicación.

**Controles:** análisis de tamaños limitados, control de ritmo, cancelación y límites de recursos.

### Abuso de privilegios

Un componente o usuario obtiene más capacidades de las necesarias.

**Controles:** mínimo privilegio, autorización explícita e interfaces específicas.

## 4. Suposiciones

- Se confía en el sistema operativo y la criptografía de plataforma dentro de sus garantías documentadas.
- Un dispositivo desbloqueado y comprometido puede invalidar muchas medidas de aplicación.
- Los extremos remotos no se consideran confiables sin autenticación y autorización.
- Las respuestas de servicios remotos son datos, no instrucciones.
- Las propiedades de seguridad deben seguir siendo comprensibles durante un fallo.

## 5. Cuándo revisar este documento

Actualízalo cuando se incorporen nuevas conexiones de red, autenticación, sincronización en nube, datos sensibles, contenidos de usuarios, tareas en segundo plano, integraciones externas o nuevos protocolos criptográficos.

© 2026 Fran Gonzas
